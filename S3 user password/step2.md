INSTALL PLUGIN loads the plugin, and also registers it in the mysql.plugins system table to cause the plugin to be loaded for each subsequent normal server startup without the need for --plugin-load-add.

Install by command:
`INSTALL PLUGIN validate_password SONAME 'validate_password.so';`{{execute}} 

To verify that a keyring plugin is active, use the SHOW PLUGINS statement or query the INFORMATION_SCHEMA.PLUGINS table.

Check by command:
 `SELECT PLUGIN_NAME, PLUGIN_STATUS
       FROM INFORMATION_SCHEMA.PLUGINS
       WHERE PLUGIN_NAME LIKE 'validate%'`{{execute}} 
       
Result should be like this
<pre>
mysql> SELECT PLUGIN_NAME, PLUGIN_STATUS
       FROM INFORMATION_SCHEMA.PLUGINS
       WHERE PLUGIN_NAME LIKE 'validate%';
+-------------------+---------------+
| PLUGIN_NAME       | PLUGIN_STATUS |
+-------------------+---------------+
| validate_password | ACTIVE        |
+-------------------+---------------+
</pre>

If the PLUGIN_STATUS is "ACTIVE"; that mean the function can be use.
