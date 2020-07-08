##DATABASE2 MySQL - 15.�����������ͺ��̽��� �ʿ伺
- �����Ͱ� �ߺ��ؼ� �����ϴ� ���, ������ �ߺ��� õ���� �������?=> ������ ���� �ִ�.
- �߰��� +�� ���� ������ �Ѵٸ�? �� �����͵��� �����Ͱ� ���ٸ�?
- Ʈ���̵� ����: ������ ����� ������ ����� ����..
- ���̺��� �ΰ��� �ɰ� ���, �ϳ��� ã������ �ٸ� ���̺��� �ѹ� �� ������.
# �����͸� ������ ���̺�� ���������ν�, �ߺ��� �߻���Ű�� �����鼭, �����͸� �� ���� �ϳ��� ���̺�� �������� �� �� �ְ�

##DATABASE2 MYSQL 16.���̺� �и�
- topic���̺��� topic, author �� �����ϰ� �ΰ����� �ϳ��� ��ġ�� join�� ���캸��.

```sql
mysql> select*from topic_backup;
+----+-------------+-------------------+---------------------+---------+---------------------------+
| id | title       | description       | created             | author  | profile                   |
+----+-------------+-------------------+---------------------+---------+---------------------------+
|  1 | MySQL       | MySQL is...       | 2020-07-08 21:01:17 | JAEHOON | developer                 |
|  2 | Oracle      | Oracle is...      | 2020-07-08 21:01:31 | JAEHOON | developer                 |
|  3 | SQL Server  | SQL Server is...  | 2020-07-08 21:01:38 | duru    | data administrator        |
|  4 | Postgre SQL | Postgre SQL is... | 2020-07-08 21:01:59 | taeho   | data scientist, developer |
|  5 | MongoDB     | MongoDB is...     | 2020-07-08 21:02:15 | JAEHOON |  developer                |
+----+-------------+-------------------+---------------------+---------+---------------------------+
5 rows in set (0.00 sec)

mysql> create table topic(
    -> id int(11) not null auto_increment,
    -> title VARCHAR(30) NOT NULL,
    -> description TEXT NULL,
    -> created DATETIME NOT NULL,
    -> author_id int(11) null,
    -> primary key(id)
    -> );
Query OK, 0 rows affected, 2 warnings (0.01 sec)

mysql> desc topic;
+-------------+-------------+------+-----+---------+----------------+
| Field       | Type        | Null | Key | Default | Extra          |
+-------------+-------------+------+-----+---------+----------------+
| id          | int         | NO   | PRI | NULL    | auto_increment |
| title       | varchar(30) | NO   |     | NULL    |                |
| description | text        | YES  |     | NULL    |                |
| created     | datetime    | NO   |     | NULL    |                |
| author_id   | int         | YES  |     | NULL    |                |
+-------------+-------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

mysql> create table author(
    -> id int(11) not null auto_increment,
    -> name VARCHAR(20) NOT NULL,
    -> profile VARCHAR(200) NULL,
    -> PRIMARY KEY(id)
    -> );
Query OK, 0 rows affected, 1 warning (0.01 sec)

mysql> desc author;
+---------+--------------+------+-----+---------+----------------+
| Field   | Type         | Null | Key | Default | Extra          |
+---------+--------------+------+-----+---------+----------------+
| id      | int          | NO   | PRI | NULL    | auto_increment |
| name    | varchar(20)  | NO   |     | NULL    |                |
| profile | varchar(200) | YES  |     | NULL    |                |
+---------+--------------+------+-----+---------+----------------+
3 rows in set (0.00 sec)

mysql> insert into author (id, name, profile) VALUES(1,'egoing','developer');
Query OK, 1 row affected (0.00 sec)

mysql> select*from author;
+----+--------+-----------+
| id | name   | profile   |
+----+--------+-----------+
|  1 | egoing | developer |
+----+--------+-----------+
1 row in set (0.00 sec)

mysql> insert into topic(id, title, description, created, author_id) VALUES(1, 'MySQL', 'MySQL is...','2018-1-1 12:10:11',1);
Query OK, 1 row affected (0.00 sec)

mysql> select*from topic;
+----+-------+-------------+---------------------+-----------+
| id | title | description | created             | author_id |
+----+-------+-------------+---------------------+-----------+
|  1 | MySQL | MySQL is... | 2018-01-01 12:10:11 |         1 |
+----+-------+-------------+---------------------+-----------+
1 row in set (0.00 sec)

mysql> insert into topic(id, title, description, created, author_id) VALUES(2, 'Oracle', 'Oracle is...','2018-01-03 13:01:10',1);
Query OK, 1 row affected (0.00 sec)

mysql> insert into author(id, name, profile)  VALUES(2, 'duru', 'data administrator'); , 'Oracle is...
Query OK, 1 row affected (0.00 sec)

    '> insert into topic(id, title, description, created, author_id) VALUES(3, 'SQL Server', 'SQL Server is...','2018-01-20 11:01:10'.1)

mysql> desc author;
+---------+--------------+------+-----+---------+----------------+
| Field   | Type         | Null | Key | Default | Extra          |
+---------+--------------+------+-----+---------+----------------+
| id      | int          | NO   | PRI | NULL    | auto_increment |
| name    | varchar(20)  | NO   |     | NULL    |                |
| profile | varchar(200) | YES  |     | NULL    |                |
+---------+--------------+------+-----+---------+----------------+
3 rows in set (0.00 sec)

mysql> INSERT INTO `author` VALUES (1,'egoing','developer');
ERROR 1062 (23000): Duplicate entry '1' for key 'author.PRIMARY'
mysql>
mysql> desc topic;
+-------------+-------------+------+-----+---------+----------------+
| Field       | Type        | Null | Key | Default | Extra          |
+-------------+-------------+------+-----+---------+----------------+
| id          | int         | NO   | PRI | NULL    | auto_increment |
| title       | varchar(30) | NO   |     | NULL    |                |
| description | text        | YES  |     | NULL    |                |
| created     | datetime    | NO   |     | NULL    |                |
| author_id   | int         | YES  |     | NULL    |                |
+-------------+-------------+------+-----+---------+----------------+
5 rows in set (0.00 sec)

mysql> desc topic_backup;
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
6 rows in set (0.00 sec)

mysql> INSERT INTO `author` VALUES (3,'taeho','data scientist, developer');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO `topic` VALUES (3,'SQL Server','SQL Server is ...','2018-01-20 11:01:10',2);
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO `topic` VALUES (4,'PostgreSQL','PostgreSQL is ...','2018-01-23 01:03:03',3);
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO `topic` VALUES (5,'MongoDB','MongoDB is ...','2018-01-30 12:31:03',1);
Query OK, 1 row affected (0.00 sec)

mysql> select*from topic;
+----+------------+-------------------+---------------------+-----------+
| id | title      | description       | created             | author_id |
+----+------------+-------------------+---------------------+-----------+
|  1 | MySQL      | MySQL is...       | 2018-01-01 12:10:11 |         1 |
|  2 | Oracle     | Oracle is...      | 2018-01-03 13:01:10 |         1 |
|  3 | SQL Server | SQL Server is ... | 2018-01-20 11:01:10 |         2 |
|  4 | PostgreSQL | PostgreSQL is ... | 2018-01-23 01:03:03 |         3 |
|  5 | MongoDB    | MongoDB is ...    | 2018-01-30 12:31:03 |         1 |
+----+------------+-------------------+---------------------+-----------+
5 rows in set (0.00 sec)

mysql> select*from author;
+----+--------+---------------------------+
| id | name   | profile                   |
+----+--------+---------------------------+
|  1 | egoing | developer                 |
|  2 | duru   | data administrator        |
|  3 | taeho  | data scientist, developer |
+----+--------+---------------------------+
3 rows in set (0.00 sec)
```