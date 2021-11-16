The master encryption key should be rotated periodically and whenever you suspect that the key has been compromised.

Rotating the master encryption key only changes the master encryption key and re-encrypts tablespace keys. It does not decrypt or re-encrypt associated tablespace data.

To rotate the master encryption key, run by command:

`ALTER INSTANCE ROTATE INNODB MASTER KEY;`{{execute}} 

When the ENCRYPTION option is specified in a CREATE TABLE or ALTER TABLE statement, it is recorded in the CREATE_OPTIONS column of INFORMATION_SCHEMA.TABLES. This column can be queried to identify tables that reside in encrypted file-per-table tablespaces.

Check by command:

`SELECT TABLE_SCHEMA, TABLE_NAME, CREATE_OPTIONS FROM INFORMATION_SCHEMA.TABLES
       WHERE CREATE_OPTIONS LIKE '%ENCRYPTION%';`{{execute}} 
       
Result should be like this
<pre>
mysql> SELECT TABLE_SCHEMA, TABLE_NAME, CREATE_OPTIONS FROM INFORMATION_SCHEMA.TABLES
       WHERE CREATE_OPTIONS LIKE '%ENCRYPTION%';
+--------------+------------+----------------+
| TABLE_SCHEMA | TABLE_NAME | CREATE_OPTIONS |
+--------------+------------+----------------+
| test         | t1         | ENCRYPTION="Y" |
+--------------+------------+----------------+
</pre>

If the CREATE_OPTIONS is "ENCRYPTION="Y""; that mean the encryption function is enabled.

We can also query INFORMATION_SCHEMA.INNODB_SYS_TABLESPACES to retrieve information about the tablespace associated with a particular schema and table.

By command:

`SELECT SPACE, NAME, SPACE_TYPE FROM INFORMATION_SCHEMA.INNODB_SYS_TABLESPACES WHERE NAME='test/t1';`{{execute}} 
       
Result should be like this
<pre>
mysql> SELECT SPACE, NAME, SPACE_TYPE FROM INFORMATION_SCHEMA.INNODB_SYS_TABLESPACES WHERE NAME='test/t1';
+-------+---------+------------+
| SPACE | NAME    | SPACE_TYPE |
+-------+---------+------------+
|     3 | test/t1 | Single     |
+-------+---------+------------+
</pre>
