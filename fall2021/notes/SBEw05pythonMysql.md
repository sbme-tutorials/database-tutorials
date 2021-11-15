* TOC
{:toc}

## Introduction: Python Mysql connector

* Python can be used in database applications.
* One of the most popular databases is MySQL.

## Prerequisites 

1. AMPPS installation check course homepage
2. install python recommended **Anaconda distribution**
3. install mysql connector for python
```
conda   install -c anaconda mysql-connector-python 
```

**To check everything is going well**
1. start Ampps server
2. run the following python code

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root"
)

print(mydb) 
```

you should see 
```
<mysql.connector.connection_cext.CMySQLConnection object at 0x7fdcf9307790>
```

**previously we implemented many tables on ampps server lets check if they existed**: you should see all databases implemented on your ampps

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root"
)

mycursor = mydb.cursor()

mycursor.execute("SHOW DATABASES")

for x in mycursor:
  print(x) 
```

## Create with python mysql

1. create new database

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root"
)

mycursor = mydb.cursor()
mycursor.execute("CREATE DATABASE MyPythonDatabase")
```
Now you can open ampps:phpmyadmin you will find the new database

2. create table on the new database

```
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root",
  database="MyPythonDatabase"
)
mycursor = mydb.cursor()

mycursor.execute("CREATE TABLE demo (name VARCHAR(255), id INT)")
```

**Note** we added new argument database in the connect function to address specific database.

to check table existence enter the following code to lst all tables in the specified database.

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root",
  database="MyPythonDatabase"
)

mycursor = mydb.cursor()

mycursor.execute("SHOW TABLES")

for x in mycursor:
  print(x) 
```

## Insert statement: python mysql

1. insert one raw

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root",
  database="MyPythonDatabase"
)
mycursor = mydb.cursor()
sql = "INSERT INTO demo (name, id) VALUES (%s, %s)"
val = ("John", "21")
mycursor.execute(sql, val)

mydb.commit()

print(mycursor.rowcount, "record inserted.")
```

2. mulitple raws

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root",
  database="MyPythonDatabase"
)
mycursor = mydb.cursor()

## new syntax

sql = "INSERT INTO demo (name, id) VALUES (%s, %s)"
val = [
  ('Peter', '4'),
  ('Amy', '652'),
  ('Hannah', '21'),
  ('Michael', '345'),
  ('Sandy', '2')
]

mycursor.executemany(sql, val)

mydb.commit()

print(mycursor.rowcount, "was inserted.") 
```

## Select statement: python mysql

Two main keywords:

1. mycursor.fetchone(): to fetch nly one raw from the database from the top of the selected table
2. mycursor.fetchall(): to fetch all records matches the select statement criteria

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root",
  database="MyPythonDatabase"
)
mycursor = mydb.cursor()

mycursor.execute("SELECT * FROM demo")

myresult = mycursor.fetchone()

print(myresult) 
```

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root",
  database="MyPythonDatabase"
)
mycursor = mydb.cursor()

mycursor.execute("SELECT * FROM demo")

myresult = mycursor.fetchall()

for x in myresult:
  print(x)
```

## Update statement: python mysql

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root",
  database="MyPythonDatabase"
)
mycursor = mydb.cursor()

sql = "UPDATE demo SET id = %s WHERE id = %s"
val = ("55", "21")

mycursor.execute(sql, val)

mydb.commit()

print(mycursor.rowcount, "record(s) affected") 

```

## Delete statement: python mysql

```python
import mysql.connector

mydb = mysql.connector.connect(
  host="localhost",
  user="root",
  passwd="root",
  database="MyPythonDatabase"
)
mycursor = mydb.cursor()
sql = "DELETE FROM demo WHERE id = %s"
id = ("55", )

mycursor.execute(sql, id)

mydb.commit()

print(mycursor.rowcount, "record(s) deleted") 
```

**Note you can try all what you have learns in mysql tutorials to find out the differences**

## Python server

Now we need a running server to recieve user request using jason and send back resulted jason file.

First, wee need to install python server. recommended flask
```
conda install -c anaconda flask 
or 
pip install -u flask
```

### to make sure of the installation run the following code
```python
from flask import Flask
app = Flask(__name__)

@app.route('/')
def home():
   return ('Home')

if __name__ == '__main__':
   app.run(host='127.0.0.1', port=80)
```

now open your browser and write 127.0.0.1:80

### Lets send out demo data from server to the browser

```python
from flask import Flask
import mysql.connector

app = Flask(__name__)

@app.route('/')
def home():
   return ('Home')

@app.route('/select')
def select():
   mydb = mysql.connector.connect(
   host="localhost",
   user="root",
   passwd="root",
   database="sben2302"
   )
   mycursor = mydb.cursor()

   mycursor.execute("SELECT * FROM demo")
   row_headers=[x[0] for x in mycursor.description] #this will extract row headers

   myresult = mycursor.fetchall()
   return (str(myresult))
if __name__ == '__main__':
   app.run(host='127.0.0.1', port=80)
```

Moreover next class ISA.
