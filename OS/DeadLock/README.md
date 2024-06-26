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
   * 탐지 : 자원 할당 그래프를 통해 교착 상태(데드락)를 탐지함
            자원 요청 시, 탐지 알고리즘을 실행시켜 그에 대한 오버헤드 발생함
   * 회복 : 교착 상태 일으킨 프로세스를 종료하거나, 할당된 자원을 해제시켜 회복시키는 방법


* <b>은행원 알고리즘</b>이 뭔지 설명해보세요 </br>
```
 DeadLock 해결 방법 중 회피에 해당하는 것으로, 교착상태가 되지 않도록 회피하는 자원 할당 방식입니다.
은행원 알고리즘은 DeadLock에 빠질 가능성이 있는지 판단하기 위해 상태를 safe state와 unsafe state로 나누고
은행원 알고리즘에서 운영체제는 안전 상태를 유지 할 수 있는 요구만 수락하고 불안전 상태를 초래할 사용자의 요구는 나중에 만족될 수 있을때까지 계속 거절하게 됩니다.
 즉, 은행으로 비유하자면, 전액을 빌려 줄 수 있는 대출부터 차근차근 해 주는 프로세스입니다.
이러한 알고리즘의 단점으로는 할당할 수 있는 자원의 수가 일정해야 하며 항상 불안전 상태를 방지해야 하므로 자원의 이용도가 낮아지게 됩니다. 따라서 현재 채택하고 있는 방식은 아닙니다.
```

 1) 안전 상태
    각 프로세스가 요구한 만큼 차례차례 필요한 자원을 할당할 수 있는 상태
 2) 불안전 상태
    이미 상당한 자원이 프로세스에 할당된 상태로, 남은 자원으로 프로세스가 요구하는 자원을 충당할 수 없는 경우인데, 불안전 상태가 곧 DeadLock을 의미하진 않는다.
    이미 할당된 프로세스로부터 자원을 회수해서 불안전 상태를 해소할 수 있으며, 다시 안전 상태로 돌아갈 수 있다. 만약 자원을 회수할 수 없다면 불안전 상태는 DeadLock으로 굳어지게 된다.

    [참고블로그](https://star7sss.tistory.com/939)
    
