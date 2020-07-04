## DATABASE2 MySQL - 3.MySQL 설치 (Windows)
 - 구글에 mysql community server 치고 상단 페이지 들어가서, community server다운
 - bitnami wamp 들어가서 윈도우 버전 찾고 mysql설치
 - 설치 완료 후, cmd에 C:\Users\jung>cd c:\Bitnami\wampstack-7.4.7-0\mysql\bin
 - c:\Bitnami\wampstack-7.4.7-0\mysql\bin>mysql -uroot -p
    Enter password: *********
 - mySQL > n

## DATABASE2 MySQL - 3.4. MySQL 설치 (codeanywhere.com)
 -  여기 사이트에서 mySQL처럼 사용 가능

## DATABASE2 MySQL - 4.MySQL의 구조
 - 데이터 기록의 최종적인 장소는 표, Spreadsheet와 비슷한 구조
 - 연관되 있는 표를 그룹해서 연관되어있지 않은 표들과 분리하는데 사용하는 파일에 폴더가 데이터베이스
 - 스키마?? 표들을 서로 그룹핑할 때 사용하는 일종의 폴더
 - 스키마는 서로 연관된 데이터를 기록해 준다. 스키마가 많아지면 데이터베이스 서버에 저장된다.
 - (MySQL에서 커뮤니티 서버 받았고, bitnami에서 데이터베이스 받았다)

## DATABASE2 MySQL - 5.서버접속
 - 데이터베이스의 효용 : 보안 , 파일을 뚫리면 무주공산. 데이터베이스는 암호체계
 - 권한: mySQL에 많은 사람을 등록할 수 있어서, egoing은 모든 테마에 대해 읽고 쓰고 검색하고 할 수 있고,
   xxx는 읽기만 할 수 있고..
 - schema
 - cmd로 다시 접속해보자.