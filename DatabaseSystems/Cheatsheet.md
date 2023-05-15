>[!tip] Users
``` sql
SELECT User, Host from mysql.user;
```


``` sql
CREATE USER 'userName'@'localhost' IDENTIFIED BY 'somePassword';
```

``` sql
GRANT ALL PRIVILEGES ON * . * TO 'userName'@'localhost';
FLUSH PRIVILEGES;
```

``` sql
SHOW GRANTS for 'userName'@'localhost';
```

``` sql
REVOKE ALL PRIVILEGES, GRANT OPTION FROM 'userName'@'localhost';
```

``` sql
DROP USER 'userName'@'localhost';
```
>[!tip] Database
``` sql
SHOW DATABASES;
```

``` sql
DELETE DATABASE somedatabase;
```

``` sql
USE somedatabase
```

>[!tip] Tables
``` sql
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

``` sql
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

``` sql
DROP TABLE tablename
```

``` sql
INSERT INTO users (first_name, last_name, email, password, location, dept, is_admin, register_date) values ('Brad', 'Traversy', 'brad@gmail.com', '123456','Massachusetts', 'development', 1, now());
```

``` sql
INSERT INTO users (first_name, last_name, email, password, location, dept,  is_admin, register_date) values ('Fred', 'Smith', 'fred@gmail.com', '123456', 'New York', 'design', 0, now()), ('Sara', 'Watson', 'sara@gmail.com', '123456', 'New York', 'design', 0, now()),('Will', 'Jackson', 'will@yahoo.com', '123456', 'Rhode Island', 'development', 1, now()),('Paula', 'Johnson', 'paula@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now()),('Tom', 'Spears', 'tom@yahoo.com', '123456', 'Massachusetts', 'sales', 0, now());
```

``` sql
DELETE FROM tablename WHERE id = 6
```

``` sql
UPDATE tablename SET email = 'freddy@gmail.com' WHERE id = 2;
```

``` sql
ALTER TABLE tablename ADD columname VARCHAR(30)
```

``` sql
ALTER TABLE tablename MODIFY COLUMN columname INT
```
### SELECT STATEMENTS

>[!tip] ORDER BY (Sort)

``` sql
SELECT * FROM tableName ORDER by tableName ASC; 
SELECT * FROM tableName ORDER by tableName DESC; 
```

>[!tip] Concat Colloum
``` sql
SELECT CONCAT(first_name, ' ', last_name) AS 'Name', dept FROM users;
```

>[!tip] DISTINCT ROWS
``` sql
SELECT DISTINCT rowName from tableName
```
>[!tip] BETWEEN (SELECT RANGE)
``` sql
SELECT rowName from tableName WHERE rowName BETWEEN 20 and 25; #IF INT
```
>[!tip] LIKE (SEARCHING)
``` sql
SELECT rowName from tableName WHERE rowName like 'd%'
SELECT rowName from tableName WHERE rowName like 'dev%'
SELECT rowName from tableName WHERE rowName like '%t'
SELECT rowName from tableName WHERE rowName like '%e%'
```
>[!tip] NOT LIKE
``` sql
SELECT rowName FROM tableName WHERE rowName NOT LIKE 'd%';
```
>[!tip] IN
``` sql
SELECT * FROM tableName WHERE rowName IN ('design', 'sales');
```
>[!tip] INDEX
``` sql
CREATE INDEX LIndex On users(location);
DROP INDEX LIndex ON users;
```

### JOIN
>[!tip] INNER JOIN
``` sql
SELECT
rowNamesFromBoth
FROM tableName
INNER JOIN posts
ON users.id = posts.user_id
ORDER BY posts.title;
```
>[!tip] LEFTJOIN & RIGHTJOIN
``` sql
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

>[!tip] INNER JOIN
``` sql
SELECT
rowNamesFromBoth
FROM tableName
INNER JOIN tableName on rowName = secondRowName
INNER JOIN tableName on rowName = secondRowName # SHOULD NOT BE THE SAME TABLE
ORDER BY posts.title;
```
Think of inner join as a more specialized natural, where you only get where the on is true, but get all so no squishing of 2 tables

![[Pasted image 20230514131615.png]]

>[!tip] AGGREGATE FUNCTIONS
``` sql
SELECT COUNT(rowName) FROM tableName;
SELECT MAX(rowName) FROM tableName;
SELECT MIN(rowName) FROM tableName;
SELECT SUM(rowName) FROM tableName;
SELECT UCASE(first_name), LCASE(last_name) FROM tableName;
```

``` sql
UCASE = toUpperCase
LCASE = toLowerCase
```

>[!tip] GROUP BY
``` sql
SELECT age, COUNT(age) FROM users GROUP BY age;
SELECT age, COUNT(age) FROM users WHERE age > 20 GROUP BY age;
SELECT age, COUNT(age) FROM users GROUP BY age HAVING count(age) >=2;
```
>[!tip] HAVING 

Having is mostly used with aggrregate functions since they run after the database has been made
``` sql
SELECT _column_name(s)_  
FROM _table_name_  
WHERE _condition_  
GROUP BY _column_name(s)  
_HAVING _condition  
_ORDER BY _column_name(s);_
```

>[!example] Having example
>```
>SELECT COUNT(CustomerID), Country  
>FROM Customers  
>GROUP BY Country  
>HAVING COUNT(CustomerID) > 5  ## Aggragtor function
>ORDER BY COUNT(CustomerID) DESC;
>```


