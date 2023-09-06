### 동적 호스트 구성 프로토콜 DHCP란?

Dynamic Host Configuration Protocol로, 호스트 IP주소의 동적 할당을 위한 네트워크 설정을 제공하는 프로토콜 입니다. </br>
IP주소 할당에는 '고정 IP할당'과 '동적 IP할당'이 있는데,</br>
고정 IP는 PC별로 지정된 IP만 사용하는 방식으로, 회사나 기관에서 주로 사용합니다.</br>
이 같은 경우는 인증된 사용자만 해당 IP로 접속하므로 유지 관리 및 추적이 용이합니다.</br>

동적 IP의 경우에는 개인 PC가 대체로 동적 IP를 할당받아 사용하는데, 부족한 IP주소를 효율적으로 운용하기 위해, 
사용하지 않는 PC의 IP는 회수하고 사용할 때만 할당한다고 볼 수 있습니다.


### DHCP의 동적 IP 할당 과정
DNS나 ARP 프로토콜처럼, DHCP 동적 IP할당 과정도 비슷하게 이루어집니다.
 - DISCOVER
 - OFFER
 - REQUEST
 - ACK

### DISCOVER, OFFER, REQUEST, ACK 4단계에서 브로드캐스팅을 하는 이유
