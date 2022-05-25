# 가변 객체, 불변 객체

## 가변 객체(Mutable Object)

- Class의 인스턴스가 생성된 이후, 내부의 상태 가변
- `ArrayList`, `HashMap`, `StringBuilder`, `StringBuffer`

## 불변 객체(Immutable_Object)

- Class의 인스턴스가 생성된 이후, 내부의 상태 불변
    - 내부 상태를 제공하는 메소드를 제공하지 않거나 방어적 복사(defensive-copy)를 통해 제공
    - 방어적 복사 : 참조(Reference)를 끊어내고, 내부를 복사하여 전달
- `String`, `Integer`, `Long`

### 장점

- 내부 상태가 불변
    - 공유하더라도 내부 상태에 대한 불변성을 보장

1. Thread-safe
    1. 공유 자원에 동시 쓰기 연산 발생하지 않음
        1. 멀티 스레드 환경에서 동기화 문제가 발생하지 않음
    2. 동기화를 고려하지 않음 -> 성능상의 이점
2. 실패 원자적인(Failure Atomic) 메소드를 만들 수 있다.
    1. 가변 객체로 작업을 하는 도중 예외가 발생하면 해당 객체가 불안정한 상태에 빠질 수 있다
    2. 불변 객체라면 어떠한 예외가 발생하여도 메소드 호출 전의 상태를 유지
3. Cache, Map, Set 등의 원소(요소)로 활용하기에 더욱 적합하다.
    1. 원소(요소)가 가변 객체라면, 변경 시 이를 갱신하는 등의 부가 작업이 필요
    2. 원소(요소)가 불변 객체라면, 한 번 데이터가 저장된 이후에 다른 작업들을 고려하지 않아도 되므로 사용하는데 용이
4. Avoid Side Effect
    1. 변수의 값이 변경되거나, 필드 값이 설정되는 등의 변화가 발생하지 않음
    2. 다른 메소드가 호출되어도 객체의 상태가 유지됨
    3. 가비지 컬렉션의 성능을 높일 수 있다
5. 다른 사람이 작성한 함수를 예측가능하며 안전하게 사용할 수 있다
    1. 불변성이 보장된 함수라면 다른 사람이 개발한 함수를 위험없이 이용
    2. 변경에 대한 불안없이 다른 사람의 코드를 이용할 수 있다
6. 가비지 컬렉션의 성능을 높일 수 있다.
    1. `Object` 타입의 `value` 객체 생성
    2. `ImmutableHolder` 타입의 컨테이너 객체 생성
    3. `ImmutableHolder`가 `value` 객체를 참조
    4. 컨테이너 객체(`ImmutableHolder`)가 살아있다는 것은 하위의 불변 객체들(`value`) 역시 처음에 할당된 상태로 참조되고 있음을 의미
    5. GC가 수행될 때, 가비지 컬렉터가 컨테이너 객체 하위의 불변 객체들은 Skip할 수 있도록 도와준다.
    6. 가비지 컬렉터가 스캔해야 되는 객체의 수가 줆
    7. 스캔해야 하는 메모리 영역과 빈도수 역시 줄어들 것이고, GC가 수행되어도 지연 시간을 줄일 수 있을 것

### 추가 개념

- 실패 원자적
    - 호출된 메서드가 실패하더라도 해당 객체는 메서드 호출 전 상태를 유지하는 특성
- 부수 효과
    - 외부의 상태를 변경하는 것 또는 함수로 들어온 인자의 상태를 직접 변경하는 것
- 순수 함수
    - 부수효과가 없는 함수
        - 어떤 함수에 동일한 인자를 주었을 때 항상 같은 값을 리턴하는 함수
        - 외부의 상태를 변경하지 않는 함수

## 참고

- Modern Java in Action, Raoul-Gabriel Urma
- [https://mangkyu.tistory.com/131](https://mangkyu.tistory.com/131)
- [https://steady-coding.tistory.com/559](https://steady-coding.tistory.com/559)
- [https://jeong-pro.tistory.com/23](https://jeong-pro.tistory.com/23)
- [https://madplay.github.io/post/strive-for-failure-atomicity](https://madplay.github.io/post/strive-for-failure-atomicity)