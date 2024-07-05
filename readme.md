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


