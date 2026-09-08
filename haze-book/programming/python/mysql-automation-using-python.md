---
description: >-
  Here’s a basic guide for automating MySQL operations using Python with the
  mysql-connector-python library.
icon: python
---

# MySQL: Automation

## Introduction

This section will explain how to automate CRUD operations in MySQL using Python.

Requirements:

* Python installed
* `mysql-connector-python` library (`pip install mysql-connector-python`)
* MySQL Server running

## Setup

Install the required library:

```
pip install mysql-connector-python
```

Connect to the MySQL database using Python:

```python
import mysql.connector

# Database connection
conn = mysql.connector.connect(
    host="localhost",
    user="root",
    password="your_password",
    database="your_database"
)

cursor = conn.cursor()
```

## MySQL Operation

### CREATE

Create a new table:

```python
create_table_query = """
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100),
    email VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
)
"""
cursor.execute(create_table_query)
conn.commit()
```

Insert data into the table:

```python
insert_data_query = """
INSERT INTO users (username, email)
VALUES (%s, %s)
"""
values = ("john_doe", "john@example.com")
cursor.execute(insert_data_query, values)
conn.commit()
```

### READ

Fetch all records from the table:

```python
select_query = "SELECT * FROM users"
cursor.execute(select_query)

# Fetch and print all rows
rows = cursor.fetchall()
for row in rows:
    print(row)
```

Fetch specific records:

```python
select_where_query = "SELECT * FROM users WHERE username = %s"
username = ("john_doe",)
cursor.execute(select_where_query, username)

row = cursor.fetchone()
print(row)

```

### UPDATE

Update data in the table:

```python
update_query = """
UPDATE users
SET email = %s
WHERE username = %s
"""
values = ("new_email@example.com", "john_doe")
cursor.execute(update_query, values)
conn.commit()
```

### DELETE

Delete a record from the table:

```python
delete_query = "DELETE FROM users WHERE username = %s"
username = ("john_doe",)
cursor.execute(delete_query, username)
conn.commit()
```

## Close Connection

```python
cursor.close()
conn.close()
```

## Full Script

```python
import mysql.connector

# Database connection
conn = mysql.connector.connect(
    host="localhost",
    user="root",
    password="your_password",
    database="your_database"
)
cursor = conn.cursor()

# Create table
create_table_query = """
CREATE TABLE IF NOT EXISTS users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100),
    email VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
)
"""
cursor.execute(create_table_query)
conn.commit()

# Insert data
insert_data_query = "INSERT INTO users (username, email) VALUES (%s, %s)"
values = ("john_doe", "john@example.com")
cursor.execute(insert_data_query, values)
conn.commit()

# Read data
select_query = "SELECT * FROM users"
cursor.execute(select_query)
rows = cursor.fetchall()
for row in rows:
    print(row)

# Update data
update_query = "UPDATE users SET email = %s WHERE username = %s"
values = ("new_email@example.com", "john_doe")
cursor.execute(update_query, values)
conn.commit()

# Delete data
delete_query = "DELETE FROM users WHERE username = %s"
username = ("john_doe",)
cursor.execute(delete_query, username)
conn.commit()

# Close connection
cursor.close()
conn.close()
```

## Best Practices

* Use **prepared statements** to avoid SQL injection.
* Always handle **exceptions** for better error handling in production scripts.
* Make use of connection pooling for better performance when dealing with frequent database operations.
