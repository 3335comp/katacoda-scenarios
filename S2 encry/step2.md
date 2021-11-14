A keyring plugin must be installed and configured. Keyring plugin installation is performed at startup using the early-plugin-load option. Early loading ensures that the plugin is available prior to initialization of the InnoDB storage engine.

Install by command:
`INSTALL PLUGIN keyring_file SONAME 'keyring_file.so';`{{execute}} 

To verify that a keyring plugin is active, use the SHOW PLUGINS statement or query the INFORMATION_SCHEMA.PLUGINS table.

Check by command:
`SELECT PLUGIN_NAME, PLUGIN_STATUS
       FROM INFORMATION_SCHEMA.PLUGINS
       WHERE PLUGIN_NAME LIKE 'keyring%';`{{execute}} 
       
Result should be like this
<pre>
mysql> SELECT PLUGIN_NAME, PLUGIN_STATUS
       FROM INFORMATION_SCHEMA.PLUGINS
       WHERE PLUGIN_NAME LIKE 'keyring%';
+--------------+---------------+
| PLUGIN_NAME  | PLUGIN_STATUS |
+--------------+---------------+
| keyring_file | ACTIVE        |
+--------------+---------------+
</pre>

If the PLUGIN_STATUS is "ACTIVE"; that mean the encryption function can be use.
