This account-creation statement fails, even though the account is locked initially, because it does not include a password that satisfies the current password policy:

`CREATE USER 'juanita'@'localhost' ACCOUNT LOCK;`{{execute}} 

<pre>
mysql> CREATE USER 'juanita'@'localhost' ACCOUNT LOCK;
ERROR 1819 (HY000): Your password does not satisfy the current
policy requirements
</pre>

validate_password checks the cleartext password in the following statement. Under the default password policy, which requires passwords to be at least 25 characters long, the password is weak and the statement produces an error:

`CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'newpassword';`{{execute}} 

<pre>
mysql> CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'newpassword';
ERROR 1819 (HY000): Your password does not satisfy the current
policy requirements
</pre>

Seccess:

`CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'ASDnewpasswordpasspasspass123456789123456897.';`{{execute}} 

<pre>
mysql> CREATE USER 'jeffrey'@'localhost' IDENTIFIED BY 'ASDnewpasswordpasspasspass123456789123456897.';
Query OK, 0 rows affected (0.01 sec)
</pre>

It also happen in ALTER,

`ALTER USER USER() IDENTIFIED BY 'abc';`{{execute}} 

<pre>
mysql> ALTER USER USER() IDENTIFIED BY 'abc';
ERROR 1819 (HY000): Your password does not satisfy the current
policy requirements
</pre>

`ALTER USER 'jeffrey'@'localhost'
       IDENTIFIED WITH mysql_native_password
       AS '*0D3CED9BEC10A777AEC23CCC353A8C08A633045E';`{{execute}} 

<pre>
mysql> ALTER USER 'jeffrey'@'localhost'
       IDENTIFIED WITH mysql_native_password
       AS '*0D3CED9BEC10A777AEC23CCC353A8C08A633045E';
Query OK, 0 rows affected (0.01 sec)
</pre>
