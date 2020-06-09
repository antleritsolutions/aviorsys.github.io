---
layout: post
title: "First Selenium Test automation Script with Java"
categories: Technology
author: "Anuradhika Wijayathilake"
---
 ![cover Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/selenium-test-automation.jpg)

# What is selenium?

**Selenium** is a widely used test automation framework. There are 3 selenium tools; Selenium RC,
Selenium IDE and Selenium Webdriver, out of which the Selenium Webdriver is the most commonly used
industry tool. Using the Selenium Webdriver the test cases can be automated with Java.

To learn more about selenium, follow the link below:
<https://www.seleniumhq.org/docs/01_introducing_selenium.jsp#introducing-selenium>

### Environment Setup

First you need to install java to the PC.
Then the Eclipse IDE needs to be installed. Next the Selenium Webdriver for Java must be downloaded.

### Follow the link below:
<https://www.seleniumhq.org/download/>

#### Example

### Step 1 : Create a new project.

a. Open Eclipse and go on to the File tab and click on New.Then select Java project.

 ![First Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/1.JPG)

 b. Give your project name and then click Finish.

  ![Second Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/2.JPG)

**Newly created project will display in eclipse project explorer)**


###  Step 2 : Create a Package

a. Right click on the created project and go New.Then click on Package.

![Third Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/3.JPG)


b.
Give your package name and click on Finish.

![Fourth Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/4.JPG)

**(Newly created package display under the created project)**

### Step 3 : Create new Java Class

a. Right click on the created package and go New.Then click on Java Class.

![Fifth Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/5.JPG)

**(Newly created class display under the created package)**

### Step 4 : Add Selenium jars to the Project.

a. Right-click on Project and Select Properties then Java build path. Then navigate to Libraries tab and
click Add External JARs.

![sixth Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/6.JPG)

b. Add Selenium Java jar source file.

![seventh Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/7.JPG)

c. Add all the jars from the libs folder.

![eighth Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/8.JPG)

d. Click Apply and then OK.

![tenth Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/10.JPG)

### Step 5 : Write test Script

For example, the following test will direct you to the Antler Group website.the following steps are included
in the script,

- Launch the Chrome browser
- Open website “Antlergroup.com”
- Print a Message to display that the website is opened successfully
- Wait for 5 Seconds
- Close the Browser

![leventh Image](https://github.com/aviorsys/aviorsys.github.io/raw/master/images/11.JPG)












