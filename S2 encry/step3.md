Creating a Database 'teat'

`CREATE DATABASE test;`{{execute}} 

Selecting a Database 'test'
`use test`{{execute}} 

To enable encryption for a new file-per-table tablespace, specify the ENCRYPTION option in a CREATE TABLE statement. 
 #The following example assumes that innodb_file_per_table is enabled.

`CREATE TABLE t1 (c1 INT) ENCRYPTION='Y';`{{execute}} 

To enable encryption for an existing file-per-table tablespace, specify the ENCRYPTION option in an ALTER TABLE statement.

`CREATE TABLE t1 (c1 INT) ENCRYPTION='Y';`{{execute}} 

To disable encryption for file-per-table tablespace, set ENCRYPTION='N' using ALTER TABLE.

`CREATE TABLE t1 (c1 INT) ENCRYPTION='N';`{{execute}} 
