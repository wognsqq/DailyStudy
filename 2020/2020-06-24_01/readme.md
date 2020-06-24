# 생활코딩 : Web to Home Server
 -(~#1,#2까지)

## 스터디 내용
 - 공유기를 사용하는 환경에서 웹 서버를 구동하는 방법을 알려드리는 수업 
 - 공유기에 연결된 컴퓨터에 불특정 다수가 접속할 수 있도록하는 과정
 - 현재 사용되고 있는 통신 규칙 IPv4(42억개)에서 더 이상 남은 게 얼마 없게되자(IOT,스마트폰 등의 발달)
   근본적인 해결방안 : 주소의 형식을 완전히 바꿔버리는 IPv6(2800구,자,...) 그러나 바로 바꿀 수는 없음 
 - => 공유기: 하나의 IP를 여러대 컴퓨터가 나눠 쓸 수있음
 - 공유기에 연결 돼 있는 컴퓨터에 웹서버로 사용하기 위해서는
 # 클라이언트에서 생산자로
   * Network Address Translation
   * Public VS Private IP Address
   * Port forwarding
   * Dynamic VS Static IP address
   * Dynamic DNS 등의 개념을 알아야 한다.


## Router
### 공유기는 어떻게 작동하는가? 사설IP 와 공용IP의 차이는?
 - 인터넷에 접속되어있는 컴퓨터는 양쪽 다 정보를 주고받기 위해 IP Address가 필요하다.
 - 1가정에서 인터넷을 쓴다고 할 때
 - (공유기 1개의 IP, WAN) (각 3개의 IP, LAN 노트북, 컴퓨터, 스마트폰)
 - LAN : Local Area Network
 - WAN: Wide Area Network(인터넷에 속해있는 네트웤
 - LAN과 WAN의 중개자, 교환원이 공유기, 영어로는 Router
 - LAN에 접속한 기계는 개별 IP를 부여받음 (Ex.192.168.0.1 , Gateway address, Router Address)
 - WAN 광역네트웍 안에서 공유기로 접속할 수 있게 해주는 IP (Ex. 59.6.66.238 , public IP address, 대표번호)
 - LAN에서 (?) 지역 네트워크 안에서만 쓸수 있는 IP (Ex. 192.169.0.4, private IP Address 사설 IP주소, 내선번호)

 동영상 링크
 [![Video Label](http://img.youtube.com/vi/sQBXgccvE98&list/0.jpg)](https://www.youtube.com/watch?v=sQBXgccvE98&list=PLuHgQVnccGMA52uRBmSwqcvtI5IMoFclJ&index=2&t=0s)
 
