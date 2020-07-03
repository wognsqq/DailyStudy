## DATABASE 2 MySQL 1. 수업 소개
 - file : 정보관리도구 쉽고 전송하기 편리 데이터베이스도 파일에 저장하는 구조
 - file 만으로 입력 저장 출력 데이터를 입력해서 필요할 때 꺼내쓰고 싶다 => 1960년대부터 개발, 이것이 데이터베이스 =>1970 Relational DATABASE ... 2018년까지 RDB는 절대강자
 - RDB로 데이터를 표의 형태로 정리할 수 있고, 정렬 검색 등의 작업을 빠르고 편하게 할 수 있다. 
 - RDB의 종류 : MySQL / Oracle / SQL Server/ PostgreSQL/ DB2/ Access
 - WEB의 폭발적인 성장. 수많은 엔지니어들이 무료인 MySQL을 사용하면서, WEB과 함께 성장하여 현재 MySQL은 데이터베이스의 지배자.
 
## DATABASE 2 MySQL 2. 데이터베이스 사용의 목적
 # 데이터베이스와 spreadsheet 공통점, 차이점

 - RDB와 SpreadSheet의 공통점 : DATA를 표로 표현해 준다.
 - RDB와 SpreadSheet의 차이점 : RDB는 코딩= 컴퓨터 언어를 통해 제어할 수 있다. Spreadsheet는 클릭하고 기다려야 한다. RDB는 사람의 말을 알아들을 수 있다. 
 - SELECT*FROM topic WHERE author = 'egoing' ORDER By id DESC; => 전체범위에서 골라라/ 토픽을/ author에 순서대로 정리해라/ 큰 숫자 순으로.
 - 코드를 통해 데이터를 정렬하는 것...
 -  web app을 통해 공유할 수도 있고, 웹을 통해 이 데이터를 표시해 보자
 -  web에 입력한게 mysql에 추가되네? 데이터베이스를 내부적으로 중요부품으로 사용하는 수많은 사례중에 하나.  