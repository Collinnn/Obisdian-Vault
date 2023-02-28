[[SELECT]]
```
SELECT * from "Tablename"
SELECT ID from "TableName"
Example
SELECT * from student

SELECT CourseID,StudyYear,Grade from takes,student
where studname = "shankar"
and student.studID = takes.studid;

```

Insert takes an entire table row as an input.
```
Select * from section; // Not needed.

insert section values("CS-102",1,"Fall",2009,null,null,null),
```


```
Delete from takes 
where courseID = "CS-102" OR courseID= "CS-103";
```

CREATE TABLE first needs the name afterwords a name for each row followed by type.

```
create table owns(DriverID varchar(5),License varchar(5), primary key(DriverID,License)
, foreign key(DriverID) references Person(DriverID), foreign key(License) references Car(License));

```
[[Like]] is a string matching operator,

```
Like 'Anne'
Like 'Intro%', matches Intro and "introduction"
Like '%duc%', matches anything with the substring duc, example being "introduction"
```

[[NULL]]

[[DISTINICT]]


[[Aggregate Functions]] take duplicate values into effect

[[GROUPBY]]

[[HAVING]]

[[SOME]] IS a type of subquery, that selects on a defined basis inside the some. Atleast one.

[[Union,Intersect,EXCEPT]]

[[JOIN]]

[[Data Types]]

[[Not Null And Primary Key]]

[[Views]]

[[Users]]

[[Rules]]