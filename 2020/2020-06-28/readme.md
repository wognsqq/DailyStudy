# WEB 2 Domain Name System
## (#1)
 - Server Client IP Address.
 - host : 인터넷에 연결된 컴퓨터 한대 한대. => 통신을 위해 필요한 주소 ip => host - host 연결해서 한대의 컴퓨터가 한대의 한계 초월
 - IP 주소를 기억하는 것이 너무 어렵다. 인터넷의 신이 Domain Name System 개발 => DNS Server 수만은 ip 주소의 도메인 이름이 저장되어 있다. 
 - 운영체제는 DNS 서버에 접속해서 www.icann.org에 아이피 주소를 물어봄 => DNS 가 IP주소를 알려주면 ip주소에 해당하는 컴퓨터에 접속.
 - 미지의 대상에 이름을 붙임으로서 미지의 대상이 존재하는 것처럼, 대화하고 생각하고 기록해 계산한다. 도메인 이름을 짓는 작명가가 되어보자.
 
# WEB 2 Domain Name System. 2. IP주소와 hosts(1/2)
## (#2)
 -  hosts 
 - 클라이언트 -> 서버 / 클라이언트가 서버로 접속할 때는 서버의 아이피를 알아야 한다. 
 - 서버는 203.0.113.0에게 응답을 하려면 클라이언트의 ip를 알아야 한다. 
 - 모든 운영 체제에는 host파일이 있는데 파일에 (93.184.216.34) example.com 적어놓으면 위 아이피로 서버가 접속한다.
 - host에 이름을 부여할 수 있다.
 - host 파일을 운영체제별로 변경해서 도메인으로 바꾸는 모습을 살펴 보자

# WEB 2 Domain Name System. 3. IP주소와 hosts(2/2)
## (#3)
 -  host파일의 위치  찾아내기 hosts wikipedia - Location in the file system 
 -  windows : %SystemRoot%/Ststem32/drivers/etc/hosts
 -  리눅스. mac도 다 나와있음  (동영상 참조)
 -  메모장 - 관리자 권한으로 실행 -  file - open - windows directory - system 32 - etc( All files) - hosts - 내용을 추가
 -  Web의 아이피 주소 52.231.12.15 - web1.com으로 접속했을때 위 아이피로 들어오게 하려면 - 메모장에 
    52.231.11.152 web1.com -저장

# WEB 2 Domain Name System. 4. 도메인 이름과 보안
## (#4)
 - example.com의 ip를 93.184.216.34로 저장했을 때, 악의적으로 66..66.66.66 으로 연결되게 했다면 -
 - 예방하려면 백신사용
 - 어떤 문제가 생길까? kbstar.com접속 한다고 할 때 악의적으로 호스트파일 아이피를 바꿨다면 엉뚱한 사이트가 나온다.
 - 이 사이트를 국민은행과 완전 똑같이 만들면? 피싱
 - https로 접속하면 우리에게 경고를 해줄 수 있다. 
   kbstar 완전히 다 타이핑해서 들어가면. your connection is not private 뜸

# WEB 2 Domain Name System. 5. DNS의 태동
## (#5)
 - DNS 이전의 시대는?? DNS등장의 맥락
 - hosts파일을 이용해 IP주소부를 개인적으로 운용할 수 있었다. 
 - example.com으로 들어오면 이 아이피로 모든컴퓨터가 들어올 수 있으면 얼마나 좋을까?  
 - example.com은 유지하면서 아이피주소는 바꾸는 - 중간에 신뢰 업체 Stanford Research Institute 전 세계 호스트 파일 관리  
 - 93.184.216.34 는 example.com으로 해주세요 라고 스탠포드 연구 협회에 전화해서 갱신해줌.
 - 각자가 host파일을 관리하는게 아니라, 신뢰업체를 거쳐서 관리 했었다.  
  * 이 방식의 문제점: 호스트 파일을 스탠포드협회로부터 다운 받기 전 까지는 호스트의 이름을 사용할 수 없다. 많은 시간과 비용의 문제 
    하나의 호스트 파일에 모든 인터넷주소가 담길 수 없는 한계
 - 새로운 고민이 시작, 1983 인터넷의 신 John Postel, Paul Mockapetris에 의해 Domain Name System 두둥등장. 