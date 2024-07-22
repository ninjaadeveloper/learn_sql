# MySql Query Bank

## xampp

    X - Cross Platform
    A- Apache
    M - MariaDB, MySql
    P - Pearl
    P - PHP


##    DDL (Data Definition Language)
    Create 
    Drop
    Alter 
    Truncate


##   DML (Data Manipulation Language)
    Insert
    Select
    Update
    Delete
    Merge

##    DCL (Data Control Language)
    Grant
    Revoke

##    TCL (Transection Control Language)
    Commit
    Rollback


##  Queries

    mysql -u root -p

    show databases;
    create database db_users;
    use db_users;

    create table tbl_user(user_id int,user_name varchar(50),email varchar(50), age int);
    show tables;

    show columns from tbl_user;

    Insert into tbl_user (id,name,email,age) values (1,'zaki','zaki98@gmail.com',21);

    select * from tbl_user;

    Insert into tbl_user (id,name,email,age) values (2,'hamza','hamza@gmail.com',19);

    Insert into tbl_user (id,name,email,age) values (3,'suleman','suleman@gmail.com',22);

    select * from tbl_user;

    Update tbl_user set name='zaki khan' where id=1;
    
    select * from tbl_user;

    Update tbl_user set name='zaki haider',email='zaki@gmail.com' where id=1;

    select * from tbl_user;

    select name from tbl_user;

    select name,email from tbl_user;

    select *  from tbl_user where id=1

    select *  from tbl_user where email='suleman@gmail.com'

    delete from tbl_user where id=2;

    select * from tbl_user;

    alter table tbl_user change column name user_name varchar(50);

    show columns from tbl_user;

    alter table tbl_user add column gender varchar(25);

    alter table tbl_user drop column age;
    
    alter table tbl_user RENAME new_user;

    show columns from tbl_user;

    select * from new_user;

    TRUNCATE new_user;

    drop table new_user;

    create table user(id int not null unique,name varchar(25) not null,age int not null check (age>18) ,gender varchar(20) default 'M');

    insert into user (id,name,age) value (1,'shehran',19);
    insert into user (id,name,age) value (2,'zaki',19);

    select * from user;
     
    insert into user (id,name,age,gender) value (3,'neha',20,'F');
    
    select * from user;

    create table users(id int not null AUTO_INCREMENT,name varchar(50) not null ,email varchar(50) unique not null,PRIMARY KEY (id));

    show columns from users;

    insert into users (name,email) values ('asad','asad@gmail.com');

    select * from users;

    insert into users (name,email) values ('zaki','zaki@gmail.com');\
    insert into users (name,email) values ('affan','affan@gmail.com');

    select * from users;

    delete from users where id=1;
    
    select * from users;

    insert into users (name,email) values ('asad','asad@gmail.com');
    select * from users;

    insert into users (name,email) values ('hamza','muhammadhamza@gmail.com');
    select * from users;

    delete from users where id=4;
    select * from users;

    insert into users (name,email) values ('huma','huma@gmail.com');
    select * from users;

    create database school;

    use school;
    show tables;

    create table courses (id int primary key auto_increment,course_name varchar(25) not null);
    show columns from courses;

    create table students(id int auto_increment primary key,name varchar(50) not null,courseId int not null,FOREIGN KEY (courseId) REFERENCES courses(id));

    show columns from students;

    insert into courses(course_name) values ('HTML');
    insert into courses(course_name) values ('CSS');
    insert into courses(course_name) values ('JS');

    select * from courses;

    insert into students(name,courseId) values ('Hammad',1);
    insert into students(name,courseId) values ('Hamza',5);

    select * from students;

    insert into students(name,courseId) values ('Zaki',1);
    insert into students(name,courseId) values ('Affan',3);
    insert into students(name,courseId) values ('Mudassir',3);
    
    select * from students;

    delete from courses where id=1;
    delete from courses where id=2;

    delete from students where id=6;
    select * from students;
    delete from courses where id=2;

    SELECT * FROM students JOIN courses on students.courseId = courses.id;
    SELECT students.name,courses.course_name FROM students JOIN courses on students.courseId = courses.id;

    CREATE TABLE cities(id int AUTO_INCREMENT PRIMARY KEY,city_name varchar(25) NOT NULL UNIQUE);
    
    INSERT into cities (city_name) VALUES ('Karachi'), ('Lahore'),('Islamabad')
    SELECT * from cities;

    ALTER TABLE students ADD COLUMN (cityId int,FOREIGN KEY (cityId) REFERENCES cities(id));

    UPDATE students set cityId=3 WHERE students.id = 8;

    SELECT * from students 
    JOIN courses on students.courseId = courses.id 
    JOIN cities on students.cityId = cities.id;

    SELECT * from students 
    LEFT JOIN courses on students.courseId = courses.id
    LEFT JOIN cities on students.cityId = cities.id;

    SELECT * from students 
    RIGHT JOIN courses on students.courseId = courses.id
    RIGHT JOIN cities on students.cityId = cities.id;

    SELECT * from students 
    CROSS JOIN courses on students.courseId = courses.id
    CROSS JOIN cities on students.cityId = cities.id;

    SELECT students.name,courses.course_name from students JOIN courses on students.courseId = courses.id WHERE courses.course_name = 'HTML';

    SELECT students.name,courses.course_name,cities.city_name from students JOIN courses on students.courseId = courses.id JOIN cities on students.cityId = cities.id WHERE courses.course_name = "JS" AND cities.city_name = "Islamabad";

    SELECT students.name,courses.course_name,cities.city_name from students JOIN courses on students.courseId = courses.id JOIN cities on students.cityId = cities.id WHERE courses.course_name = "JS" OR cities.city_name = "Islamabad";

    SELECT students.name,courses.course_name,cities.city_name from students 
    JOIN courses on students.courseId = courses.id
    JOIN cities on students.cityId = cities.id
    WHERE NOT courses.course_name = "HTML";


    INSERT INTO users (name,email,age,salary,city) VALUES
    ('Zaki','zaki@gmail.com',23,50000,'Karachi'),
    ('Bilal','bilal@gmail.com',18,22000,'Hyderabad'),
    ('Affan','ali@gmail.com',22,19000,'Lahore'),
    ('Yawar','yawar@gmail.com',24,30000,'Karachi'),
    ('Daniyal','daniyal@gmail.com',19,25000,'Sukkar'),
    ('Shehran','shehran@gmail.com',20,22000,'Sanghar'),
    ('Mudassir','mudassir@gmail.com',20,100000,'Multan'),
    ('Waqar','waqar@gmail.com',20,20000,'Islamabad'),
    ('hamza','hamza@gmail.com',20,25000,'Karachi'),
    ('usama','usama@gmail.com',20,10000,'Karachi')

    SELECT * FROM `users` WHERE city IN ('Lahore','Karachi','Sanghar','Multan');
    
    SELECT * FROM users WHERE salary BETWEEN 15000 AND 20000;

    SELECT * FROM users WHERE age BETWEEN 17 AND 22;

    SELECT * FROM `users` WHERE name LIKE "a%"; (start)

    SELECT * FROM `users` WHERE name LIKE "%a"; (end)

    SELECT * FROM `users` WHERE name LIKE "%n"; (end)

    SELECT * FROM `users` WHERE name LIKE "%ff%";

    SELECT * FROM `users` WHERE name LIKE "%ra%";

    SELECT * FROM `users` WHERE city LIKE "%h%";

    SELECT * FROM `users` WHERE name LIKE "Z%i";

    SELECT * FROM `users` WHERE name LIKE "_a%"; (2nd posoition)

    SELECT * FROM `users` WHERE name LIKE "__a%"; (3rd posoition)

    SELECT * FROM `users` WHERE name LIKE "%a__";

    SELECT * FROM `users` WHERE name LIKE "__fa%";

    SELECT * FROM `users` ORDER by name DESC;

    SELECT * FROM `users` ORDER by name ASC;

    SELECT name,salary FROM `users` ORDER by salary DESC;


    DELIMITER $$

    CREATE PROCEDURE getUsers()
    BEGIN
    SELECT * from users;
    END $$

    DELIMITER ;

    CALL getUsers(); 



    CREATE PROCEDURE getSingleUsers(userId INT)
    BEGIN
    SELECT * from users where id = userId ;
    END $$ 


    CALL getSingleUsers(5);

    DELIMITER $$
    CREATE PROCEDURE insertUser(
            myname VARCHAR(50),
            myemail VARCHAR(25),
            myage INT,
            mysalary INT,
            mycity VARCHAR(25)
            )
    BEGIN
    INSERT INTO users (users.name,users.email,users.age,users.salary,users.city) VALUES (myname,myemail,myage,mysalary,mycity);
    END$$

    DELIMITER ;

    CALL insertUser('Neha','neha@gmail.com',20,25000,'Karachi');







