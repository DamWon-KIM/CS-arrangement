### 스케줄링

시스템 환경에 따라 분류해보시오 </br>
Preemptive, Nonpreemptive

### scheduling algorithm
throughput : 단위 시간에 완료된 job의 갯수 </br>
turnaround time : job이 system에 submit된 다음에 terminate까지의 시간 </br>
cpu utilization : cpu 이용률 - cpu를 바쁘게 하는 것이 목표 </br>

1. 배치 시스템
2. 대화식 시스템
3. 실시간(Real time)시스템


### 배치 시스템
Non-preemptive
1. FCFS
   큐에 도착한 순서대로 CPU 할당
   실행 시간이 짧은 게 뒤로 가면 평균 대기 시간이 길어짐

2. Shortest Job First
   수행시간이 가장 짧다고 판단되는 작업을 먼저 수행
   FCFS보다 평균 대기 시간 감소, 짧은 작업에 유리

Preemptive
* Shortest Remaining Time Next
  큐에서 남은 잔여시간이 짧은 작업을 선택함 : turnaround time
  중간에 새로운 작업 들어오면, 새 작업의 실행시간과 현재 수행 중인 작업의 남은 시간을 비교함
