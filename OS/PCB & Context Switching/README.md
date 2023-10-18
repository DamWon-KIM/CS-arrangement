### Context_Switching이란?
```
주어진 상태에서 현재 사용하는 시스템의 함수 시행으로 프로세스를 전환할 때 OS에 의해 사용되는 기술로써
이전의 프로세스를 ready queue에서 기다리게 하고 상태를 저장 한 후, 다음 실행할 프로세스의 상태를 불러옵니다.
이를 통해 커널에서 여러 프로세스가 동시에 실행(multitasking)하는 것 처럼 보여집니다.

멀티 태스킹, 인터럽트, 커널 <-> 사용자모드 전환 시 발생됩니다.
```

1. 하드웨어 문맥(Hardeware Context)
2. 프로세스 주소 공간(Process Adress Space)
3. 커널 상의 문맥(Kernel Context)
   
context_switch() 함수는 현재 실행 중인 스레드의 레지스터 상태와 메모리 매핑 정보를 새로운 스레드의 정보로 교체하는 작업을 수행합니다

[참고사이트](https://jaykos96.tistory.com/34)
