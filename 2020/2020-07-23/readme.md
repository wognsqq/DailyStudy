## WEB1 - 19. 웹서버 운영하기
[WEB1 - 19. 웹서버 운영하기](https://www.youtube.com/watch?v=ThlyDSM0FNU&list=PL2Mkwvh6s7KI1Wb3COvfpVUZi46XG322g&index=19)
- 인터넷이 동작하는 여러 원리를 알수 있다
- 실습이 동작하지 않을 가능성이 매우 높다. 
- 보통 웹 호스팅을 사용하지만..
- 웹 서버 Apache를 설치해보자
- how to install apache http server os
## WEB1 - 19.1.1. 웹서버 설치 (윈도우)
[WEB1 - 19.1.1. 웹서버 설치 (윈도우)](https://www.youtube.com/watch?v=Bvzzee7-kuQ&list=PL2Mkwvh6s7KI1Wb3COvfpVUZi46XG322g&index=20)
- how to easy install apache on window
- bitnami WAMP STACK
- bitnami를 통해 apache를 설치했다
- Bitnami tool에서 Apache Web Server찾자

## WEB1 - 19.1.2. 웹서버와 http (윈도우)
[WEB1 - 19.1.2. 웹서버와 http (윈도우)](https://www.youtube.com/watch?v=had7IqJHEKM&list=PL2Mkwvh6s7KI1Wb3COvfpVUZi46XG322g&index=21)
- http://127.0.0.1/index.html 을 치면 똑같은 화면이 나와야 한다
- C:\Bitnami\wampstack-7.4.8-0\apache2\htdocs
```html
<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
<title>Bitnami: Open Source. Simplified</title>
<link href="bitnami.css" media="all" rel="Stylesheet" type="text/css" />
</head>
<body>
<h4>web1</h4>
<div id="container">
  <div id="header"> 
    <div id="bitnami">

```
- 폴더 찾아가서 메모장으로 연다 - web1이라는 글자를 작성한다
- bitnami -htdocs- 라는 디렉토리에 index.html 이 저장되어있고, 컴퓨터에 웹 브라우저와 웹서버가 한대에 설치된 상태
- 웹서버를 통해서 htdocs밑에있는 index.html을 찾아오고 싶으면, https://127.0.0.1/index.html
- 127.0.0.1 => Internet Protocol Address = IP Address
- 웹 브라우저가 자신의 컴퓨터에 접속해있는 웹서버에 접근해서 웹서버는 htdocs라는 디렉토리에서 파일을 찾도록  기본적인 설정이 되어있는 상태
- 웹 서버가 index.html을 전송해주면 브라우저가 읽어서 표현
- htdocs 삭제하고 web1 파일을 넣고 reload
- 주소를 입력하여 웹페이지를 보는 것과, 파일 열기를 통해 보는 것 사이의 차이는?
- 차이가 없어보이는데 질적으로 완전히 다르다 
- http://127.0.0.1/index.html vs file:///C:/Bitnami/wampstack-7.4.8-0/apache2/htdocs/index.html
- 127.0.0.1의 경우 웹브라우저가 웹서버에게 요청하는 것 
- file:///C:/Bitnami/wampstack-7.4.8-0/apache2/htdocs/index.html 이 컴퓨터에서 웹 서버는 개입하지 않고  웹 브라우저가 직접 index.html을 읽어서 열어주는 것
- http:// 웹브라우저와, 웹 서버를 통신할 때 사용하는 통신 규약
- file:// 파일 경로를 표시하는
- 서로 다른 컴퓨터에 있는 웹 브라우저와 웹 서버가 통신하기 위해서는 반드시 http를 사용해야 한다!

## WEB1 - 19.1.3. 웹서버와 웹브라우저의 통신 (윈도우)
[WEB1 - 19.1.2. 웹서버와 http (윈도우)](youtube.com/watch?v=gde0uNwMSa4&list=PL2Mkwvh6s7KI1Wb3COvfpVUZi46XG322g&index=22)

- Web Browser =>Web Server
- 친구에게 전화를 할때는 전화번호가 필요하듯이, 웹브라우저가 웹서버에 요청을 할 때는 ip address가 필요하다. 
- http://192.168.0.13/index.html 로 요청
- 전제조건 1)컴퓨터가 2대 있어야 한다. (컴퓨터/ 스마트폰)  2) 웹서버가 설치된 컴퓨터의 아이피주소는 윈도우의 부채모양 아이콘 오른쪽 클릭  
- 네트워크 및 공유 센터 열기 - 연결 - 자세히 - Ipv4 Address를 확인 
- 127.0.0.1은 전 세계적으로 모든 컴퓨터가 그것을 자기 자신을 의미
- 무선인터넷이라면 같은 네트워크에 들어있어야 한다. 
- 와이파이 공유기가 같아야 한다. 
- 서버 컴퓨터의 아이피 주소를 스마트 폰으로 입력
- 서버로 신호가 가고 index.html파일을 읽어서 전송해주면 스마트폰에 출력


## WEB1 - 20. 수업을 마치며 1/3
[WEB1 - 20. 수업을 마치며 1/3](https://www.youtube.com/watch?v=bTSDDyuMuUo&list=PL2Mkwvh6s7KI1Wb3COvfpVUZi46XG322g&index=27)
- 본질과 혁신/ 교양과 직업
- 진도가 나갈수록 중요도는 급격히 떨어진다
- 진도가 나아갈수록 난이도는 급격히 올라간다
- 교점의 앞쪽은 본질 교양
- 뒷쪽은 혁신과 직업
- 만족감 자신감 기대감 성장하자
- 코딩 교양 - 출구 // 직업 - 입구로

## WEB1 - 21. 수업을 마치며 2/3
[WEB1 - 21. 수업을 마치며 2/3]( https://www.youtube.com/watch?v=JUNFoER12kk&list=PL2Mkwvh6s7KI1Wb3COvfpVUZi46XG322g&index=28)
- 좋은 코드가 무엇인가? 어떻게 짜는가?
- 현명한 판단을 할수있는 재료들
- 복잡함. 눈에 보이는/보이지않는
- <input type>="checkbox"
- 체크박스가 2개면 4번의 테스트, 3개면 8번의 테스트
- 체크박스가 50개라면??
- 2^50 = 1000조개의 경우의 수, 체크박스보다 복잡한 앱이 훨씬많은데
- 그걸 눈에 보이지 않아서 버그가 생기지..
- 개념을 알게 되는 것은 체크박스가 늘어나는 것. 복잡함은 나쁘지 않다 
- 주어 동사 목적어 10개씩 하면 1000개의 문장을 만들 수 있다
- 간단한 문법으로 무수한 이득을 발생시킬 수 있다. 
- 인생에서 중요할수록 불만족이 쏟아져 나올겨
- 불만족이 누적되어 절망감이 성숙해져야 한다. 진도를 나가자

## WEB1 - 22. 수업을 마치며 3/3
[WEB1 - 22. 수업을 마치며 3/3](https://www.youtube.com/watch?v=WD-LFlMi6iA&list=PL2Mkwvh6s7KI1Wb3COvfpVUZi46XG322g&index=29)
- 혁신을 향해 나아가는 사람
- 정보의 효용은 최소한으로 배워서 최대로 써먹자
- 웹사이트를 아름답게 꾸미고 싶다 => web2 css / web publisher, web designer
- 사용자와 상호작용하고 싶다 => web2 JavaScript / web front end engineer, web interactivedesigner
- back end => 하나의 파일을 변경하면 1억개가 바뀐다 =>web2 JSP, PHP, Node.js
- web2광고수업 => 광고수익을 올리고 싶다.
- 알고있는 지식을 이용해서 프로젝트화, 알고있는 지식을 컨텐츠로 만들어 알려주기
- 프로젝트를 시작해보고 컨텐츠를 만들어봐.