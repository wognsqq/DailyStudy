### 스터디 내용 (생활 코딩의 #3,#4)

## NAT Network Address Translation
 - 각각의 ip들이 외부의 인터넷으로 접속할 수 있게 됩니다.
 - ex. 클라이언트로 동작할때,  위키피디아에 접속 
    1) 192.168.0.4 내 개인컴퓨터 -> Gateway(Router) Address 192.168.0.1에 신호를 보낸다.  
    2) LAN => WAN 을 통해 외부로 보내는 과정. 04가 보내는 과정이다를 기록 + 공유기에 NAT 요청한 데이터를 59.6.66.238 public ip address로 전환해서 위키피디아에 쏴줌
    3) 04가 요청했었던 (위키피디아에 접속) 사실임을 파악후에, 다시 04( 내 개인 컴퓨터)로 응답
    => 사설ip가 바깥쪽 public, 외부의 세계에 접속하게 해주는 기술이 NAT
  - 서버로 접속할 수 있게 하는 방법?

## 이 컴퓨터의 IP Address가 어떻게 되는가? 여러분의 router add(사설 ip)? 결과적으로 외부에서는 어떤 ip로 보여지는가?
  - 제어판=>네트워크와 공유센터=>커넥션에 케이블(이더넷) , 와이파이 =>Details => ipv4 address가 이 컴퓨터의 내부 네트웤 상에서의 ip add
  - default gateway = LAN에서, 공유기 Gateway address다.
  - 가정용 공유기를 사용하고 있는 경우에는, router의 ip address를 입력하면 로그인이 가능 => 라우터의 관리자에 접속하게 된거고, 여러가지 동작 세팅 가능
####   WAN 상에서 라우터, 퍼블릭 아이피 알아내기 
  - 공유기 관리자 => 외부 아이피 주소 (public address), 내부 아이피 주소 (gateway address)
  - my ip 구글에 검색
  
