---
layout: post
title: "Evolution of Database Management"
tagline: "An introduction to Database Management"
categories: Technology
author: "Anuradhika Ravini"
---

**Evolution of Database Management Systems** From earlier stage flat-file system, to relational and object-relational systems, database technology has gone through many generations and its history that is spread over more than 40 years now.

**1968 file based** Predecessor of database,data was maintained in a flat file. in past,later we used punched cards technology was used to store data.but the files have no such advantage,rather have several limitations.

**1968-1980 Era of Hierarchical Database** Prominent hierarchical database model was IBM’s first DBMS called IMS(Information Management System).

- Hierarchical data Model-In this model,files are linked in apparent/child manner,with each child file having at most one parent file.

- Network data Model-In network data model,files are linked as owners and members,similar to the common network model except that each member file can have more than one owner.
The hierarchical model and the network model were in use in almost the same era.

**1970-present Era of Relational Database and Database Management**The relational database model was conceived by E. F. Codd in 1970. It can be defined using the following two terminologies.

- Instance-a table with rows or columns.

- Schema-specifies the structure(name of relation,name and type of each column)

The model is based on branches of mathematics called set theory and predicate logic.
Object oriented data model:
It gives the modeling and creation of the data as objects.

## Advantages and Disadvantages of DBMS approch vs file based system approach

### Advantages of DBMS over file based systems

1.Controlling Redundancy  
In file system, each application has its own private files, which cannot be shared between multiple applications. This can often lead to considerable redundancy in the stored data, which results in wastage of storage space. By having centralized database most of this can be avoided.

2.Integrity can be enforced
Integrity of data means that data in database is always accurate, such that incorrect information cannot be stored in database. In order to maintain the integrity of data, some integrity constraints are enforced on the database. A DBMS should provide capabilities for defining and enforcing the constraints.

3.Data can be shared
Data is shared by multiple applications in based DBMS as compared to file system so now applications can be developed to operate against the same stored data. 

4.Restricting unauthorized access
When multiple users share a database, it is likely that some users will not be authorized to access all information in the database. Hence, the type of access operation retrieval or update must also be controlled. Typically, users or user groups are given account numbers protected by passwords, which they can use to gain access to the database. A DBMS should provide a security and authorization subsystem, which the DBA uses to create accounts and to specify account restrictions. The DBMS should then enforce these restrictions automatically.

5.Providing Backup and Recovery
 A DBMS must provide facilities for recovering from hardware or software failures. The backup and recovery subsystem of the DBMS is responsible for recovery. database is restored to the state it was in before the program started executing.

6.Data Model can be developed
 The centralized system is able to represent the complex data and interfile relationships, which results better data modeling properties.

7.Inconsistency can be avoided
 When the same data is duplicated and changes are made at one site, which is not propagated to the other site, it gives rise to inconsistency and the two entries regarding the same data will not agree. 

### Disadvantages of DBMS over data systems

1.Cost of DBMS
The cost of DBMS varies significantly, depending on the environment and functionality provided. There is also the recurrent annual maintenance cost.

2.Complexity
 The provision of the functionality that is expected of a good DBMS makes the DBMS an extremely complex piece of software. Database designers, developers, database administrators and end-users must understand this functionality to take full advantage of it. Failure to understand the system can lead to bad design decisions, which can have serious consequences for an organization.

3.Performance
Typically, a File Based system is written for a specific application, such as invoicing. As result, performance is generally very good. However, the DBMS is written to be more general, to cater for many applications rather than just one. The effect is that some applications may not run as fast as they used to.

4.Higher impact of a failure
The centralization of resources increases the vulnerability of the system. Since all users and applications rely on the availability of the DBMS, the failure of any component can bring operations to a halt.

<embed src="https://drive.google.com/viewerng/viewer?embedded=true&url=https://github.com/aviorsys/aviorsys.github.io/raw/master/uploads/Evolution-of-Database-Management-Systems.pdf" width="100%" height="500">

#### References

* Robbin R.j. (1994). database fundamentals. Available: www.esp.org/db-fund.pdf

* carl chebi. (2015). introduction of database management system.Available

