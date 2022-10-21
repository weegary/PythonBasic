#Database

```python
import pyodbc
import pandas as pd

database_ip = ""
database_name = ""
user_id = ""
user_pw = ""
table_name = ""

connection_str = ("Driver={SQL Server Native Client 11.0};" #固定語法
            "Server=" + database_ip + ";"
            "Database="  + database_name + ";"
            "UID=" + user_id + ";"
            "PWD=" + user_pw + ";" )
connection = pyodbc.connect(connection_str)


sql_text = ('''
            SELECT *
            FROM ['''+database_name+'''].[dbo].['''+table_name+''']
            ''')

data = pd.read_sql(sql_text,connection)
del connection


# create connection
# create sql query
# read query result >> data 
# close (delete) connection
```
