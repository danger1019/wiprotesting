create database training;

/* 
It is used to select the database
*/
use training;

create table employee
(
id int,
name varchar(30),
dept varchar(30),
salary float,
age int
)

insert into employee values(1,'sahin','hr',93000.89,32);

insert into employee(id,name,dept) values (2,'ravi','admin');
insert into employee values(3,'manoj','tester',52000.89,32);
insert into employee values(4,'suraj','developer',46000.89,32);
insert into employee values(5,'ankit','developer',78000.89,26),
							(6,'karan','hr',44000,28);
insert into employee values(7,'mahi','developer',83000,31);

update employee set salary=60000 where id=2;

describe employee;

select * from employee;
/*-------------------------------------------------------------------------------------*/
create table product(
id int,
name varchar(30),
description varchar(30)
);

describe product;

/* adding a column*/
alter table product add column price int;
alter table product add column (quantity int,suppliername varchar(30));

/* rename a column*/
alter table product rename column suppliername to supply_name;

/*dropping a column*/
alter table product drop supply_name;

alter table product modify column description varchar(100);

rename table product to product2;
rename table product1 to product;

drop table product;
truncate table product;
/*--------------------------------------------------------------------------------------*/
select id,name,salary,salary+10000 as bonus,salary/30 as perdaysalary from employee;
/*----------------------------------------------------employee----------------------------------*/
select * from employee where dept ='hr' or dept = 'admin';
select * from employee where dept!='hr';
select * from employee where dept='developer' and age>30;

/*orderby*/
select * from employee order by age asc;
select * from employee order by salary desc;

select * from employee
where dept = 'developer'
order by salary desc;

select count(id) from employee;
select max(salary) from employee;
select dept,count(id) from employee group by dept;
select min(salary) from employee;

select dept from employee group by dept;

