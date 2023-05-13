### Users
```
Select User, Host from mysql.user;
```

```
CREATE USER 'userName'@'localhost' IDENTIFIED BY 'somePassword';
```

```
GRANT ALL PRIVILEGES ON * . * TO 'userName'@'localhost';
FLUSH PRIVILEGES;
```

```
SHOW GRANTS for 'userName'@'localhost';
```

```
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'userName'@'localhost';
```

```
DROP USER 'userName'@'localhost';
```
### Database
```
SHOW DATABASES;
```

```
DELETE DATABASE somedatabase;
```

```
USE somedatabase
```
### Tables
```
CREATE TABLE users(
id INT AUTO_INCREMENT,
   first_name VARCHAR(100),
   last_name VARCHAR(100),
   email VARCHAR(50),
   password VARCHAR(20),
   location VARCHAR(100),
   dept VARCHAR(100),
   is_admin TINYINT(1),
   register_date DATETIME,
   PRIMARY KEY(id)
);
```

```
CREATE TABLE posts(
id INT AUTO_INCREMENT,
   user_id INT,
   title VARCHAR(100),
   body TEXT,
   publish_date DATETIME DEFAULT CURRENT_TIMESTAMP,
   PRIMARY KEY(id),
   FOREIGN KEY (user_id) REFERENCES users(id)
);
```

```
DROP TABLE tablename
```

```
INSERT INTO users (first_name, last_name, email, password, location, dept, is_admin, register_date) values ('Brad', 'Traversy', 'brad@gmail.com', '123456','Massachusetts', 'development', 1, now());
```

```
INSERT INTO users (first_name, last_name, email, password, location, dept,  is_admin, register_date) values ('Fred', 'Smith', 'fred@gmail.com', '123456', 'New York', 'design', 0, now()), ('Sara', 'Watson', 'sara@gmail.com', '123456', 'New York', 'design', 0, now()),('Will', 'Jackson', 'will@yahoo.com', '123456', 'Rhode Island', 'development', 1, now()),('Paula', 'Johnson', 'paula@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now()),('Tom', 'Spears', 'tom@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now());
```

```
DELETE FROM tablename WHERE id = 6
```

```
UPDATE tablename SET email = 'freddy@gmail.com' WHERE id = 2;
```

```
ALTER TABLE tablename ADD columname VARCHAR(30)
```

```
ALTER TABLE tablename MODIFY COLUMN columname INT
```
### SELECT STATEMENTS

##### ORDER BY (Sort)

```
SELECT * FROM tableName ORDER by tableName ASC; 
SELECT * FROM tableName ORDER by tableName DESC; 
```

##### CONCAT COLUNM
```
SELECT CONCAT(first_name, ' ', last_name) AS 'Name', dept FROM users;
```
##### DISTINCT ROWS
```
SELECT DISTINCT rowName from tableName
```
##### BETWEEN (SELECT RANGE)
```
SELECT rowName from tableName WHERE rowName BETWEEN 20 and 25; #IF INT
```
##### LIKE (SEARCHING)
```
SELECT rowName from tableName WHERE rowName like 'd%'
SELECT rowName from tableName WHERE rowName like 'dev%'
SELECT rowName from tableName WHERE rowName like '%t'
SELECT rowName from tableName WHERE rowName like '%e%'
```
##### NOT LIKE
```
SELECT rowName FROM tableName WHERE rowName NOT LIKE 'd%';
```
##### IN
```
SELECT * FROM tableName WHERE rowName IN ('design', 'sales');
```
### INDEX
```
CREATE INDEX LIndex On users(location);
DROP INDEX LIndex ON users;
```

### JOIN
##### INNER JOIN
```
SELECT
rowNamesFromBoth
FROM tableName
INNER JOIN posts
ON users.id = posts.user_id
ORDER BY posts.title;
```
##### LEFTJOIN & RIGHTJOIN
```
SELECT
rowNamesFromBoth
FROM tableName
LEFT JOIN rowName ON rowName = secondRowName
ORDER BY rowName;
```
Left outer join
![[Pasted image 20230512165745.png]]
Right outer join
![[Pasted image 20230512165811.png]]
![[Pasted image 20230512165845.png]]

| SN | UNION | JOIN |  
| :------: | :------: | :------: |  
| 1. | Combine the result from multiple tables using SQL queries | Used to fetch the record from more than one table using SQL queries. |   
| 2. | It combines the records into new rows | It combines the records into new columns. |
| 3. | It allows us to connect the tables vertically. | It will enable us to join the tables vertically. |
| 4. | It works as the conjunction of the more than one tables that sum ups all records. | Produces results in the intersection of the tables. |
| 5. | In this, the order and number of the columns must be the same in all tables | In this, the order and number of the columns do not need to be the same in all tables. |
| 6. | It has a default feature to remove the duplicate rows from the result set. | It does not eliminate the duplicate rows from the result set. |
| 7. | In this, the data type must be the same in all SELECT statements. | In this, there is no need to be the same data type. It can be different. |
| 8. | The Union clause is applicable only when the number of columns and corresponding attributes has the same domain. | The Join clause is applicable only when the two tables that are going to be used have at least one column. |
| 9. | The Union clause can have mainly two types that are given as UNION and UNION ALL|  The Join clause can have different types that are given as INNER JOIN, LEFT OUTER JOIN, RIGHT OUTER JOIN, FULL JOIN |

##### INNER JOIN
```
SELECT
rowNamesFromBoth
FROM tableName
INNER JOIN tableName on rowName = secondRowName
INNER JOIN tableName on rowName = secondRowName # SHOULD NOT BE THE SAME TABLE
ORDER BY posts.title;
```
##### AGGREGATE FUNCTIONS
```
SELECT COUNT(rowName) FROM tableName;
SELECT MAX(rowName) FROM tableName;
SELECT MIN(rowName) FROM tableName;
SELECT SUM(rowName) FROM tableName;
SELECT UCASE(first_name), LCASE(last_name) FROM tableName;
```

```
UCASE = toUpperCase
LCASE = toLowerCase
```

##### GROUP BY
```
SELECT age, COUNT(age) FROM users GROUP BY age;
SELECT age, COUNT(age) FROM users WHERE age > 20 GROUP BY age;
SELECT age, COUNT(age) FROM users GROUP BY age HAVING count(age) >=2;
```
