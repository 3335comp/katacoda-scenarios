In this scenario, we are going to teach our users how to make use of the autocommit, Commit, and Rollback functions introduced in InnoDB

Typically individual DML (Insert, Update, Delete) statements are performed in an autocommit transaction, 
which those commands are committed as soon as the statement successfully completes. 
There will be no opportunity to roll back the database to the state prior to the statement if autocommit is enabled. 
When something goes wrong, the only restoration option available is to reconstruct the data from a backup (providing one exists).

In MySQL, autocommit is on by default for InnoDB, here in this case, we are going to teach you how to disable this option.

Secondly, after seting up a MYSQL enviroment, we will create a testing database and table for experiment:

 Create a table inside the database

 `CREATE DATABASE testDB;`{{execute}} 
 
 `START TRANSACTION;`{{execute}} 

 `use testDB;`{{execute}} 

 `CREATE TABLE tester (age INT, name CHAR (20), INDEX (age));`{{execute}} 
 
 Do a transaction with autocommit turned on.
 
 `START TRANSACTION;`{{execute}} 
 
 `show tables;`{{execute}} 

 Insert show orgin info inside
 
 `INSERT INTO tester VALUES (10, 'Alice');`{{execute}} 

 `SELECT * FROM tester;`{{execute}}
 
 Result should be like this
 <pre>
 mysql> SELECT * FROM tester;
 +------+-------+
 | age  | name  |
 +------+-------+
 |   10 | Alice |
 +------+-------+
 </pre>
 
