### 로드밸런서가 서버를 선택하는 방식에 대해 설명해주세요

* Round Robin
  * 단순히 CPU 스케줄링의 Round Robin으로 분산하는 방식
  * Weighted Round Robin Scheduling - Round Robin 방식으로 분배하지만 서버의 가중치에 따라 요청의 분배가 더 하기도, 덜 하기도 한다
  * ~네이버 클라우드 플랫폼에서 잘 쓰임

* Least Connections
  * 연결 개수가 가장 적은 서버를 선택하는 방식
  * 트래픽으로 인해 세션이 길어지는 경우 권장하는 방식
  * Weigthed Least Connections : Least Connection 방식으로 분배하지만 서버 가중치에 따라 요청을 더 분배하기도, 덜 분배하긷 한다
 
* Source
  * 사용자의 IP를 Hashing하여 분배하는 방식
  * 사용자는 항상 같은 서버로 연결되는 것을 보장함
 
* Fastest Response Time
  * 서버가 요청에 대해 응답하는 시간을 체크하여 가장 빠른 서버로 요청을 분배하는 방식
