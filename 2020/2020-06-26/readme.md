# 스터디 내용 (#5)

# PORT
## 내 컴퓨터를 클라이언트가 아닌, 서버로 사용
 - 접속이 들어 왔을 때, 누가 이중에 서버로써 응답할 것인가를 공유기가 연결해줄 수 있도록
  
  * 각자 자신의 port에 정박해 있는 배. 하나의 컴퓨터에 웹 서버가 여러가지 있을 수 있지(web game chatting media ftp ..)server
  * Port Number 여러 서버 중 식별, 누구와 상호작용 할지 알려 주는 것
  * 0/ 20/ 80-http(hyper text transfer protocol)/ 1023/ 65535 /
  * Listening - 웹 서버에 들어와 있다. - 0~1023 = well known port 웹서버를 깔면 80번(web server)에 연결되있다.
  * 웹 서버를 하나 더 깔려면 80번은 안되고, 다른 포트를 쓰면 되는데, 관습적으로 80, 8000, 8080에 많이 설치 한다. 
  * well known port(유명한 서버) 에 못 들어가면, 1023~65535 사이에 들어가면됨
 - 누구와 상호작용할 것인가? 
  * http://opentutorials.org =>80 port에 접속, http로 통신하겠다=> http는 80port 
  * 8080에 Listening 하고 있는 웹서버를 하고 싶다면 http://opentutorials.org:8080
  * 127.80....어디서 나온건지..?
  
# 스터디 내용 (#6)

# Port Fowarding
## 우리의 공유기의 P ip Address = 59.6.66.238,  192.168.04에 웹 서버 설치 
 - Pf를 통해서 라우터로 들어온 포트번호가 무엇이냐에 따라서 내부 네트웤 특정 머신에 특정 포트로 요청을 Fowarding 할 수 있다.
 - 나의 웹서버에 접속하게 하려면 p ip address를 알려줘야하는데(?) 이걸 192.168.04로 연결 할 수 있게 Fowarding
  * Ex. 59.6.66.238:8081 로 접속이 들어오면 => 내부의 192.168.0.4:80으로 보내 => 192.168.0.4
        59.6.66.238:8080 로 접속이 들어오면 => 내부의 192.168.0.3:80으로 보내 => 192.168.0.4  
  * 라우터가 위의 행동을 함  iptime 서버관리 페이지 들어가면 설정 가능.
  * ip공개는 상당히 위험한 일

# 스터디 내용 (#7)
## Dynamic VS Static IP Address
### Dynamic IP Address
 - 부족한 ip 를 효율적으로 사용하기 위한 또하나의 다른 방법. 유동 IP라고 불림
 -집 -통신사 (ISP, Internet Service Provider) =>계약 => 누군가에게 ip주소를 알려주고 웹 브라우저에 ip주소를 치면 요청이 온다 (서버 기준)
  * 모든 집집마다 줄만큼의 ip숫자는 부족해 => 내 아이피(잘 안쓰던 ip)를 회수해서 다른 가입자에게  주고 또 주고.. 돌려막기.. 돌려막기 
  * IP가 자꾸 동적(Dynamic ip address)으로 바뀌잖아 
### Static IP Address
 -  내가 웹 서버를 깔아놨으면 다른사람에게 내 ip주소를 알려줬을텐데, dynamic ip add일 경우, 엉뚱한 사람에게 접속이 된다
  * => 2~3만원 내고 고정 ip(Static IP address)를 받음 

# 스터디 내용 (#8(1/2),9(2/2))
## DHCP(Dynamic Host Configuration Protocol)
 - 자신의 ip주소를 변경하는 방법, 그리고 그것이 얼마나 까다로운지 , 어떻게 자동으로 설정되는지 알아보자.
  * 원래는 컴퓨터의 ip add를 직접 지정해야 한다. => 중복된 사설 ip를 사용하면 안 된다. 

  * IP 직접 지정하는 방법 (원래는 이렇게 해야함)
    윈도우 - 제어판 -네트워크와 인터넷 - connection - properties - tcp/ip ver4 -속성 - 기본으로는 자동 - 
    직접입력칸으로 이동 -  subnet mask(?) - default gateway (192.168...) -  직접 하지 않고 자동 설정하는 방법 DHCP
  * DHCP Server (공유기에 내장) , 컴퓨터엔 기본적으로 DHCP Client가 깔려있다. 
    통신 부품들은 부품마다 고유한 식별자를 가지고 있다. 8c85:50:0c:e3:cc (Media Access Adreess, Physical Access Add)
    DHCP Client 가 난 8c:85:50...인데 ip주소가 필요해 => DHCP Server가 난 88:36...인데 192.168.0.4 임대해줄게. => 그거 쓸게
    =>라우터 (컴퓨터) 안에 8c 통신장치는 0.4 ip를 빌려갔다. => 이 ip add는 2시간동안 임대해줄게.
  * DHCP가 없었다면 모바일 혁명은 오지 않았거나 늦게왔을거다. 
   
 - DHCP를 이용해 나의 공유기에 접속하자 - 내부 네트워크 설정(DHCP기능을 제어하는 기능) -  동적 IP 주소 범위 - IP대여시간 - 맥 어드래스의 사용자에게는
   수동 등록으로 IP설정해서 IP대여시간 설정해서 준다. 
  * 각각의 컴퓨터는 기본적으로 IP대여시간동안 빌려줌 (Dynamic ip add), 직접 누군가에게 준다 - (Static ip add)
  * 공유기에 들어온 ip는 기본적으로 유동 아이피 - 라우터도 통신사에서 거대한 dhcp 체계를 갖고 있다.

# 스터니 내용 (#10)
## 소비문화. 최소한의 지식으로 엄청난 일을 할 수 있게 해줌.
 - 그것의 그늘. 쉽게 사용하다 보면 여러가지 문제가 생긴다.
  * 인터넷은 악의로 가득 찬 위험한 통로. 이 통로에서 살아남으려면 이 통로를 알아야 한다. 알면 기회의 통로가 된다. 
  * 라우터는 서버, 클라이언트, 아이피, 포트, NAT  
  * NAS (Network Attatched Storage) Dropbox GoogleDrive 와 같은 내 컴퓨터를 웹하드로 만드는 방법
  * Domain name // ip를 통해 내 서버로 접속시키는게 아니라, 도메인으로 접속시키면 유동 아이피에서도 내 서버로 들어올수 있다. 
  * DDNS (Dynamic DNS) 고정아이피를 갖고있는것과 비슷한 효과
  * 보안 Http (80) 감청 확률이 높은 Http의 약점을 보완한 - Https (Hyper text transfer Protocol overSecure) 요새는 무료
    단순 제공이 아닌, 사용자의 정보를 저장하는 웹이라면 반드시 Https를 사용해야 한다 - Let's encript 에서 무료로 인증서 발급
 
  * 가정에서 서버운영은 별로 좋지 않다. => web hosting / server hosting / cloud computing 업체를 통해 실제 서비스를 운용(?)
   



 