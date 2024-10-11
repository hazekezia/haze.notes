# MySQL: Basic CRUD Command

These are the essential CRUD commands for MySQL.

Be careful with UPDATE and DELETE operations by using the appropriate WHERE clause to avoid unintended data changes or deletions.

### CREATE

Create table

```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(100),
    email VARCHAR(100),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

Insert data into the table

```sql
INSERT INTO users (username, email) 
VALUES ('john_doe', 'john@example.com');
```

### READ

Select all data from table

```sql
SELECT * FROM users;
```

```sql
SELECT username, email FROM users;
```

Select data with a specific condition

```sql
SELECT * FROM users WHERE username = 'john_doe';
```

Select data with ordering

```sql
SELECT * FROM users ORDER BY created_at DESC;
```

Join data from multiple tables

```sql
SELECT orders.id, users.username 
FROM orders 
JOIN users ON orders.user_id = users.id;
```

### UPDATE

Update data in the table

```sql
UPDATE users 
SET email = 'new_email@example.com' 
WHERE username = 'john_doe';
```

### DELETE

Delete data from the table

```sql
DELETE FROM users 
WHERE username = 'john_doe';
```

Delete all data from the table (use with caution!)

```sql
DELETE FROM users;
```
