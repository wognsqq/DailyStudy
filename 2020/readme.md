## WEB2 - Domain Name System-9. DNS register

# DNS 시스템이 어떻게 동작하는가 ? 도메인 이름을 갖기 위해 어떤 절차가 필요한가?
 - 등록자(Registrant) 서버로 쓸 컴퓨터 example.com주소를 부여하고 싶다. 
 - ICANN,DNS시스템의 최고 꼭대기엔 ICANN (전세계 아이피 주소 관리, 루트네임 서버 관리) => 인터넷 체계 전체를 관리하는 거대한 비영리단체 Root name server //  a.root-servers.net 
 - Registry(등록소) Top - level domain '.com .net' 을 관리 a.gtld-servers.net
 - Registrar(등록대행자)
 - example.com을 Registrant가 쓰고 싶으면 Registrar에게 수수료 주고 등록
 - 루트 네임서버 에는 com NS a.gtld.servers.net으로 적혀있다.
 - 스스로 서버한대를 마련해서 name server를 설치해야함 (a.iana-servers.net). 등록대행자가 제공해주는 경우도 있고, 무료로 사용할 수 있는 경우도 있음
 - 등록대행자에게 example.com NS a.iana-servers.net이다를 보내면 Registry(등록소)에 보내고, 등록소 서버 Top lv domain에 등록
 - 네임서버 example.com 의 아이피가 ~~~다라고 설정하는 것은, 네임서버에 접속해서 example.com A 93.123.123.2 라고 알려준다. 
 - 구체적인 example.com의 아이피 주소는 최종적인 값이라고 해서 'A'라고 하고 , 레코드 타입이라고 한다. 
 
 - 클라이언트 컴퓨터를 가지고 example.com에 접속하는 여정 
 - 랜선을 꼽거나, 와이파이에 연결하는 순간, 내 컴퓨터에는 내 컴퓨터가 도메인 정보를 조회할 때 사용할 도메인 네임서버의 주소가 자동으로 세팅이 된다.
 - example.com 접속 -DNS Server 로 보내면 dns서버가 rootnameserver에 물어봄 - 루트네임서버는 .com이 누가 관리하는지 알기 때문에  그걸 관리하는
   a.gtld-servers.net의 주소를 알려준다.  -DNS 는 그 주소로 접속 시도 - authoritative name server, 등록대행자의 서버가 DNS서버에 아이피 주소를 알려줌

## WEB2-Domain Name System-10.nslookup

# example.com의 아이디가 무엇인가? nslookup 사용(윈도우), dig(윈도우 호환 아직 안됨)
 - 윈도우 cmd 
 - nslookup example.com 치면 Address가 찍힌다.
 - 처음 나오는 정보 : 맨처음 연결되는 dns server의 주소
 - 인터넷 dns system에는 구석구석 cache가 있어서, 같은 정보를 요청하면 자기가 기억하는 ip를 알려줌
 - cache가 응답한 것이라면, authoritive가 응답한 것이 아닌, 저장된 정보를 알려준 것이기 때문에 Non authoritive로 나옴
 - caching이 아니라 직접 물어봄=> nslookup.com a.iana-servers.net(authoritive 네임 서버의 주소)
 - ns lookup -type(네임서버에 관한 정보) =a example.com (-type은 a와 같습니다.)

## WEB2-Domain Name System-11.나의 도메인 이름 장만하기

# 나의 도메인 이름을 가져보자
 - dns.4u.ga / 52.231.13.171 : 등록 대행자를 통해 등록소에 등록해야 한다.
 - freenom.com 1년동안 ga tk 몇몇 탑레벨 도메인을 1년간 무료로 쓸 수 있게 해줌
 - 회원가입 및 로그인 => Register New domain => Find your new Domain란에 dns4u 체크 => 맘에드는 도메인 체크아웃 => Period 선택 continue 
 => 만료일 항상 확인 => menu - my domain 에서 구매목록 확인 -manage domain - manage freenom DNS - 레코드 등록(IPV6방식) - ip를 type란에 작성
 TTL(Time To Leave :캐쉬가 얼마나 오래 지속되는가? 장점:빠르다 단점: 캐쉬가 갱신될 때 까지 ip가 바뀔때까지 갱신이 안됨) -save changes
 - 등록대행자에게 도메인을 사고싶다 했더니, 등록소(freenom에서 도메인을 줌)
 - nslookup dns4u.ga 접속하니, 인터넷 상의 나의 이름을 갖게 되는 순간! 