## DATABASE2 MySQL - 15.관계형데이터베이스의 필요성
- 데이터가 중복해서 등장하는 경우, 데이터 중복이 천만개 정도라면?=> 개선할 것이 있다.
- 중간에 +라도 끼워 넣으려 한다면? 각 데이터들이 데이터가 많다면?
- 트레이드 오프: 장점이 생기면 단점이 생기기 마련..
- 테이블을 두개로 쪼갤 경우, 하나를 찾기위해 다른 테이블을 한번 더 봐야함.
### 데이터를 별도의 테이블로 보관함으로써, 중복을 발생시키지 않으면서, 데이터를 볼 때는 하나의 테이블로 합쳐지게 볼 수 있게

## DATABASE2 MYSQL 16.테이블 분리
- topic테이블을 topic, author 로 분할하고 두가지를 하나로 합치는 join을 살펴보자.

## DATABASE MYSQL 17. JOIN
- JOIN을 통해서 서로 각각 독립적인 분리된 테이블을, 읽을 때 마치 그 테이블이 마치 하나의 테이블로 저장되 있었던 것처럼 만들 수 있다.
- author id의 값과 같은 값을 가지고 있는, author 테이블에 있는 행을 가져와서 topic 테이블에 붙여.
- 내가 author_id만 있을 때 cmnt만 보고 누구의 아이디인지 알 수 있을 까?
- Select*From comment LEFT JOIN author ON comment.author_id = author.id;
- 관계형 데이터베이스를 관계형 데이터베이스 답게 하는 
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

-17.join

```sql
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

mysql>
mysql>
mysql> select*from topic LEFT JOIN author;
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near '' at line 1
mysql> select*from topic LEFT JOIN author on topic.author_id = author.id;
+----+------------+-------------------+---------------------+-----------+------+--------+---------------------------+
| id | title      | description       | created             | author_id | id   | name   | profile                   |
+----+------------+-------------------+---------------------+-----------+------+--------+---------------------------+
|  1 | MySQL      | MySQL is...       | 2018-01-01 12:10:11 |         1 |    1 | egoing | developer                 |
|  2 | Oracle     | Oracle is...      | 2018-01-03 13:01:10 |         1 |    1 | egoing | developer                 |
|  3 | SQL Server | SQL Server is ... | 2018-01-20 11:01:10 |         2 |    2 | duru   | data administrator        |
|  4 | PostgreSQL | PostgreSQL is ... | 2018-01-23 01:03:03 |         3 |    3 | taeho  | data scientist, developer |
|  5 | MongoDB    | MongoDB is ...    | 2018-01-30 12:31:03 |         1 |    1 | egoing | developer                 |
+----+------------+-------------------+---------------------+-----------+------+--------+---------------------------+
5 rows in set (0.00 sec)

mysql> select id, title, description, created, name, profile from topic LEFT JOIN author on topic.author_id = author.id;
ERROR 1052 (23000): Column 'id' in field list is ambiguous
mysql> select topic.id, title, description, created, name, profile from topic LEFT JOIN author on topic.author_id = author.id;
+----+------------+-------------------+---------------------+--------+---------------------------+
| id | title      | description       | created             | name   | profile                   |
+----+------------+-------------------+---------------------+--------+---------------------------+
|  1 | MySQL      | MySQL is...       | 2018-01-01 12:10:11 | egoing | developer                 |
|  2 | Oracle     | Oracle is...      | 2018-01-03 13:01:10 | egoing | developer                 |
|  3 | SQL Server | SQL Server is ... | 2018-01-20 11:01:10 | duru   | data administrator        |
|  4 | PostgreSQL | PostgreSQL is ... | 2018-01-23 01:03:03 | taeho  | data scientist, developer |
|  5 | MongoDB    | MongoDB is ...    | 2018-01-30 12:31:03 | egoing | developer                 |
+----+------------+-------------------+---------------------+--------+---------------------------+
5 rows in set (0.00 sec)

mysql> select topic.id AS topic_id, title, description, created, name, profile from topic LEFT JOIN author on topic.author_id = author.id;
+----------+------------+-------------------+---------------------+--------+---------------------------+
| topic_id | title      | description       | created             | name   | profile                   |
+----------+------------+-------------------+---------------------+--------+---------------------------+
|        1 | MySQL      | MySQL is...       | 2018-01-01 12:10:11 | egoing | developer                 |
|        2 | Oracle     | Oracle is...      | 2018-01-03 13:01:10 | egoing | developer                 |
|        3 | SQL Server | SQL Server is ... | 2018-01-20 11:01:10 | duru   | data administrator        |
|        4 | PostgreSQL | PostgreSQL is ... | 2018-01-23 01:03:03 | taeho  | data scientist, developer |
|        5 | MongoDB    | MongoDB is ...    | 2018-01-30 12:31:03 | egoing | developer                 |
+----------+------------+-------------------+---------------------+--------+---------------------------+
5 rows in set (0.00 sec)

mysql> update author set profile='database administrator' WHERE id=2;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> select*from author;
+----+--------+---------------------------+
| id | name   | profile                   |
+----+--------+---------------------------+
|  1 | egoing | developer                 |
|  2 | duru   | database administrator    |
|  3 | taeho  | data scientist, developer |
+----+--------+---------------------------+
3 rows in set (0.00 sec)
```





## 동영상 링크
[DATABASE2 MySQL - 15.관계형데이터베이스의 필요성](https://www.youtube.com/watch?v=-w1vJgslUG0&list=PLuHgQVnccGMCgrP_9HL3dAcvdt8qOZxjW&index=21)  
[DATABASE2 MySQL - 16.테이블 분리하기](https://www.youtube.com/watch?v=LeTeb3ImxI0&list=PLuHgQVnccGMCgrP_9HL3dAcvdt8qOZxjW&index=22)  
[DATABASE2 MySQL - 17.JOIN](https://www.youtube.com/watch?v=q0UHWaDRwlk&list=PLuHgQVnccGMCgrP_9HL3dAcvdt8qOZxjW&index=24&t=0s)
