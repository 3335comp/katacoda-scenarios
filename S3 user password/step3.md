validate_password checks the cleartext password in the following statement. Under the default password policy, which requires passwords to be at least 8 characters long, the password is weak and the statement produces an error:

`CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'newpassword';`{{execute}} 

<pre>
mysql> CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'newpassword';
ERROR 1819 (HY000): Your password does not satisfy the current
policy requirements
</pre>


validate_password checks the cleartext password in the following statement. Under the default password policy, which requires passwords to be at least 8 characters long, the password is weak and the statement produces an error:

`ALTER USER USER() IDENTIFIED BY 'abc';`{{execute}} 

<pre>
mysql> ALTER USER USER() IDENTIFIED BY 'abc';
ERROR 1819 (HY000): Your password does not satisfy the current
policy requirements
</pre>

Selecting a Database 'test'

`use test`{{execute}} 

To enable encryption for a new file-per-table tablespace, specify the ENCRYPTION option in a CREATE TABLE statement. 
 #The following example assumes that innodb_file_per_table is enabled.

`CREATE TABLE t1 (c1 INT) ENCRYPTION='Y';`{{execute}} 

To enable encryption for an existing file-per-table tablespace, specify the ENCRYPTION option in an ALTER TABLE statement.

`ALTER TABLE t1 ENCRYPTION='Y';`{{execute}} 

To disable encryption for file-per-table tablespace, set ENCRYPTION='N' using ALTER TABLE.

`ALTER TABLE t1 ENCRYPTION='N';`{{execute}} 
