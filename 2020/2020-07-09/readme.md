## Database2 - MySQL - 18. 인터넷과 데이터베이스
### server의 의미?
- 인터넷을 사용하기 위해서는 컴퓨터가 최소 몇 대 필요한가 => 2대, 
- 인터넷의 의미: 각자 흩어져있는 컴퓨터들이 한곳에 뭉치면서, 컴퓨터들의 사회.
- 한대 컴퓨터가 갖고 있는 한계를 넘어섰다. 정보 요청과 응답, Web이 동작하기 위해서는 인터넷이 필요하고
- 웹 브라우저가 설치된 컴퓨터 1대 - 도메인 주소 입력 (www.naver.com 입력) - 요청한 정보를 받아서 웹 브라우저에 표시하면 그 과정이 끝
- 요청/응답하는 쪽으로 나뉨. 이러한 역할분담을 설명 : 요청(Client, 고객, 갑) 응답(Server, 사업자, 을)
- 클라이언트 컴퓨터는 서브 컴퓨터에게 정보를 요청하는데, 게임한다면, 게임 서버/ 게임 클라이언트.
- MySQL 은 2개의 프로그랩을 동시에 설치해준다 (Database client, Database server), 데이터베이스 서버는 반드시 데이터베이스 클라이언트를 사용해야한다. =>/mysql -uroot -p => "welcome to the mysql monitor"(명령어를 통해 데이터베이스를 통제하는 프로그램)
- Mysql workbench를 사용하면 GUI 환경에서 , 그래피컬한 환경에서 mysql을 다룰 수 있다. 
- 이해가 아니라, 익숙해져보자 ㅎㅎ... 
- Database server를 통해서, 전 세계의 수많은 사람들이 하나의 서버를 통해 정보를 주고받고 관리할 수 있게 해줄 수 있다. 

## Database2 - MySQL - 19. MySQL Client
- Mysql의 장점 - 명령어 기반으로 빠르게 처리. 단점 - 명령어를 모르면 처리를 못함 => 검색으로 해결
- gui기반 클라이언트의 장점 -  클릭클릭으로 보다 쉽게 처리. 단점 - 클릭하는 동안 기다려야 함


## Database2 - MySQL - 20. MySQL Workbench
- MySQL 서버와 클라이언트가 같은 컴퓨터에 위치해 있으므로 
- mysql -uroot -p (ip주소 생략되있음) 기본적으로 안쓰고 엔터치면, mysql mornitor와 서버와 같이 설치된 곳 접속한다고 생각
- SQL workbench를 이용해서 스키마를 생성하고, 컬럼을 추가해보자
```sql
mysql> show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| mysql              |
| performance_schema |
| pxpx               |
| sys                |
| workbench          |
+--------------------+
6 rows in set (0.00 sec)
```

- 모니터를 쓰건 워크벤치를 쓰건 모든 클라이언트는 sql을 mysql서버에 전송함으로써, 데이터베이스 서버를 제어하게 된다. 
- (자바, 파이썬, php)등의 프로그래밍 언어를 통해서, 앱,웹에서 굉장히 중요하고 넘기 힘든데, sql문을 생성해서 그것을 서버에게 전달하는 것이다.
- workbench -tables - topic 옆에 번개 그려져 있는 네모 클릭, - 테이터 입력
- Performance - 메모리 얼마나 사용했는지 등의 정보를 보여주는 기능
- instance -  데이터를 끄거나 키거나 , Export 데이터를 빼거나..
- mySQl 서버가 있고 client가 별도로 존재하기 때문에, 복잡해졌고, 좋은 점은 mysql client를 통해 다양한 mysql 생태계가 존재하게 됐다. 
- 모든 데이터베이스 검색 시스템은 모두가 mysql client다.


## Database2 - MySQL - 21. 수업을 마치며
- 두갈래의 길 :지금까지 배운 것을 사용해 현실의 문제 해결 or 극복할 수 없는 한계를 극복할 수 있도록 엔지니어의 이론과 기술을 배우는 길
- 당장 후자인 혁신을 쫓기 보다는 이미 많은 것을 배웠기 때문에 그것부터 해보자. 충분히 혁신적이고 혁명적이다. 
- 데이터가 많아지고 중요해지고 더 많은 사람이 관리해야 되는 상황이 오면, 한계에 부딪힐 때, 절망했을 때가 혁신을 향해 갈 때다.
- 복습 열심히 해라

### 공부 할 것들
- SQL 관계형 데이터베이스를 잘 다루는 사람 : sql을 잘 이해하고 쓸 줄 아는 사람
- CRUD R에 해당하는 SELECT는 상당히 복잡한데, 여러 면모를 잘 살펴보면서, 가장 좋은 것을 잘 살펴보는
- index , 정보가 많아지면서 생기는 현실의 지옥들
  1) 데이터를 정리하지 않는다는것은, 넣을 때 편하고, 정리를 처음에 해놓으면, 꺼낼 때 편하다.
- index : 색인, 데이터가 들어올떄 데이터베이스가 그 컬럼의 데이터를  별도로 정리한다.
- modeling : 데이터가 많아짐에 따라 여러 문제가 생길 수 있는데, 데이터베이스의 구조(테이블)를 효율적으로 잘 설치 하는 방법.
- 테이블 어떻게 만들어야되나? 는 modeling을 검색해보자
- backup : 하드디스크에 대해 예측할 수 없는 것 - 언제고장남? 예측할 수 있는 것 - 반드시 고장남.
- 내 컴퓨터와 동시에 다른 곳에 저장해 놓는다면 데이터 분실의 가능성이 현저히 떨어진다. 
- mysqldump, binary log
- cloud : 큰 회사들이 운영하고 있는 인프라 위에 있는 컴퓨터를 임대해서 사용하는 것이 cloud computing, 원격제어를 통해 다룬다. mysql같은 데이터베이스를 클라우드를 서비스함으로써,
가서, 클릭클릭 하면 데이터가 생성된다. 세계 최고 수준의 엔지니어가 인생을 갈아넣어서 서비스 하고있기 때문에, 백업도 알아서 해줘서, 정말로 쉬워집니다. 클라우드의 흐름을 관찰해보자.
(AWS RDS, Google Cloud SQL for MySQL, Azure Database for MySQL...)
- programming: 데이터 베이스 자체를 쓰는 경우보다, 부품으로 정보시스템을 완제품으로 만드는 것.
(Python mysql api, PHP mysql api, JAVA mysql api) 그 언어로 데이터베이스를 쉽게 컨트롤 하는 조작 장치

## 동영상 링크
[DATABASE2 MySQL - 18.인터넷과 데이터베이스](https://www.youtube.com/watch?v=hjgaxlTQMXk&list=PLuHgQVnccGMCgrP_9HL3dAcvdt8qOZxjW&index=24) 
[DATABASE2 MySQL - 19.MySQL Client](https://www.youtube.com/watch?v=yWy1PlkMMIw&list=PLuHgQVnccGMCgrP_9HL3dAcvdt8qOZxjW&index=25)
[DATABASE2 MySQL - 20.MySQL Workbench](https://www.youtube.com/watch?v=JWB6sUd1R-Q&list=PLuHgQVnccGMCgrP_9HL3dAcvdt8qOZxjW&index=26)
[DATABASE2 MySQL - 21.수업을 마치며](https://www.youtube.com/watch?v=ySH4-hEdiTs&list=PLuHgQVnccGMCgrP_9HL3dAcvdt8qOZxjW&index=27)
