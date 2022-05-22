# OOP(Object-Oriented Programming, 객체 지향 프로그래밍)

## OOP 의 4가지 특징

1. 캡슐화
    1.
2. 상속
    1.
3. 추상화
    1.
4. 다형성
    1.

# SOLID (객체 지향 설계 원칙)

> 컴퓨터 프로그래밍에서 SOLID란 로버트 마틴이 2000년대 초반에 명명한 객체 지향 프로그래밍 및 설계의 다섯 가지 기본 원칙을 마이클 페더스가 두문자어 기억술로 소개한 것이다.

1. SRP(Single Responsibility Principle, 단일 책임의 원칙)
   > 한 클래스는 하나의 책임만 가져야 한다.
    1. 모든 클래스는 하나의 책임만 가지며, 클래스는 그 책임을 완전히 캡슐화해야 함을 일컫는다.
    2. 특정 모듈의 기능이 (편집 + 출력)이면, 편집에대한 책임, 출력에 대한 책임을 모두 가지고있기에 SRP 위반이다.
    3. 편집기능을 변경하면 출력기능에도 영향을 줄 위험이 있기 때문.
    4. 적용 시 장점
        1. 높은 응집도, 낮은 결합도, 캡슐화
            1. 한 클래스가 가지고 있는 의존관계가 낮아지면 유지보수성이 올라감
2. OCP(Open-Closed Principle, 개방 폐쇄 원칙)
   > "소프트웨어 요소는 확장에는 열려 있으나 변경에는 닫혀 있어야 한다."
    1. 소프트웨어 개발 작업에 이용된 많은 모듈 중에 하나에 수정을 가할 때 그 모듈을 이용하는 다른 모듈을 줄줄이 고쳐야 한다면, 이와 같은 프로그램은 수정하기가 어렵다.
       개방-폐쇄 원칙은 시스템의 구조를 올바르게 재조직(리팩토링)하여 나중에 이와 같은 유형의 변경이 더 이상의 수정을 유발하지 않도록 하는 것이다. 개방-폐쇄 원칙이 잘
       적용되면, 기능을 추가하거나 변경해야 할 때 이미 제대로 동작하고 있던 원래 코드를 변경하지 않아도, 기존의 코드에 새로운 코드를 추가함으로써 기능의 추가나 변경이
       가능하다.
    2. 확장에 대해 열려 있다.
        1. 이것은 모듈의 동작을 확장할 수 있다는 것을 의미한다. 애플리케이션의 요구 사항이 변경될 때, 이 변경에 맞게 새로운 동작을 추가해 모듈을 확장할 수 있다.
           즉, 모듈이 하는 일을 변경할 수 있다.
        2. urlMapping 모듈에서 urlMapping 함수를 수정하지 않고 mapping-url들을 __추가할 수 있다__.
        3. repository 인터페이스를 __수정하지 않고__ repository 구현을 __바꿀 수 있다__.
    3. 수정에 대해 닫혀 있다
        1. 모듈의 소스 코드나 바이너리 코드를 수정하지 않아도 모듈의 기능을 확장하거나 변경할 수 있다. 그 모듈의 실행 가능한 바이너리 형태나 링크 가능한 라이브러리(
           예를 들어 윈도의 DLL이나 자바의 .jar)를 건드릴 필요가 없다.
        2. urlMapping 모듈에서 urlMapping 함수를 __수정하지 않고__ mapping-url들을 추가할 수 있다.
        3. repository 인터페이스를 __수정하지 않고__ repository 구현을 바꿀 수 있다.
    4. 적용 시 장점
        1. 유지보수성
        2. 확장성
3. LSP(Liskov Substitution Principle, 리스코프 치환 원칙)
   > "프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 한다."
    1. if class `Square` extends `Rectangle`, 필요한 프로그램의 속성(정확성, 수행하는 업무 등)의 변경 없이 자료형 `Rectangle`의
       객체를 자료형 `Square`의 객체로 교체(치환) 할 수 있어야 한다는 원칙이다.
    2. 자식 클래스가 항상 부모 클래스의 역할을 포함(=충실히 수행)
    3. 행동적 하위형화
        1. `q(x)`를 자료형 `T`의 객체 `x`에 대해 증명할 수 있는 속성이라 하자. 그렇다면 `S`가 `T`의 하위형이라면 `q(y)`는 자료형 `S`의
           객체 `y`에 대해 증명할 수 있어야 한다.
        2. `getArea(rectangle)`를 자료형 `Rectangle`의 객체 `rectangle`에 대해 증명할 수 있는 속성이라 하자. 그렇다면 `Square`
           가 `Rectangle`의 하위형이라면 `getArea(square)`는 자료형 `Square`의 객체 `square`에 대해 증명할 수 있어야 한다.
        3. 이력 제약 조건 (이력 규칙). 객체는 그 자신의 메서드를 통해서만 수정(캡슐화)할 수 있는 것으로 간주된다. 하위형은 상위형에 없는 메서드를 추가할 수 있기
           때문에, 추가된 메서드를 통해 상위형에서 허용하지 않는 하위형 상태의 변경을 일으킬 수 있다. 리스코프와 윙이 도입한 참신한 요소인 이력 제약조건은 이를
           방지한다. 이 제약조건의 위반을 정의하기 위해 변경 가능 지점을 변경 불가 지점의 하위형으로 정의해 볼 수 있다. 변경 불가 지점의 이력은 생성한 이후 상태가
           항상 동일해야 하기 때문에, 앞에서 가정한 정의는 이력 제약조건의 위반이며, 따라서 일반적으로 변경 가능 위치를 이력에 포함할 수 없다. 반면 하위형에 추가된
           필드는 상위형의 메서드로 감시할 대상이 아니기 때문에 안정적으로 수정할 수 있다. 따라서 고정된 점에서 고정된 중심점과 변경 가능한 반지름을 가진 원을 LSP를
           위반하지 않고 유도할 수 있다.
    4. 적용 시 장점
        1. TODO https://www.baeldung.com/java-liskov-substitution-principle
4. ISP(Interface segregation principle, 인터페이스 분리 원칙)
   > "특정 클라이언트를 위한 인터페이스 여러 개가 범용 인터페이스 하나보다 낫다." - 로버트 마틴
    1. 클라이언트가 자신이 이용하지 않는 메서드에 의존하지 않아야 한다는 원칙
    2. 큰 덩어리의 인터페이스들을 구체적이고 작은 단위들로 분리시킴으로써 클라이언트들이 꼭 필요한 메서드들만 이용할 수 있게 한다.
    3. 적용 시 장점
        1. SRP 준수
            1. 내부 의존성을 약화, 클래스의 책임 덜어줌
            2. 유지보수성, 확장성
                1. 리팩토링, 수정, 재배포를 쉽게 할 수 있다.
5. DIP(Dependency Inversion Principle, 의존 역전 원칙)
   > 프로그래머는 "추상화에 의존해야지, 구체화에 의존하면 안된다." - 로머트 마틴
    1. 상위 계층(정책 결정)이 하위 계층(세부 사항)에 의존하는 전통적인 의존관계를 반전(역전)시킴으로써 상위 계층이 하위 계층의 구현으로부터 독립되게 할 수 있다.
        1. 상위 모듈은 하위 모듈에 의존해서는 안된다. 상위 모듈과 하위 모듈 모두 추상화에 의존해야 한다.
            1. 이 원칙은 '상위와 하위 객체 모두가 동일한 추상화에 의존해야 한다'는 객체 지향적 설계의 대원칙을 제공한다
        2. 추상화는 세부 사항에 의존해서는 안된다. 세부사항이 추상화에 의존해야 한다.
    2. 의존 관계를 맺을 때 __변화하기 쉬운 것__(__구체화__)에 의존하기보다는, __변화하지 않는 것__(__추상화__)에 의존하라는 원칙
    3. 적용 시 장점
       1. 느슨한 결합도
          1. 확장성
          2. 다양한 설계, 복잡한 설계 가능

## 참고

- [https://ko.wikipedia.org/wiki/SOLID_(%EA%B0%9D%EC%B2%B4_%EC%A7%80%ED%96%A5_%EC%84%A4%EA%B3%84)](https://ko.wikipedia.org/wiki/SOLID_(%EA%B0%9D%EC%B2%B4_%EC%A7%80%ED%96%A5_%EC%84%A4%EA%B3%84))
    - [https://ko.wikipedia.org/wiki/%EB%8B%A8%EC%9D%BC_%EC%B1%85%EC%9E%84_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EB%8B%A8%EC%9D%BC_%EC%B1%85%EC%9E%84_%EC%9B%90%EC%B9%99?tableofcontents=0)
    - [https://ko.wikipedia.org/wiki/%EA%B0%9C%EB%B0%A9-%ED%8F%90%EC%87%84_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EA%B0%9C%EB%B0%A9-%ED%8F%90%EC%87%84_%EC%9B%90%EC%B9%99?tableofcontents=0)
    - [https://ko.wikipedia.org/wiki/%EB%A6%AC%EC%8A%A4%EC%BD%94%ED%94%84_%EC%B9%98%ED%99%98_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EB%A6%AC%EC%8A%A4%EC%BD%94%ED%94%84_%EC%B9%98%ED%99%98_%EC%9B%90%EC%B9%99?tableofcontents=0)
        - [https://www.baeldung.com/java-liskov-substitution-principle](https://www.baeldung.com/java-liskov-substitution-principle)
        - [https://en.wikipedia.org/wiki/Circle%E2%80%93ellipse_problem](https://en.wikipedia.org/wiki/Circle%E2%80%93ellipse_problem)
    - [https://ko.wikipedia.org/wiki/%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4_%EB%B6%84%EB%A6%AC_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4_%EB%B6%84%EB%A6%AC_%EC%9B%90%EC%B9%99?tableofcontents=0)
    - [https://ko.wikipedia.org/wiki/%EC%9D%98%EC%A1%B4%EA%B4%80%EA%B3%84_%EC%97%AD%EC%A0%84_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EC%9D%98%EC%A1%B4%EA%B4%80%EA%B3%84_%EC%97%AD%EC%A0%84_%EC%9B%90%EC%B9%99?tableofcontents=0)
- [https://mangkyu.tistory.com/194](https://mangkyu.tistory.com/194)
- [https://huisam.tistory.com/entry/SRP?category=705896](https://huisam.tistory.com/entry/SRP?category=705896)
- [https://huisam.tistory.com/entry/OCP?category=705896](https://huisam.tistory.com/entry/OCP?category=705896)
- [https://huisam.tistory.com/entry/LSP?category=705896](https://huisam.tistory.com/entry/LSP?category=705896)
- [https://huisam.tistory.com/entry/ISP?category=705896](https://huisam.tistory.com/entry/ISP?category=705896)
- [https://huisam.tistory.com/entry/DIP?category=705896](https://huisam.tistory.com/entry/DIP?category=705896)
- [https://velog.io/@ygh7687/OOP%EC%9D%98-5%EC%9B%90%EC%B9%99%EA%B3%BC-4%EA%B0%80%EC%A7%80-%ED%8A%B9%EC%84%B1](https://velog.io/@ygh7687/OOP%EC%9D%98-5%EC%9B%90%EC%B9%99%EA%B3%BC-4%EA%B0%80%EC%A7%80-%ED%8A%B9%EC%84%B1)