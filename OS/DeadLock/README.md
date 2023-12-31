### DeadLock의 발생조건 네가지
```
 한 번에 한 프로세스만 사용, "대기"하는 프로세스가 있어야하고, '대기'는 순환형태로
 그리고, 마지막으로, 다른 프로세스에 할당된 자원은 강제로 빼앗을 수 없어야 한다. 즉, '대기'만 하고 있어야 한다.
```
```
 정리하자면, 
 한 번에 한 프로세스만 -> 1. 상호 배제(Mutual Exclusion)
 "대기"하기 -> 2. 점유 대기(Hold and wait)
 어떤 형태로? '순환적으로' -> 3. 순환 대기(Circular wait)
 진짜 "대기"만 해야해. 뺏으면 안돼 -> 4. 비선점(No preemption)
 그리고, 이 네 가지 조건이 "모두" 발생해야 한다
```

### DeadLock 해결방법
DeadLock의 발생조건 네가지에서 하나라도 성립하지 않으면 데드락 문제 해결 가능 </br>
예방, 회피, 탐지 및 회복
예방은 당연히 하면 해결이 되고, 피하거나 다시 회복시키는 것이 있는데 그걸 정리하자면

1. 예방
   교착상태 발생조건 중 하나를 제거하면서 해결한다(자원 낭비 엄청 심함)
   * 상호배제 부정 : 여러 프로세스가 공유 자원을 사용
   * 점유대기 부정 : 프로세스 실행 전 모든 자원을 할당
   * 순환 대기 부정 : 자우너에 고유번호 할당 후 순서대로 자원 요구
   * 비선점 부정 : 자원 점유 중인 프로세스가 다른 자원을 요구할 때 가진 자원을 반납

2. 회피
   * 은행원 알고리즘
   * 자원 할당 그래프 알고리즘

3. 탐지 및 회복
   교착 상태가 되도록 허용한 다음 회복시키는 방법
   * 탐지 : 자원 할당 그래프를 통해 교착 상태를 탐지함
            자원 요청 시, 탐지 알고리즘을 실행시켜 그에 대한 오버헤드 발생함
   * 회복 : 교착 상태 일으킨 프로세스를 종료하거나, 할당된 자원을 해제시켜 회복시키는 방법


* 은행원 알고리즘이 뭔지 설명해보세요
