Last, we can use ROLLBACK command to roll back the hacked information to correct information
 `ROLLBACK;`{{execute}}

 After that check it again.
 
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

