# Concurrency(동시성) vs Parallelism(병렬성)

## Concurrency(동시성) 

- 두 개 이상의 작업이 겹치는 기간에 시작, 실행 및 완료가 가능
- 적어도 두 개의 스레드가 진행 중일 때 존재하는 조건
  - 가상 병렬 처리의 한 형태로 시간 분할(time slicing)을 포함할 수 있는 보다 일반적인 형태의 병렬 처리
- 동시성의 주요 목표는 유휴 시간을 최소화하여 CPU를 최대화하는 것
  -  현재 스레드 또는 프로세스가 입출력 작업, 데이터베이스 트랜잭션 또는 외부 프로그램 실행을 기다리는 동안 다른 프로세스 또는 스레드가 CPU 할당을 받습니다.

### 작동방식

![](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/concurrency_-1024x593-1-768x445.png)

### 예시

- 단일코어 시스템에서 멀티태스킹

### 주의사항

- 동시 환경을 신중하게 설계하지 않으면 교착 상태, 경쟁 조건 또는 기아 상태가 발생할 수 있습니다.

## Parallelism(병렬성)

- 작업이 동시에 실행
- 두 개 이상의 스레드가 동시에 실행될 때 발생하는 조건
- 동일한 시간에 프로그램의 독립적인 작업을 실행할 수 있는 기능
  - 동시성 작업과 달리 다른 프로세서 코어, 다른 프로세서 또는 분산 시스템이 될 수 있는 완전히 다른 컴퓨터에서 동시에 실행할 수 있습니다.

### 작동방식

![](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/parallelism-1024x639-1.png)

### 예시

- 멀티코어 프로세서

### 주의사항

- 어디서 멈추고 무엇을 공유해야 하는지 알아야 합니다. 그렇지 않으면 메모리 손상, 누수 또는 오류가 발생할 수 있습니다.

## Concurrency(동시성) vs Parallelism(병렬성)

![](https://www.baeldung.com/wp-content/uploads/sites/4/2022/01/vs-1024x462-1.png)

## 참고

- [https://seamless.tistory.com/42](https://seamless.tistory.com/42)
- [What is the difference between concurrency and parallelism?](https://stackoverflow.com/questions/1050222/what-is-the-difference-between-concurrency-and-parallelism)
- [Sun's Multithreaded Programming Guide](https://docs.oracle.com/cd/E19455-01/806-5257/6je9h032b/index.html)
- [https://www.baeldung.com/cs/concurrency-vs-parallelism](https://www.baeldung.com/cs/concurrency-vs-parallelism)