
Start mysql in cmd:
```js
mysql -u root -p
```

for import file in mysql database:
```js
mysql -u root -p patient < patients.sql
```

Show Databases:
```js
show databases;
```

Create Database:
```js
create database student;
```

Delete Databases:
```js
DROP DATABASE student;
```

Use Database:
```js
use student
```
show table:
```js
show tables;
```

Create tables:
```js
create table students(
    -> name varchar(255),
    -> email varchar(50),
    -> code varchar(10),
    -> batch varchar(30)
    -> );
```

Describe table:
```js
 describe students;
```

Create table data of students:
```js
INSERT into students (name, email, code, batch)
    -> VALUES ("Satya", "satya_pw1_125@masai.school", "pw1_125", "ptweb-1");
```

Show table Data students:
```js
select name from students;

select name, email from students;
```

Delete Table students:
```js
DROP TABLE students;
```

Reset Table Data: or Delete table Data:
```js
TRUNCATE TABLE students;
```

Create table data students:
```js
INSERT into students (name, email, code, batch)
    -> VALUES ("Satya", "satya_pw1_125@masai.school", "pw1_125", "ptweb-1");
```

Show table Data Students:
```js
select name from students;

select name, email from students;
```

Use database patient:
```js
use patient;
```
create table Patients:
```js
create table patients(
   ---------------------
);
```
show Tables:
```js
show tables;
```

Describe Patients:
```js
describe patients;
```

use table data of patients:
```js
select patient_name from patients where age = 25;

select patient_name, age from patients where age = 25;

select count(*) from patients;

select count(*) from patients where age=24;

select count(*) from patients where gender="Male";

select count(*) from patients where gender="Male" and age=25;

select count(*) from patients where age=24 or age=23;

select count(*) from patients where age in (24,25);

select count(*) from patients where age != 25;

select count(*) from patients where age between 22 and 25;

select count(*) from patients where age>=25;
select count(*) from patients where age>25;

select count(*) from patients where age<=25;
select count(*) from patients where age<25;

select * from patients where gender= "Male" order by weight desc;

select patient_name, weight from patients where gender= "Male" order by weight desc;

select patient_name, weight from patients where gender= "Male" order by weight asc;

select patient_name, weight from patients limit 10;

select patient_name, weight from patients order by weight desc limit 10;

select patient_name, weight from patients order by weight desc, patient_name asc limit 10;

select patient_name, weight from patients order by weight desc, patient_name asc limit 10, 10;
// first 10 offset and next 10 limit; means skip 10 and next 10 limit;

select SUM(age) from patients;

select AVG(age) from patients;

select AVG(age) from patients where gender="Female";

select AVG(age) from patients where gender="Male";

select patient_name from patients where patient_name like "A%" limit 10;

select patient_name from patients where patient_name like "A%";

select patient_name from patients where patient_name like "%A" limit 10;

select patient_name from patients where patient_name like "%A_" limit 10;

select patient_name from patients where patient_name like "_A%" limit 10;

select patient_name from patients where patient_name like "%ll%" limit 10;

select distinct severity from patients;

select distinct cond_id from patients;

select count(distinct cond_id) from patients;

select (weight/height*height) AS bmi from patients;

select (weight/height*height) AS bmi from patients limit 10;

select patient_name, (weight/height*height) AS bmi from patients limit 10;

select patient_name, (weight/height*height) AS bmi from patients order by bmi limit 10;

select patient_name, (weight/height*height) AS bmi from patients order by bmi desc limit 10;

select patient_name, (weight/height*height) as bmi, weight, height from patients order by bmi desc limit 10;

select patient_name, (weight/(height*height)) as bmi, weight, height from patients order by bmi desc limit 10;
// this is correct values;

select patient_id, patient_name, (weight/(height*height)) as bmi, weight, height from patients order by bmi desc limit 10;
```

Update table data of patients:
```js
update patients set height = 155 where patient_id = 0;
```

Show table data patients:
```js
select patient_id, patient_name, (weight/((height/100)*(height/100))) as bmi, weight, height from patients order by bmi desc limit 10;

select min(age) from patients;

select max(age) from patients;
```

Use database patient and it's data:
```js
use patient;

select count(*) from patients GROUP BY severity; 

select severity, count(*) from patients GROUP BY severity; 

select severity, count(*) as counts from patients GROUP BY severity; 

select severity, count(*) as counts from patients GROUP BY severity HAVING counts > 140; 

select severity, count(*) as counts from (select * from patients where age > 25) as pat group by severity; 

select severity, cond_id, count(*) as counts from patients group by severity, cond_id; 

select * from (select severity, cond_id, count(*) as counts from patients group by severity, cond_id) as main order by counts;

```

Create table of Users:
```js
create table users (
    -> id int NOT NULL AUTO_INCREMENT,
    -> name varchar(255) NOT NULL,
    -> code varchar(20),
    -> PRIMARY KEY (id)
    -> );
```