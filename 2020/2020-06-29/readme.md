## WEB2 - Domain Name System -6. DNS의 원리

 - 컴퓨터가 두대가 있을 때, 93.184.216.34로 접속할 때 이름으로 접속하고 싶다? =>DNS서버에 93..... 이 example.com이라는 도메인 네임을 갖게 하고 싶다고 요청
 - 컴퓨터가 example.com이라는 도메인 네임으로 접속하면 -랜선을 꼽거나 와이파이를 접속하는 순간에 DNS 서버에 아이피 주소가 자동으로 세팅이 됨 (DHCP통해서) 
   호스트파일우선 접속 하는데 없을 경우 - DNS SERVER에 접속해서 아이피를 물어봄
 - DNS서버는 자기가 알고있는 ip주소를 컴퓨터로 보내줌
 - 예전에는 전화로 수동으로  시행했다면, DNS Server로 행정 절차 신속화 
 - 서버를 통해 ip관리, 변경된 사항들을 컴퓨터에 바로 반영할 수 있음

## WEB2 - Domain Name System -7. Public DNS의 사용
 
 - 서버에 접속해서 이 서버에게 example.com 아이피 물어봐서 컴퓨터로 가져올 수 있으려면  DNS 서버의 아이피, 도메인 정보를 알고 있어야 함.
 - 인터넷 통신사 sk,lg등이 ISP (Internet Service Provider) 컴퓨터에 도메인에 사용할 dns서버에 자동으로 아이피 세팅하는 메커니즘을 갖고 있다.
 - 자동으로 설정된 DNS 서버를 사용하고 싶지 않다면? 내 개인정보 유출이 꺼려지면?
 - public dns server 구글에 검색 => Free and Public DNS Servers =>자신이 사용하는 DNS Server 를 바꿀 수 있다.
 - 기관과 기업이 힘을합쳐 만든 Public DNS - DNS 서버 바꾸기
 - 제어판- 네트워크와 인터넷 - 네트워크 공유센터- 아답터 설정 변경 - 이더넷(랜선), 와이파이 클릭 - 프로퍼티 - ipv4 -속성 - use the following ip address -적용

## WEB2 - Domain Name System -8. 도메인 이름의 구조
 
 - DNS Internal , 서버를 운용하는 생산자의 수업 내용
 - DNS Server 한대가 하는 역할
   1) 서버로 사용할 컴퓨터가 자신의 이름과 아이피를 제출해서 등록하는 것
   2) 클라이언트로 사용될 컴퓨터가 이름을 물어보면 알려주는 것 
 - DNS서버는 전 세계에 수천 수만대 갖춰져 있음
 - blog.example.com(.)('.'이 생략되어있음) 도메인 각 부분 이름이 있다 
 - .=Root domain // .com = Top level Domain // example = second- level domain // blog =sub domain 
 - 도메인 각 부분은 각 부분을 담당하는 독자적인 서버 컴퓨터들이 존재한다
 - 루트 도메인을 담당하는 dns서버는 하위 개념 탑 레벨이 담당하는 dns 서버를 알고 있어야 한다 => 탑레벨 담당 dns server는 second -level dns알고 있어야 하고
    => 세컨 레벨은 서브의 목록과 아이피 주소를 알고 있어야 한다. 
 - 루트는 세컨드, 서브를 알지 못한다. => 자기 직속 하위 파트만 알고 있다. 
 - blog.example.com의 아이피주소를 알고 있는데 자기가 필요한 아이피를 한방에 알 수 있는 방법이 없기 때문에 알아가는 과정
   1) Root name server에 물어본다. (모든 컴퓨터는 루트 네임서버의 아이피를 알고 있다.) 
   2) 나 모르겠는데 주소가 컴으로 끝나니까 com전담하는 서버들의 아이피를 알려줄게 => 계속 하위 파트의 아이피를 알려주고 sub domain까지 갔을 때 아이피를 알려주게 된다.
 
