# MySQL

## 了解MySQL

### 什么是数据库？

数据库是一个以某种有组织的方式存储的数据集合。理解数据库的一种最简单的办法是将其想象为一个文件柜。此文件柜是一个存放数据的物理位置，不管数据是什么以及如何组织的。保存有组织的数据的容器（通常是一个文件或一组文件）

### 数据库表

你将资料放入自己的文件柜时，并不是随便将它们扔进某个抽屉就完事了，而是在文件柜中创建文件，然后将相关的资料放入特定的文件中。在数据库领域中，这种文件称为表。表是一种结构化的文件，可用来存储某种特定类型的数据。表可以保存顾客清单、产品目录，或者其他信息清单。（某种特定类型数据的结构化清单）

### 列和数据类型

列：表中的一个字段。所有表都是由一个或多个列组成的。

数据类型（datatype）： 所容许的数据的类型。每个表列都有相
应的数据类型，它限制（或容许）该列中存储的数据。

### 行

表中的数据是按行存储的，所保存的每个记录存储在自己的行内。

### 主键

一列（或一组列），其值能够唯一区分表中每个行。

主键用来表示一个特定的行。没有主键，更新或删除表中特定行很困难。

主键满足以下条件：
*任意两行都不具有相同的主键值；
*每个行都必须具有一个主键值（主键列不允许NULL值）。

## 什么是SQL

是结构化查询语言（Structured Query Language）的缩写。SQL是一种专门用来与数据库通信的语言。

### SQL的分类

#### 数据库定义语言DDL

Data Defintion Language

用于定义不同的数据对象、数据库、表、列、索引等。常用的语句关键字包括create、drop、alter等

#### 数据操作语言DML 

Data Manipulation Language

数据操纵语句，用于添加、删除、更新和查询数据库记录，并检查数据的完整性。常用的语句关键字主要包括insert、delete、update和select等。（DML:添加，修改，删除，DQL:查询 记录）

#### 数据控制语言DCL

DCL， Data Control Language

数据控制语句，用于控制不同数据段直接的许可和访问级别的语句。这些语句定义了数据库、表、字段、用户的访问权限和安全级别。主要的语句关键字包括grant、revoke等。

### 启动MySQL服务

win+R，CMD，以管理员身份运行dos

#### 启动MySQL

`net start mysql`

#### 停止MySQL

`net stop mysql`

#### 客户端连接MySQL

`mysql -uroot -p123456`（-p后面跟密码）

### DDL数据定义语言-数据库

#### 查询所有的数据库

`show databases;`

#### 显示所有的数据表

`show tables;`

#### 创建数据库

`create database cao;`

#### 在创建数据库指定编码

`create database cao default character set utf8;`

#### 使用数据库

`use cao;`

#### 删除数据库

`drop database cao;`

### DDL数据定义语言-数据表

#### 创建数据表

在创建表的提前下，必须使用某一个数据库

`use cao;`

`CREATE TABLE t_student(
	username VARCHAR(32),
	PASSWORD VARCHAR(32),
	age INT(3),
	salary DOUBLE(8,2)
);`

#### 删除数据表

`drop table t_student;`

#### 修改表名

`alter table t_student rename student; `

#### 查看表的结构

`desc t_student;`

### DDL---数据库字段操作

#### 修改字段类型

alter table 表名 modify 字段名 varchar(20);

`ALTER TABLE t_student MODIFY username VARCHAR(20);`

#### 修改表字段名

alter table 表名 change 字段原名 字段新名 字段类型;

`ALTER TABLE t_student CHANGE PASSWORD `passWord` VARCHAR(30);` 

#### 增加表字段

alter table 表名 add column 字段名 类型;

`ALTER TABLE t_student ADD COLUMN class VARCHAR(20);`

#### 删除表字段

alter table 表名 drop column 字段名;

`ALTER TABLE t_student DROP COLUMN class;`









