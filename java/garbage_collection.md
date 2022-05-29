# Garbage Collection

## Why GC?

- 가비지 컬렉터(Garbage Collector)는 더 이상 필요 없는 (쓰레기) 객체를 찾아 지우는 작업을 함
- Java에서는 개발자가 프로그램 코드로 메모리를 명시적으로 해제하지 않기 때문
- 자바의 핵심 사상
  - 저수준 세부를 일일이 신경쓰지 않는 대가로 저수준 제어권을 포기한다
  - > 자바는 블루 컬러(주로 생산직에 종사하는 육체 노동자)언어입니다.
    > 
    > 박사 학위 논문 주제가 아니라 일을 하려고 만든 언어죠
    > 
    > 제임스 고슬링(자바의 아버지)

## Garbage Collection Process

- stop-the-world
    - GC을 실행하기 위해 JVM이 애플리케이션 실행을 멈추는 것이다
    - 어떤 GC 알고리즘을 사용하더라도 stop-the-world는 발생한다.
    - 대개의 경우 GC 튜닝이란 이 stop-the-world 시간을 줄이는 것이다.
- GC 발생 시
    - GC를 실행하는 쓰레드를 제외한 나머지 쓰레드는 모두 작업을 멈춘다.
    - GC 작업을 완료한 이후에야 중단했던 작업을 다시 시작한다

## Mark and Sweep Algorithm

- 자바의 GC 알고리즘의 기본
- Mark
  - 살아있는 객체를 표시
- Sweep
  - 나머지는 쓸어담기

1. All the objects have their marked bits set to false
   1. ![All the objects have their marked bits set to false](https://media.geeksforgeeks.org/wp-content/uploads/garbageCollection.jpg)
2. Reachable objects are marked true
   1. ![Reachable objects are marked true](https://media.geeksforgeeks.org/wp-content/uploads/garbagecollect.jpg)
3. Nonreachable objects are cleared from the heap
   1. ![Nonreachable objects are cleared from the heap](https://media.geeksforgeeks.org/wp-content/uploads/nonreachable.jpg)

- [TODO] marked 값이 잘못 적용되어있음. 수정 필요

## weak generational hypothesis

- Garbage Collection 대전제
    1. 대부분의 객체는 금방 접근 불가능 상태(unreachable)가 된다.
    2. 오래된 객체에서 젊은 객체로의 참조는 아주 적게 존재한다.

## Garbage Colletion 물리적 공간

- weak generational hypothesis를 참고하여 HotSpot VM에서는 크게 2개로 물리적 공간을 나누었다.
- ![그림 1 GC 영역 및 데이터 흐름도](https://d2.naver.com/content/images/2015/06/helloworld-1329-1.png)
  - 그림 1 GC 영역 및 데이터 흐름도

1. Young 영역(Young Generation 영역)
    1. 새롭게 생성한 객체의 대부분이 여기에 위치한다.
    2. 대부분의 객체가 금방 접근 불가능 상태가 되기 때문에 매우 많은 객체가 Young 영역에 생성되었다가 사라진다.
    3. 이 영역에서 객체가 사라질때 __Minor GC__ 가 발생한다고 말한다.
2. Old 영역(Old Generation 영역)
    1. 접근 불가능 상태로 되지 않아 Young 영역에서 살아남은 객체가 여기로 복사된다.
    2. 대부분 Young 영역보다 크게 할당하며, 크기가 큰 만큼 Young 영역보다 GC는 적게 발생한다.
    3. 이 영역에서 객체가 사라질 때 __Major GC__(혹은 __Full GC__)가 발생한다고 말한다.
3. Permanent Generation 영역(= Perm 영역, Method Area)
   1. 객체나 억류(intern)된 문자열 정보를 저장하는 곳
   2. Old 영역에서 살아남은 객체가 영원히 남아 있는 곳은 절대 아니다.
   3. 이 영역에서 GC가 발생할 수도 있는데, 여기서 GC가 발생해도 __Major GC__ 의 횟수에 포함된다.

- "Old 영역에 있는 객체가 Young 영역의 객체를 참조하는 경우가 있을 때에는 어떻게 처리될까?"
  - weak generational hypothesis 2
    - 오래된 객체에서 젊은 객체로의 참조는 아주 적게 존재한다. 
  - Young 영역의 GC를 실행할 때 Old 영역에 있는 객체가 Young 영역의 객체를 참조하는 경우에 해당하는 Young 객체는 GC를 제외
  - Old 영역에는 512바이트의 덩어리(chunk)로 되어 있는 카드 테이블(card table)이 존재한다.
    - 카드 테이블에는 Old 영역에 있는 객체가 Young 영역의 객체를 참조할 때마다 정보가 표시된다.
    - Young 영역의 GC를 실행할 때에는 Old 영역에 있는 모든 객체의 참조를 확인하지 않고, 이 카드 테이블만 뒤져서 GC 대상인지 식별한다.
    - 카드 테이블은 write barrier를 사용하여 관리한다.
      - write barrier는 Minor GC를 빠르게 할 수 있도록 하는 장치이다.
      - write barrirer때문에 약간의 오버헤드는 발생하지만 전반적인 GC 시간은 줄어들게 된다.
  - ![그림 2 카드 테이블 구조](https://d2.naver.com/content/images/2015/06/helloworld-1329-2.png)
    - 그림 2 카드 테이블 구조

## Young 영역의 구성

## Old 영역에 대한 GC

## Serial GC (-XX:+UseSerialGC)

## Parallel GC (-XX:+UseParallelGC)

## Parallel Old GC(-XX:+UseParallelOldGC)

## CMS GC (-XX:+UseConcMarkSweepGC)

## G1 GC

## 참고

- [https://d2.naver.com/helloworld/1329](https://d2.naver.com/helloworld/1329)
- [https://www.icatpark.com/entry/JVM-Garbage-Collection-Basic?category=632984](https://www.icatpark.com/entry/JVM-Garbage-Collection-Basic?category=632984)
- [https://www.geeksforgeeks.org/mark-and-sweep-garbage-collection-algorithm/](https://www.geeksforgeeks.org/mark-and-sweep-garbage-collection-algorithm/)
- [https://www.geeksforgeeks.org/garbage-collection-java/](https://www.geeksforgeeks.org/garbage-collection-java/)
- - [https://www.educative.io/courses/a-quick-primer-on-garbage-collection-algorithms/jy6v](https://www.educative.io/courses/a-quick-primer-on-garbage-collection-algorithms/jy6v)