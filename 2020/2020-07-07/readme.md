## DATABASE2 MySQL - 11.SELECT
- 모든 데이터를 화면에 출력하고 싶다.
- mysql> SELECT id, title, created, author FROM topic; => 적혀지지 않은 것들은 보이지 않는다.
- WHERE - 데이터 값이 JAEHOON인 값만 보고 싶다. FROM다음
- SELECT id, title, created, author FROM topic WHERE author = 'JAEHOON';
- ORDER BY => 정렬기능, mysql> SELECT id, title, created, author FROM topic WHERE author = 'JAEHOON' ORDER BY id DESC;
  (토픽으로부터 저자 "jaehoon"이 포함한 데이터를 descending (오름차순)으로 보여달라.
- 스프레트 시트는 65,000개의 데이터를 넣을 수 있는데, 데이터베이스는 10억건 정도 뽑아낼 수 있는데, 이때 slct from topic 하면 컴퓨터 맛감ㅁ.
- LIMIT =>mysql> SELECT id, title, created, author FROM topic WHERE author = 'JAEHOON' ORDER BY id DESC LIMIT 2;
  (제한된 것만 볼 수 있게)
- 수련이 필요함 .. CRUD 중 Read의 영역.

## DATABASE2 MySQL - 12.UPDATE 
- 수정은 어떻게 할까?
- sql update mysql 검색
- UPDATE topic SET description='ORACLE is...', title='Oracle' where id=2;
  (본래 Oracle=> ORACLE로 업데이트, 제목이 오라클인, 아이디 2 에서만)
- *where문을 빠뜨리는 순간 재앙이 닥친다...

## DATABASE2 MySQL - 13.DELETE
- SQL delete in mySQL
- DELETE FROM topic WHERE id = 5;
  (id 5인mongoDB를 삭제한다.)
- DELETE 잘못하면 인생이 뒤바뀐다...

## DATABASE2 MySQL - 14.수업의 정상
- 혁신innovaion과 본질essence을 원심분리
- essence: Database (CRUD)
- innovation: Relational
- 교양이라면 경제적인 공부라면 여기까지야.....
- 멈출 수 없는 분들은 RDB는 왜 다른 데이터베이스와 구분되는가? => Relaational의 의미는?
- 어려워도 잘해보자....


'''sql
mysql> desc topic;
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

mysql> SELECT*FROM topic;
Empty set (0.00 sec)

mysql>  INSERT INTO topic(title,description,created,author,profile) VALUES('MySQL','MySQL is...',now(), 'JAEHOON', 'developer');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO topic(title,description,created,author,profile) VALUES('Oracle','Oracle is...',now(), 'JAEHOON', 'developer');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO topic(title,description,created,author,profile) VALUES('SQL Server','SQL Server is...',now(), 'duru','data administrator');
Query OK, 1 row affected (0.00 sec)

mysql> INSERT INTO topic(title,description,created,author,profile) VALUES('Postgre SQL','Postgre SQL is...',now(), 'taeho','data scientist, developer');
Query OK, 1 row affected (0.00 sec)

mysql> NSERT INTO topic(title,description,created,author,profile) VALUES('MongoDB','MongoDB is...',now(), 'JAEHOON',' developer');
ERROR 1064 (42000): You have an error in your SQL syntax; check the manual that corresponds to your MySQL server version for the right syntax to use near 'NSERT INTO topic(title,description,created,author,profile) VALUES('MongoDB','Mon' at line 1
mysql>  INSERT INTO topic(title,description,created,author,profile) VALUES('MongoDB','MongoDB is...',now(), 'JAEHOON',' developer');
Query OK, 1 row affected (0.00 sec)

mysql> Select*from topic;
+----+-------------+-------------------+---------------------+---------+---------------------------+
| id | title       | description       | created             | author  | profile                   |
+----+-------------+-------------------+---------------------+---------+---------------------------+
|  1 | MySQL       | MySQL is...       | 2020-07-07 14:22:13 | JAEHOON | developer                 |
|  2 | Oracle      | Oracle is...      | 2020-07-07 14:22:22 | JAEHOON | developer                 |
|  3 | SQL Server  | SQL Server is...  | 2020-07-07 14:22:40 | duru    | data administrator        |
|  4 | Postgre SQL | Postgre SQL is... | 2020-07-07 14:22:47 | taeho   | data scientist, developer |
|  5 | MongoDB     | MongoDB is...     | 2020-07-07 14:23:20 | JAEHOON |  developer                |
+----+-------------+-------------------+---------------------+---------+---------------------------+
5 rows in set (0.00 sec)

mysql> select*from topic;
+----+-------------+-------------------+---------------------+---------+---------------------------+
| id | title       | description       | created             | author  | profile                   |
+----+-------------+-------------------+---------------------+---------+---------------------------+
|  1 | MySQL       | MySQL is...       | 2020-07-07 14:22:13 | JAEHOON | developer                 |
|  2 | Oracle      | Oracle is...      | 2020-07-07 14:22:22 | JAEHOON | developer                 |
|  3 | SQL Server  | SQL Server is...  | 2020-07-07 14:22:40 | duru    | data administrator        |
|  4 | Postgre SQL | Postgre SQL is... | 2020-07-07 14:22:47 | taeho   | data scientist, developer |
|  5 | MongoDB     | MongoDB is...     | 2020-07-07 14:23:20 | JAEHOON |  developer                |
+----+-------------+-------------------+---------------------+---------+---------------------------+
5 rows in set (0.00 sec)

mysql> SELECT id, title, created, author FROM topic;
+----+-------------+---------------------+---------+
| id | title       | created             | author  |
+----+-------------+---------------------+---------+
|  1 | MySQL       | 2020-07-07 14:22:13 | JAEHOON |
|  2 | Oracle      | 2020-07-07 14:22:22 | JAEHOON |
|  3 | SQL Server  | 2020-07-07 14:22:40 | duru    |
|  4 | Postgre SQL | 2020-07-07 14:22:47 | taeho   |
|  5 | MongoDB     | 2020-07-07 14:23:20 | JAEHOON |
+----+-------------+---------------------+---------+
5 rows in set (0.00 sec)

mysql> select "JAEHOON";
+---------+
| JAEHOON |
+---------+
| JAEHOON |
+---------+
1 row in set (0.00 sec)

mysql> select "JAEHOON", 1+1;
+---------+-----+
| JAEHOON | 1+1 |
+---------+-----+
| JAEHOON |   2 |
+---------+-----+
1 row in set (0.00 sec)

mysql> SELECT id, title, created, author FROM topic;
+----+-------------+---------------------+---------+
| id | title       | created             | author  |
+----+-------------+---------------------+---------+
|  1 | MySQL       | 2020-07-07 14:22:13 | JAEHOON |
|  2 | Oracle      | 2020-07-07 14:22:22 | JAEHOON |
|  3 | SQL Server  | 2020-07-07 14:22:40 | duru    |
|  4 | Postgre SQL | 2020-07-07 14:22:47 | taeho   |
|  5 | MongoDB     | 2020-07-07 14:23:20 | JAEHOON |
+----+-------------+---------------------+---------+
5 rows in set (0.00 sec)

mysql> SELECT id, title, created, author FROM topic WHERE author = 'JAEHOON';
+----+---------+---------------------+---------+
| id | title   | created             | author  |
+----+---------+---------------------+---------+
|  1 | MySQL   | 2020-07-07 14:22:13 | JAEHOON |
|  2 | Oracle  | 2020-07-07 14:22:22 | JAEHOON |
|  5 | MongoDB | 2020-07-07 14:23:20 | JAEHOON |
+----+---------+---------------------+---------+
3 rows in set (0.00 sec)

mysql> SELECT id, title, created, author FROM topic WHERE author = 'JAEHOON' ORDER BY id DESC;
+----+---------+---------------------+---------+
| id | title   | created             | author  |
+----+---------+---------------------+---------+
|  5 | MongoDB | 2020-07-07 14:23:20 | JAEHOON |
|  2 | Oracle  | 2020-07-07 14:22:22 | JAEHOON |
|  1 | MySQL   | 2020-07-07 14:22:13 | JAEHOON |
+----+---------+---------------------+---------+
3 rows in set (0.00 sec)

mysql> SELECT id, title, created, author FROM topic WHERE author = 'JAEHOON' ORDER BY id DESC LIMIT 2;
+----+---------+---------------------+---------+
| id | title   | created             | author  |
+----+---------+---------------------+---------+
|  5 | MongoDB | 2020-07-07 14:23:20 | JAEHOON |
|  2 | Oracle  | 2020-07-07 14:22:22 | JAEHOON |
+----+---------+---------------------+---------+
2 rows in set (0.00 sec)

mysql> DESC TOPIC;
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

mysql> SELECT*FROM topic;
+----+-------------+-------------------+---------------------+---------+---------------------------+
| id | title       | description       | created             | author  | profile                   |
+----+-------------+-------------------+---------------------+---------+---------------------------+
|  1 | MySQL       | MySQL is...       | 2020-07-07 14:22:13 | JAEHOON | developer                 |
|  2 | Oracle      | Oracle is...      | 2020-07-07 14:22:22 | JAEHOON | developer                 |
|  3 | SQL Server  | SQL Server is...  | 2020-07-07 14:22:40 | duru    | data administrator        |
|  4 | Postgre SQL | Postgre SQL is... | 2020-07-07 14:22:47 | taeho   | data scientist, developer |
|  5 | MongoDB     | MongoDB is...     | 2020-07-07 14:23:20 | JAEHOON |  developer                |
+----+-------------+-------------------+---------------------+---------+---------------------------+
5 rows in set (0.00 sec)

mysql> UPDATE topic SET decription='Oracle is...', title='Oracle' where id=2;
ERROR 1054 (42S22): Unknown column 'decription' in 'field list'
mysql> UPDATE topic SET decription='ORACLE is...', title='Oracle' where id=2;
ERROR 1054 (42S22): Unknown column 'decription' in 'field list'
mysql> UPDATE topic SET description='ORACLE is...', title='Oracle' where id=2;
Query OK, 1 row affected (0.00 sec)
Rows matched: 1  Changed: 1  Warnings: 0

mysql> SELECT*FROM topic;
+----+-------------+-------------------+---------------------+---------+---------------------------+
| id | title       | description       | created             | author  | profile                   |
+----+-------------+-------------------+---------------------+---------+---------------------------+
|  1 | MySQL       | MySQL is...       | 2020-07-07 14:22:13 | JAEHOON | developer                 |
|  2 | Oracle      | ORACLE is...      | 2020-07-07 14:22:22 | JAEHOON | developer                 |
|  3 | SQL Server  | SQL Server is...  | 2020-07-07 14:22:40 | duru    | data administrator        |
|  4 | Postgre SQL | Postgre SQL is... | 2020-07-07 14:22:47 | taeho   | data scientist, developer |
|  5 | MongoDB     | MongoDB is...     | 2020-07-07 14:23:20 | JAEHOON |  developer                |
+----+-------------+-------------------+---------------------+---------+---------------------------+
5 rows in set (0.00 sec)

mysql> DELETE FROM topic WHERE id = 5;
Query OK, 1 row affected (0.00 sec)

mysql> SELECT*FROM topic;
+----+-------------+-------------------+---------------------+---------+---------------------------+
| id | title       | description       | created             | author  | profile                   |
+----+-------------+-------------------+---------------------+---------+---------------------------+
|  1 | MySQL       | MySQL is...       | 2020-07-07 14:22:13 | JAEHOON | developer                 |
|  2 | Oracle      | ORACLE is...      | 2020-07-07 14:22:22 | JAEHOON | developer                 |
|  3 | SQL Server  | SQL Server is...  | 2020-07-07 14:22:40 | duru    | data administrator        |
|  4 | Postgre SQL | Postgre SQL is... | 2020-07-07 14:22:47 | taeho   | data scientist, developer |
+----+-------------+-------------------+---------------------+---------+---------------------------+
4 rows in set (0.00 sec)
'''
