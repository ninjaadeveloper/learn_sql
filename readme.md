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


