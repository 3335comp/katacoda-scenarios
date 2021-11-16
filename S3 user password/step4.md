To check a password, use the VALIDATE_PASSWORD_STRENGTH() function:

run by command:

`SELECT VALIDATE_PASSWORD_STRENGTH('weak');`{{execute}} 

`SELECT VALIDATE_PASSWORD_STRENGTH('lessweak$_@123');`{{execute}} 

`SELECT VALIDATE_PASSWORD_STRENGTH('N0Tweak$_@123!');`{{execute}} 
      
Result should be like this
<pre>
mysql> SELECT VALIDATE_PASSWORD_STRENGTH('weak');
+------------------------------------+
| VALIDATE_PASSWORD_STRENGTH('weak') |
+------------------------------------+
|                                 25 |
+------------------------------------+
mysql> SELECT VALIDATE_PASSWORD_STRENGTH('lessweak$_@123');
+----------------------------------------------+
| VALIDATE_PASSWORD_STRENGTH('lessweak$_@123') |
+----------------------------------------------+
|                                           50 |
+----------------------------------------------+
mysql> SELECT VALIDATE_PASSWORD_STRENGTH('N0Tweak$_@123!');
+----------------------------------------------+
| VALIDATE_PASSWORD_STRENGTH('N0Tweak$_@123!') |
+----------------------------------------------+
|                                          100 |
+----------------------------------------------+
</pre>
