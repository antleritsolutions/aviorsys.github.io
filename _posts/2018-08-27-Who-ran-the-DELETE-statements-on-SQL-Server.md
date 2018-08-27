---
layout: post
title: "Who ran the DELETE statements on SQL Server"
tagline: "SQL World"
categories: technology
author: "Chathuranga Karunarathna"
---
## Delete Statement on SQL Server

It’s commonly happened at all work place where an user ran a **DELETE** command by mistake or intensely on a SQL Server and no one will be accepting who did this. Here, I would like to demonstrate a way using the transaction log to track down helpful information related to this fact.

* **Step 1**
Before moving forward, we will create a database and a table on which I will delete some data. Run the below SQL code to create a database and table.
```sql
--Create DB.
USE [master];
GO
CREATE DATABASE ReadingDBLog;
GO
-- Create tables.
USE ReadingDBLog;
GO
CREATE TABLE [Location] (
    [Sr.No] INT IDENTITY,
    [Date] DATETIME DEFAULT GETDATE (),
    [City] CHAR (25) DEFAULT 'Bangalore'
);
```

* **Step 2**
We have created a database named `ReadingDBLog` and a table `Location` with three columns. Now we will insert a 100 rows into the table.

* **Step 3**
Now go ahead and delete some rows to check who has deleted your data. You can see in the above screenshot that a row has been deleted from the table `Location`. I also ran a `SELECT` statement to verify the data has been deleted.

* **Step 4**
Now we have to search the transaction log file to find the info about the deleted rows. Run the below command to get info about all deleted transactions. All transactions which have executed a DELETE statement will display by running the above command and we can see this in the above screenshot. As we are searching for deleted data in table Location, we can see this in the last row. We can find the table name in the `AllocUnitName` column. The last row says a DELETE statement has been performed on a HEAP table `dbo.Location` under transaction ID 0000:000004ce. Now capture the transaction ID from here for our next command.

* **Step 5**
We found the transaction ID from the above command which we will use in the below command to get the transaction SID of the user who has deleted the data.Here, we can see the [Begin Time] of this transaction which will also help filter out the possibilities in finding the exact info like when the data was deleted and then you can filter on the base of begin time when that command was executed. We can read the above output as "A DELETE statement began at 2013/10/14 12:55:17:630 under transaction ID 0000:000004ce by user transaction SID 0x0105000000000005150000009F11BA296C79F97398D0CF19E8030000. Now our next step is to convert the transaction SID hexadecimal value into text to find the real name of the user.

* **Step 6**
Now we will figure out who ran the DELETE command. We will copy the hexadecimal value from the transaction SID column for the DELETE transaction and then pass that value into the `SUSER_SNAME()` function.

#### Refferences
* <https://www.mssqltips.com/sqlservertip>

<embed src="https://drive.google.com/viewerng/viewer?embedded=true&url=https://github.com/aviorsys/aviorsys.github.io/raw/master/uploads/finding-a-user-who-ran-a-delete-statement.pdf" width="100%" height="500">
