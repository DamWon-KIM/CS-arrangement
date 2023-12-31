### 동적 호스트 구성 프로토콜 DHCP란?

Dynamic Host Configuration Protocol로, 호스트 IP주소의 동적 할당을 위한 네트워크 설정을 제공하는 프로토콜 입니다. </br>
IP주소 할당에는 '고정 IP할당'과 '동적 IP할당'이 있는데,</br>
고정 IP는 PC별로 지정된 IP만 사용하는 방식으로, 회사나 기관에서 주로 사용합니다.</br>
이 같은 경우는 인증된 사용자만 해당 IP로 접속하므로 유지 관리 및 추적이 용이합니다.</br>

동적 IP의 경우에는 개인 PC가 대체로 동적 IP를 할당받아 사용하는데, 부족한 IP주소를 효율적으로 운용하기 위해, 
사용하지 않는 PC의 IP는 회수하고 사용할 때만 할당한다고 볼 수 있습니다.
DHCP는 호스트가 네트워크에 접속하고자 할 때마다 IP를 동적으로 할당받게 하여, 호스트가 빈번하게 접속을 연결하고 갱신하는 가정 인터넷 접속 네트워크 및 무선랜(LAN)에서 폭넓게 사용됩니다.

### DHCP의 동적 IP 할당 과정
DNS나 ARP 프로토콜처럼, DHCP 동적 IP할당 과정도 비슷하게 이루어집니다.
 - DISCOVER
 - OFFER
 - REQUEST
 - ACK

### DISCOVER, OFFER, REQUEST, ACK 4단계에서 브로드캐스팅을 하는 이유
```bash
* 브로드 캐스트 : 로컬 랜 상에 붙어있는 모든 네트워크 장비들에게 보내는 통신
 서버들이 자신이 어떤 서비스를 제공한다는 것을 모든 클라이언트에게 알릴 때 브로드캐스트를 사용
 이 외에도 라우터끼리 정보를 교환하거나, 다른 라우터를 찾을 경우에 사
 한 번 발생하고 끝내는 것이 아닌, 30초나 1분에 한 번씩 주기적으로 발생
```

- DISCOVER : 클라이언트가 DHCP 서버에게 IP할당을 요청하는데, DHCP 서버 IP를 모르므로 브로드캐스트로 요청에서 서버를 발견하게 됨</br>
- OFFER : 서버가 클라이언트에게 IP를 할당</br>
  이 때, IP를 제안하는 DHCP 서버는 앞서서 브로드캐스트로 DISCOVER했으므로, 여러대 일 수 있다.</br>
  주변 서버에서 가능한 IP를 제안한다.</br>
- REQUEST : 여러 DHCP 서버로부터 온 OFFER메시지 중 클라이언트가 사용할 IP를 고른다.</br>
  이 때 OFFER를 거절한 DHCP 서버도 해당 사실을 알 수 있도록 브로드캐스트로 전송한다.</br>
  그래야 해당 IP주소를 다른 서버나 클라이언트가 사용하지 않으며, 충돌을 방지 할 수 있다.</br>
- ACK : 서버가 해당 IP를 사용해도 된다고 확인 응답</br>
  이 역시 브로드캐스트로 송출되며, 해당 클라이언트와 DHCP 서버 통신에 문제가 있을 경우, 다른 장치나 관리자가 문제를 해결할 수 있도록 도와준다.</br>

  ```bash
  브로드캐스트를 통해, IP할당의 유연성과 안정성을 확보하고 타 장치와의 IP충돌을 방지하게 된다.
  ```
* 참조 : IPv4의 후속버전 인터넷 프로토콜인 IPv6는 브로드 캐스트 방법을 구현하지 않았다.
         그리고 특정 트래픽을 받으려고 할 때 해당 네트워크의 모든 노드에게 영향을 주지 않고 트래픽을 전달하도록 구현하였다.

[참조링크](https://security-nanglam.tistory.com/160) </br>
[참조링크2](https://star7sss.tistory.com/949)
