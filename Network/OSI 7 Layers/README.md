### OSI 7계층

  * 네트워크 통신이 일어나는 과정을 7단계로 나눈 국제 표준화 기구에서 정의한 네트워크 표준 모델
  * 송신층, 1계층부터 각 계층을 지날 때마다 Header가 붙게되고 수신측은 역순으로 Header를 분석


1계층 - 물리계층 (Physical Layer)
  * 주로 전기적, 기계적, 기능적인 특성을 이용해서 통신 케이블로 데이터를 전송하는 물리적인 장비
  * 데이터의 전기적인 신호(0,1)로 변환해서 주고받는 기능
  * 통신 단위 : 비트 (Bit)
  * 장비 : 통신 케이블, 리피터, 허브 등

2계층 - 데이터 링크 계층 (DataLink Layer)
  * 물리계층을 통해 송수신되는 정보의 오류와 흐름을 관리하여 안전한 통신의 흐름을 관리
  * 프레임에 물리적 주소를 부여하고, 에러검출, 재전송, 흐름제어를 수행
  * 단위 : 프레임
  * 장비 : 브릿지, 스위치, 이더넷 등
  * 브릿지나 스위치를 통해 MAC 주소를 가지고 물리계층에서 받은 정보를 전달

3계층 - 네트워크 계층 (Network Layer)
  * 데이터를 목적지까지 가장 안전하고 빠르게 전달
  * 라우터를 통해 경로를 선택하고 주소를 정하고 (IP)경로 (Router)에 따라 패킷을 전달
    * IP Header 붙음
  * 단위 : 패킷(Packet)
  * 장비 : 라우터

4계층 - 전송 계층 (Transport Layer)
  * Port 번호, 전송 방식(TCP/UDP) 결정 -> TCP Header 붙음
      * TCP : 신뢰성, 연결지향적
      * UDP : 비신뢰성, 비연결성, 실시간
  * 두 지점간의 데이터를 주고 받게 해주는 역할
  * 신호를 분산하고 다시 합치는 과정을 통해서 에러와 경로를 제어

5계층 - 세션 계층 (Session Layer)
  * 두 지점 간의 프로세스 및 통신하는 호스트 간의 연결 유지
  * TCP/IP 세션 체결, Port 번호를 기반으로 통신 세션 구성
  * API, Socket

6계층 - 표현 계층(Presentation Layer)
  * 전송하는 데이터의 표현 방식을 결정
  * 데이터 변환, 압축, 암호화 등
  * 파일 인코딩, 명령어를 포장, 압축, 암호화
  * JPEG, MPEG, GIF, ASCII

[출처](https://blog.naver.com/smileman___/223266276183)
