## DATABASE2 MySQL - 6.스키마의 사용
# schema, mySQL 에서 데이터베이스를 만들어 보자.
 - mysql create database 구글에 검색
 - mysql> CREATE DATABASE menagerie;
 -  create database oxox; Query OK, 1 row affected (0.00 sec)
 - 중요한건 검색을 통해서 알아내면 된다. 
 - how to show database list in mysql검색 ㄱㄱ
 - SHOW DATABASES;
 - mysql> SHOW DATABASES;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| oxox               |
| performance_schema |
| sys                |
+--------------------+
5 rows in set (0.00 sec)
 - 저 데이터 베이스를 사용하겠다 =>USE
 - mysql> USE oxox;
Database changed
 - 데이터 베이스 생성까지 했고 표를 다뤄봅시다.

## DATABASE2 MYSQL - 7. SQL과 테이블의 구조
# 데이터베이스는 엄청나게 많은 데이터를 다루기 때문에, 상상력으로 감당해보자구
 - SQL (Structured Query Language)
 - 관계형 데이터베이스가 표의 형식 S
 - 데이터를 넣어줘, 읽어줘, 수정 삭제 스키마를 만들어줘, 요청하는 질의하는=>쿼리,Q
 - 데이터베이스도 이해할 수 있고 나도 이해할 수 있는 언어 => Language
### SQL 컴퓨터 언어의 특징  
 - 어떤 컴퓨터 언어보다 쉽다. (HTML, SQL 둘다 쉽다.)
 - 쉽고 중요하다. SQL은 관계형 데이터베이스라는 카테고리 속의 제품들이 공통적으로 데이터베이스를 제어할 때 사용하는, 표준화된 언어.
 - 표를 본격적으로 다뤄보자.
 - 표: table, x축과 y축으로 쪼개서 생각할 수 있는데 
 - x축(가로) - row , record, 행 , =>row는 데이터 하나하나, 데이터 자체
 - y축(세로) - column, 열 =>컬럼을 얘기할 때는 data의 타입, 데이터의 구조
 - 데이터를 만들고 추가 삭제 하고 해봅시다.

## DATABASE2 MYSQL - 8.1 테이블의 생성
# 테이블 생성 해보자.
 - create table in mysql cheat sheet 검색
 - mysql로그인 
 - 스프레드 시트는 컬럼에 어떤 형태의 데이터를 넣을 수 있다. 데이터베이스에서는 , 반드시 숫자로 들어와야한다. 날짜로 들어와야 한다를 규제를 할 수 있다. (데이터가 매우 많으니까)
 - 장점: 컬럼의 데이터 타입을 강제할 수 있다.  꺼낼 때 신경 쓸 필요가 없다. (반드시 id는 숫자다. 반드시 created 컬럼은 시간이다...)
 - mysql datatype number 검색 (컬럼안의 데이터 입력값을 강제하기 위함)
 - 최대한 자신이 수용하려고 하는 데이터에 최대값에 가장 가까운 데이터 타입 선택이 최적화.
 - not null ( 값이 없는 것은 허용하지 않겠다.)
 - 3번째 행을 삭제하라고 하면, 같은 제목의 컬럼이 같은 제목이 행이 있다면? id값이 3인 것을 삭제해. 
 - 데이터를 추가할 때, 마지막 아이디보다 +1인 값을 입력하면=> 자동 auto 증가 increment
 mysql> use oxox
Database changed
mysql>
mysql>
mysql>
mysql>
mysql>
mysql>
mysql>
mysql>
mysql> create table topic(
    ->  id int(11) not null auto_increment,
=> 한 컬럼을 만들었다...
 - 
 
