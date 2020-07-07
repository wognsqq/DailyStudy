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