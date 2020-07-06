		

mysql> create database pxpx;
Query OK, 1 row affected (0.03 sec)

mysql> show databases
    -> show databases;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'show databases' at line 2
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| pxpx               |
| sys                |
+--------------------+
5 rows in set (0.06 sec)

mysql> show tables
    -> show tables;
ERROR 1046 (3D000): No database selected
mysql> create table topic;
ERROR 1046 (3D000): No database selected
mysql> use pxpx;
Database changed
mysql> create table topic;
ERROR 1113 (42000): A table must have at least 1 column
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| pxpx               |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

mysql> show tables;
Empty set (0.02 sec)

mysql> create table topic;
ERROR 1113 (42000): A table must have at least 1 column
mysql> create table topic(
    -> id INT(11) NOT NULL AUTO_INCREMENT,
    -> title VARCHAR(100) not null,
    -> description TEXT NULL,
    -> create datetime not null,
    -> author varchar(30) null,
    -> profile varchar(100) null
    -> , primary key(id));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'create datetime not null,
author varchar(30) null,
profile varchar(100) null
, p' at line 5
mysql> , primary key(id));
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near ', primary key(id))' at line 1
mysql> CREATE TABLE topic(
    -> id INT(11) NOT NULL AUTO_INCREMENT,
    -> title VARCHAR(100) NOT NULL,
    -> description TEXT NULL,
    -> created DATETIME NOT NULL,
    -> author VARCHAR(30) NULL,
    -> profile VARCHAR(100) NULL,
    -> PRIMARY KEY(id));
Query OK, 0 rows affected, 1 warning (0.08 sec)

mysql> use pxpx;
Database changed
mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| pxpx               |
| sys                |
+--------------------+
5 rows in set (0.00 sec)

mysql> SHOW TABLES;
+----------------+
| Tables_in_pxpx |
+----------------+
| topic          |
+----------------+
1 row in set (0.00 sec)

mysql> DESC topic;
+-------------+--------------+------+-----+---------+----------------+
| Field       | Type         | Null | Key | Default | Extra          |
+-------------+--------------+------+-----+---------+----------------+
| id          | int          | NO   | PRI | NULL    | auto_increment |
| title       | varchar(100) | NO   |     | NULL    |                |
| description | text         | YES  |     | NULL    |                |
| created     | datetime     | NO   |     | NULL    |                |
| author      | varchar(30)  | YES  |     | NULL    |                |
| profile     | varchar(100) | YES  |     | NULL    |                |
+-------------+--------------+------+-----+---------+----------------+
6 rows in set (0.01 sec)

mysql> INSERT INTO topic(title,description,created,author,profile) VALUES('MySQL','MySQL is...',now(), 'JAEHOON', 'developer');
Query OK, 1 row affected (0.02 sec)

mysql> SELECT FROM topic;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'FROM topic' at line 1
mysql> Select*from topic;
+----+-------+-------------+---------------------+---------+-----------+
| id | title | description | created             | author  | profile   |
+----+-------+-------------+---------------------+---------+-----------+
|  1 | MySQL | MySQL is... | 2020-07-06 17:48:24 | JAEHOON | developer |
+----+-------+-------------+---------------------+---------+-----------+
1 row in set (0.00 sec)

mysql> INSERT INTO topic(title,description,created,author,profile) VALUES('Oracle','Oracle is...',now(), 'JAEHOON', 'developer');
Query OK, 1 row affected (0.01 sec)

mysql> Select*from topic;
+----+--------+--------------+---------------------+---------+-----------+
| id | title  | description  | created             | author  | profile   |
+----+--------+--------------+---------------------+---------+-----------+
|  1 | MySQL  | MySQL is...  | 2020-07-06 17:48:24 | JAEHOON | developer |
|  2 | Oracle | Oracle is... | 2020-07-06 17:51:29 | JAEHOON | developer |
+----+--------+--------------+---------------------+---------+-----------+
2 rows in set (0.00 sec)

mysql> INSERT INTO topic(title,description,created,author,profile) VALUES('SQL Server','SQL Server is...',now(), 'duru','data administrator');
Query OK, 1 row affected (0.01 sec)

mysql> INSERT INTO topic(title,description,created,author,profile) VALUES('Postgre SQL','Postgre SQL is...',now(), 'taeho','data scientist, developer');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO topic(title,description,created,author,profile) VALUES('MongoDB','MongoDB is...',now(), 'JAEHOON',' developer');
Query OK, 1 row affected (0.01 sec)

mysql> Select*from topic;
+----+-------------+-------------------+---------------------+---------+---------------------------+
| id | title       | description       | created             | author  | profile                   |
+----+-------------+-------------------+---------------------+---------+---------------------------+
|  1 | MySQL       | MySQL is...       | 2020-07-06 17:48:24 | JAEHOON | developer                 |
|  2 | Oracle      | Oracle is...      | 2020-07-06 17:51:29 | JAEHOON | developer                 |
|  3 | SQL Server  | SQL Server is...  | 2020-07-06 17:54:16 | duru    | data administrator        |
|  4 | Postgre SQL | Postgre SQL is... | 2020-07-06 17:55:21 | taeho   | data scientist, developer |
|  5 | MongoDB     | MongoDB is...     | 2020-07-06 17:56:20 | JAEHOON |  developer                |
+----+-------------+-------------------+---------------------+---------+---------------------------+
5 rows in set (0.00 sec)
		


##DATABASE2 MySQL - 8.2���̺��� ����

VARCHAR (�ؽ�Ʈ ǥ��)
DATETIME (��¥�ͽð� ��� ǥ��)
primary key (���ɰ� �ߺ��� ���Ѵ�) -Ex. DB2�� �ۼ��ϴµ� id���� �ߺ��Ǹ� �ȵǰ� �� �� ����
You must reset your password ������, Error1820 �˻��ؼ� �ذ��϶�.
DATABASE2 MySQL - 9.CRUD
create read�� �߿�
DATABASE2 MySQL - 10.INSERT
