### 스케줄링

preemptive, Non-preemptive


```
시스템 환경에 따라 분류해보시오
**Scheduling algorithm**
throughput : 단위 시간에 완료된 job의 갯수
turnaround time : job이 system에 submit된 다음에 terminate까지의 시간
cpu utilization : cpu 이용률 - cpu를 바쁘게 하는 것이 목표
```
1. 배치 시스템
2. 대화식 시스템
3. 실시간(Real time)시스템
</br>

### 배치 시스템
프로세스 종료까지 사용자 interact가 없는 시스템 </br>
Process switch는 줄고, 성능이 향상된다 </br>
그러나 프로세스 자체를 수행하는 데에 CPU time을 많이 쓰게 된다 </br>

Non-preemptive
1. FCFS
   큐에 도착한 순서대로 CPU 할당
   실행 시간이 짧은 게 뒤로 가면 평균 대기 시간이 길어짐

2. Shortest Job First
   수행시간이 가장 짧다고 판단되는 작업을 먼저 수행
   FCFS보다 평균 대기 시간 감소, 짧은 작업에 유리

preemptive
* Shortest Remaining Time Next </br>
  큐에서 남은 잔여시간이 짧은 작업을 선택함 : turnaround time </br>
  중간에 새로운 작업 들어오면, 새 작업의 실행시간과 현재 수행 중인 작업의 남은 시간을 비교함 </br>
</br>

### 대화식 시스템
수행 중 사용자와 interact하는 시스템 </br>
preemptive 알고리즘이 주요 사용된다 </br>
한 프로세스에 많은 시간을 주면 사용자가 interact할 수 없으므로 preemptive를 사용함으로써 </br>
빠르게 context switch를 도모하여 한 프로세스의 CPU독점을 막는다

1. Round Robin 스케줄링 </br>
   FCFS에 의해 프로세스들이 보내지면 각 프로세스는 동일한 시간의 Time Quantum만큼 CPU를 할당받음 </br>
   Time Quantum </br>
   Time Slice </br>
2. 우선순위 스케줄링 </br>
   정적/동적으로 우선순위를 부여하여 우선순윙가 높은 순서대로 처리 </br> 
   우선 순위가 낮은 프로세스가 무한정 기다리는 starvation이 생길 수 있음 </br>
   aging 방법으로 starvation 문제 해결 가능 </br>

3. Multiple Queues 다단계 큐
   CTSS
   XDS
4. Shortest Process Next
5. Guaruanteed Scheduling 보장 스케줄링
6. Lottery Scheduling 복권 스케줄링
7. Fair-Share Scheduling 공평-몫 스케줄링

### 실시간(Real-time) 시스템
어떤 프로세스들은 오랫동안 수행되지 않고 자신의 일을 빠르게 수행한 뒤 block되기 때문에 preemption이 때때로 필요하지 않다
1) static : 스케줄링 결정을 시스템 시작 전에 하는 것
2) dynamic: 실행 중에 스케줄링 결정을 내리는 것
