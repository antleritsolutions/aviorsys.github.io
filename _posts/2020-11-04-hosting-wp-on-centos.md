---
layout: post
title: "Configure CentOS to host WordPress with Nginx"
tagline: "A detailed walkthrough to configure CentOS to host WordPress with Nginx"
categories: LinuxHosting
author: "Lakshan Dissanayake"
---

![img1](https://res.cloudinary.com/practicaldev/image/fetch/s--dt73NGmn--/c_imagga_scale,f_auto,fl_progressive,h_420,q_auto,w_1000/https://dev-to-uploads.s3.amazonaws.com/i/en3zqyvlplmhyovbwvb8.jpg)

# Configure CentOS to host WordPress with Nginx

I’ve been told to set up a WordPress installation on a CentOS server. While most of CentOS based WordPress hosting providers offer cPanel, I had thoughts of writing a tutorial regarding configuring a server from zero.

A WordPress site consists of 3 main parts

* PHP Interpreter
* Database
* Web Server

Let’s walk through the tutorial and find out what each of these does.

## Setup MariaDB
Even though WordPress is written in PHP, it needs a MySQL/MariaDB database for its functionality. So we’ll choose MariaDB as our SQL database.

### Install MariaDB
CentOS is packed with an old version of MariaDB which impacts on overall performance. So let’s update the MariaDB source repository configurations and install it.

```bash
# install mariadb-server
wget https://downloads.mariadb.com/MariaDB/mariadb_repo_setup
chmod +x mariadb_repo_setup 
sudo ./mariadb_repo_setup
sudo yum install mariadb-server
```

### Configure MariaDB
You need a database and properly configured MySQL user for the access of the database. let’s create a database and user.

Even though you can use MySQL root for WordPress, I strongly discourage you to do so. Because if somehow your password gets compromised, You’ll compromise other databases on your host as well.

```bash
# configure mariadb to start automatically upon system boot
sudo systemctl enable mariadb.service
sudo systemctl restart mariadb.service
# enhance security by setting up root password and other enhancements
sudo mysql_secure_installation
# login to mysql
sudo mysql -u root
# create database
mysql > CREATE DATABASE wordpress DEFAULT CHARACTER SET utf8 COLLATE utf8_unicode_ci;
# create user
mysql > grant all privileges on wordpress.* to 'wp_user'@'localhost' identified by 'secure-password';
mysql > flush privileges;
```

## Setup PHP and Nginx
We need a PHP interpreter to render raw HTML from PHP scripts and we also need a webserver to serve those. Since we’re seeking for an open-source server solution with robust speed there are several server solutions. For the purpose of this demonstration, we will Nginx as the webserver.

### Install Nginx and PHP
By default, Nginx is not listed in CentOS software repository and also the PHP version it bears is an old one. So let’s update the software repositories and install Nginx and PHP with other dependencies.

```sh
# setup required repositories for Nginx/PHP
sudo yum install -y epel-release
# setup required repositories for php74-php-fpm
sudo yum -y install https://dl.fedoraproject.org/pub/epel/epel-release-latest-7.noarch.rpm
sudo yum -y install https://rpms.remirepo.net/enterprise/remi-release-7.rpm
# install Nginx
sudo yum install -y nginx
# install PHP
sudo yum install -y php74-php-fpm php74-php-mysqlnd php74-php-mbstring php74-php-zip php74-php-gd php74-php-imagick php74-php-xml
# enable and restart nginx php74-php-fpm services
sudo systemctl enable nginx php74-php-fpm
sudo systemctl restart nginx php74-php-fpm
```

PHP and Nginx are been installed successfully at this point. But we need to change some configurations of PHP and Nginx as well.

### Configure PHP
Edit the /etc/opt/remi/php74/php.ini and make the following changes

```sh
# uncomment cgi.fix_pathinfo and change the value to 0
cgi.fix_pathinfo = 0
# change the value of post_max_size
post_max_size = 64M
# change the value of upload_max_filesize
upload_max_filesize = 32M
```

Edit the /etc/opt/remi/php74/php-fpm.d/www.conf as follows.
```sh
# change  the user to nginx
user = nginx
# change  the group to nginx
group = nginx
# uncomment and change  the listen.owner to nginx
listen.owner = nginx
# uncomment and change  the listen.group to nginx
listen.group = nginx
# change listen as follows
listen = /run/php74-fpm.sock
```
### Download WordPress
Let’s take a fresh build of WordPress from the WordPress site and extract it where you want your site to be located.

```bash
# download latest WordPress build
wget https://wordpress.org/latest.tar.gz
sudo tar -xzf latest.tar.gz -C /path/to/web-site
```
Change the ownership of extracted WordPress files
Changing the ownership of the WordPress files to the PHP user is an absolute requirement. Otherwise, PHP interpreter won’t be able to access those files and you face issues with rendering PHP.

```bash
# change the owner of the website to nginx
sudo chown -R nginx:nginx /path/to/web-site
```
### Set SELinux permissions
Since SELinux bundled with CentOS, We’ll have to let SELinux knows that the extracted files will be read and written. Execute the following to do so.

```bash
sudo setenforce 1
# enable content readable by php-fpm
sudo chcon -Rt httpd_sys_content_t /path/to/web-site
#enable content writable by php-fpm
sudo chcon -Rt httpd_sys_rw_content_t /path/to/web-site/wrirable-dir
```

## Configure Nginx
Create the following directories
```bash
# holds all (active / inactive) site configurations
sudo mkdir -p /etc/nginx/sites-available
# holds Nginx active site configurations
sudo mkdir -p /etc/nginx/sites-enabled
```

Edit /etc/nginx/nginx.conf and put the following content at the end of http block
```sh
# enable gzip compression
gzip              on;
gzip_buffers      16 8k;
gzip_comp_level   5;
gzip_http_version 1.0;
gzip_min_length   10240;
gzip_types        text/plain text/css application/x-javascript text/xml application/xml application/xml+rss text/javascript image/x-icon image/bmp;
gzip_vary         on;
gzip_proxied expired no-cache no-store private auth;
gzip_disable "MSIE [1-6]\.";
# per site configurations
include /etc/nginx/sites-enabled/*;
```
Create an empty file in /etc/nginx/sites-available/my.domain.tld and put the following content
```sh
server {
    server_name my.domain.tld;
    root /path/to/web-site;
    index index.php;
    error_log /var/log/nginx/my.domain.tld/error.log;
    access_log /var/log/nginx/my.domain.tld/access.log;
    location = /favicon.ico {
        log_not_found off;
        access_log off;
    }
    location = /robots.txt {
        allow all;
        log_not_found off;
        access_log off;
    }
    location / {
        try_files $uri $uri/ /index.php?$args;
    }
    location ~ \.php$ {
        include fastcgi.conf;
        fastcgi_intercept_errors on;
        fastcgi_pass unix:/run/php74-fpm.sock;
    }
    location ~* \.(js|css|png|jpg|jpeg|gif|ico)$ {
        expires max;
        log_not_found off;
    }
    client_max_body_size 64M;
    listen 443 ssl;
    listen [::]:443 ssl;
    ssl_certificate /etc/ssl/my.domain.tld-certs/certificate.pem;
    ssl_certificate_key /etc/ssl/my.domain.tld-certs/privatekey.pem;
}
server {
    if ($host = my.domain.tld) {
        return 301 https://$host$request_uri;
    }
    server_name my.domain.tld;
    listen 80;
    listen [::]:80;
    return 404;
}
```
Link the configuration to Nginx
```bash
# activate the site
sudo ln -s /etc/nginx/sites-available/my.domain.tld /etc/nginx/sites-enabled
```
## Reload Nginx and PHP
Let’s restart the Nginx and PHP services.
```bash
# restart nginx and php-fpm
sudo systemctl restart php74-php-fpm nginx
```
### Congratulations
Yay!!! You have successfully configured a CentOS server with PHP and Nginx. There are a lot more configurations that we didn’t even talk about in this tutorial. Just browse and look at the official documentation of Nginx, PHP and SELinux.

Don’t forget to strength up your server by implementing a Firewall. So if you have done everything correctly, with a proper DNS direction, your site should be online by now.

Originally posted on [dev.to](https://dev.to/lakshanwd/configure-centos-to-host-wordpress-with-nginx-2ld2)