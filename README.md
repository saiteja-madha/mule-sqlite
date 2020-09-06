# Description
This project demonstrates how to establish a connection with an SQLite file (.db) in Mule 4 and perform various SQL operations<br>

# Configuring Global Element
* Add the Database connector as usual, and add the Database config file
* Change the connection type to **Generic Connection**
* Generic Database Connector configuration information <br>
**URL**: jdbc:sqlite:[path to your database file]  (Example: jdbc:sqlite:c:/database.db) <br>
**Driver Class Name**: org.sqlite.JDBC

For the sake of simplicity, you can directly add the path to your .db file in the *common.properties* file under resources folder

### General Debugging
#### Symptom:
Getting a "java.sql.SQLException: [SQLITE_ERROR] SQL error or missing database" on execution, but 'Test Connection' is fine.

#### Suggestion:
Check if you have a relative path. <br>
Relative paths, they are in theory supported (and a quick google confirms as such) but where they are relative to is clearly different than other resources in the mule container.
