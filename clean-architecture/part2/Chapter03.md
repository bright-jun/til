# 3장 패러다임 개요

## 구조적 프로그래밍(structured programming)

- 1968, 에츠허르 비버 데이크스트라(Edsger Wybe Dijkstra)에 의해 등장
    - 최초로 적용된 패러다임(최초로 만들어진 패러다임은 아님)
- 무분별한 점프(`goto` 문장)이 해롭다고 제시
- `if`/`then`/`else`, `do`/`while`/`until`과 같이 익숙한 구조로 대체

> 구조적 프로그래밍은 **제어흐름의 직접적인 전환**에 대해 규칙을 부과한다.

## 객체 지향 프로그래밍(object-oriented programming)

- 1966, 올레 요한 달(Ole Johan Dahl) 과 크리스텐 니가드(Kristen Nygaard)에 의해 등장
- 알골(ALGOL) 언어의 함수 호출 스택 프레임(stack frame)을 힙(heap)으로 옮기면, 함수 호출이 반환된 이후에도 함수에서 선언된 지역변수가 오랫동안 유지될 수
  있음을 발견.
    - 함수 : 클래스의 생성자
    - 지역 변수 : 인스턴스 변수
    - 중첩 함수 : 메서드
    - 함수 포인터를 특정 규칙에 따라 사용 : 다형성

> 객체 지향 프로그래밍은 **제어흐름의 간접적인 전환**에 대해 규칙을 부과한다.

## 함수형 프로그래밍(functional programming)

- 최근 들어서야 도입된 패러다임
    - 세 패러다임 중 가장 먼저 만들어졌다.
    - 컴퓨터 프로그래밍 자체보다 먼저 등장.
- 알론조 처치(Alonzo Church) 람다(lambda) 계산법을 발명
    - 이러한 연구 결과에 의해 직접적인 영향을 받아 만들어진 패러다임
- LISP 언어의 근간
- 불변성(immutability)
    - 심볼(symbol)의 값이 변경되지 않는다
    - 함수형 언어에는 할당문이 전혀 없다

> 함수형 프로그래밍은 **할당문**에 대해 규칙을 부과한다.

## 생각할 거리

각 패러다임은 프로그래머에게서 권한을 박탈한다. 각 패러다임은 무엇을 해야 할지를 말하기보다는 무엇을 해서는 안 되는지를 말해준다.

- 구조적 프로그래밍
    - `goto` 문 빼앗음
- 객체 지향 프로그래밍
    - 함수 포인터 빼앗음
- 함수형 프로그래밍
    - 할당문 빼앗음

이 외에 더 이상 빼앗을 것이 없다.

## 결론

- 세 가지 패러다임
    1. 구조적 프로그래밍
    2. 객체 지향 프로그래밍
    3. 함수형 프로그래밍

- 아키텍처의 큰 관심사
    1. 함수
    2. 컴포넌트 분리
    3. 데이터 관리

세 가지 패러다임과 아키텍처와 관계가 있다.

- 구조적 프로그래밍
    - 모듈의 기반 알고리즘으로 사용
- 객체 지향 프로그래밍
    - 다형성을 아키텍처 경계를 넘나들기 위한 메커니즘으로 사용
- 함수형 프로그래밍
    - 데이터의 위치와 접근 방법에 대해 규칙을 부과