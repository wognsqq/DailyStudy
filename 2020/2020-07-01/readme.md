# WEB2 - Domain Name System-12. DNS record & CNAME
## 서버의 도메인 name을 지정하는 새로운 방식
 - dns4u.ga 라는 도메인, 52.132...으로 접속한다고 했을 때, Registrar - authoritative name server - DNS record = dns4u.ga A 52.132.... 에서 'A'는 이하 ip주소가 ~~~이다 라는 뜻. 
 - dns4u.ga NS ns01.freenom.com = DNS Record 1건
 - dns4u.ga를 관리하는 freenom에서 제공하는 네임서비스를 사용 => freenom.com에서 DNS MANAGEMENT for dns 들어가서 - Type (A) - add로 Name에 'blog'추가하면 blog로 같은52.132...로 접속 가능
 - dns record 구글링 - 어떠한 DNS Type이 있는지 보여준다. 
### CNAME(구글 -  What is a CNAME Record 이미지 참조)
 - CNAME , 이 도메인에 대한 별명을 정함으로써, www.example.com.으로 접속하게 해준다. 
 - A record : 도메인에 대한 ip주소 
 - CNAME : 도메인에 대한 또 다른 도메인을 지정하는 것
 - 사용 예시: example.com 의 ip주소가 자주 바뀔 때, 이 사이트를 가리키는 또다른 주소가 있을 때, 그때마다 ip주소를 바꾸는게 아니라, 여러 사이트들이 CNAME을 통해서 example.com을 가리키는 상태에서 a record의 ip주소만 바꾸면
이름을 갖고있기 때문에 걔들한테는 변경하지 않아도 된다. 
 - CNAME; 별명을 붙인다.
 - freenom - manage - add record - api.dns4u.ga -type : CNAME - target :dns4u.ga => nslookup api.dns4u.ga cmd에 실행 하면 => dns4u.ga의 아이피를 알려준다.

# WEB2 - Domain Name System-13. domain name mapping
## 내가 서버를 운영하지 않고, 남의 서비스를 사용하는 경우, 도메인을 붙이고 싶을 때, 서비스가 도메인을 허용할 경우
 - 내 웹서버가 아니다 보니. 복잡하고 지저분한 이름을 사용 (web-n.github.io/web_html_internet)했다가 계속 필요하게 될 경우 - 이사를 다른 주소로 하려 할 때 - 서비스가 도메인 허용치 않을경우, 사람들이 이사한 주소로 못온다. - 도메인을 붙일 수 있게 지원한다? - 사람들은 dns4u.ga 도메인으로 접속
 - 저 도메인을 새로운 도메인 서비스로 옮기고 기존 주소는 파기될 것 , 사람들이 내 서비스에 방문하지 못하는 상황이 없어질 것이다.
 
## 어떻게 github에 내가 만든 홈페이지를 도메인을 붙일 수 있는가??
 - web-n.github.io/web_html_internet 위 주소의 홈페이지를 갖고 있다면, 이 주소에 해당하는 콘텐츠를 볼 수 있게 하려면 - dns4u.ga 도메인 대여또는 구입 - dns Server에 dns4u.ga의 ip 는 192.30.252.153 라고 a레코드로 등록
 =>다른 사람들이 기존의 web-n.github.io/web_html_internet 로 접속 할 수 있도록 해주세요 - github가 운영하고 있는 홈페이지에 dns4u.ga 도메인의 ip로 접속을 할 텐데, 도메인으로 요청이 들어왔다 
 - 접속하려는 자가 dns4u.ga 를 통해 web-n.github.io/web_html_internet 로 접속했다는 걸 알게 해준다.
 - dns4u.ga 는 어떤 컴퓨터를 가리키고 있는가? 웹호스팅 통해 깃허브 사용법이 나오는데 - 설정 - github pages - Custom domain - dns4u.ga -save => 이 홈페이지는 dns4u.ga라고 쓸테니 web-n.github.io/web_html_internet 로 접속하게 해주세요 라는 뜻
 - learn more - Settin up an apex domain and www subdomain. - www가 없음 apex // - Setting up an apex Domain - Configuring A records(ip를 통해 접속) with your DNS Provider - 명시된 아이피를 dns 서버에 복붙하세요(안정성을 위해 2개의 아이피 제공) 
 
### 깃헙에 어떤 서비스에 도메인을 연결해서 도메인으로 접속하는 방법을 알아냈다!

# WEB2 - Domain Name System-14. 수업을 마치며
 - HOST 에게 자신의 Domain name을 붙이는 방법
 - ip주소를 변경해도 서비스를 계속해서 제공할 수 있는 유연함
## 공부해볼만한 주제
 - DNS통신규칙 이후 -BIND 제작 (최초의 DNS Server, DNS Server의 표준) -  자신의 DNS를 직접 운영해볼래?
 - DNS Service : Local DNS~ 서버의 IP를 알려주는 DNS 나에게 맞는 DNS를 찾아보자
 - DDNS (Dynamic DNS): 우리에게 들어오는 DNS가 항상 바뀜.
 - HTTPS, SSL : 악의적인 아이피 접속 차단, SSL: 피싱사이트 들어갔을 때, 아주 강력한 경고메세지를 주는데, 인증서 무료화됐으니 사용해보자  
