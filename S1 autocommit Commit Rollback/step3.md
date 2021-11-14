 After finsihed the information setup, we will process the ROLLBACK funactions:
 First, we will using COMMIT to create a save log here.
 
 `COMMIT;`{{execute}} 

 `SET autocommit=0;`{{execute}} 

 Assume some people change the info inside
 
 `INSERT INTO tester VALUES (10, 'Bob');`{{execute}} 

 `DELETE FROM tester WHERE name = 'Alice';`{{execute}} 

 `SELECT * FROM tester;`{{execute}}
 
 Result should be like this
 <pre>
 mysql> SELECT * FROM tester;
 +------+------+
 | age  | name |
 +------+------+
 |   10 | Bob  |
 +------+------+
 </pre>
