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
    1. 응집도, 캡슐화
        1. 모든 클래스는 하나의 책임만 가지며, 클래스는 그 책임을 완전히 캡슐화해야 함을 일컫는다.
        2. 특정 모듈의 기능이 (편집 + 출력)이면, 편집에대한 책임, 출력에 대한 책임을 모두 가지고있기에 SRP 위반이다.
        3. 편집기능을 변경하면 출력기능에도 영향을 줄 위험이 있기 때문.
2. OCP(Open-Closed Principle, 개방 폐쇄 원칙)
   > "소프트웨어 요소는 확장에는 열려 있으나 변경에는 닫혀 있어야 한다."
    1. 소프트웨어 개발 작업에 이용된 많은 모듈 중에 하나에 수정을 가할 때 그 모듈을 이용하는 다른 모듈을 줄줄이 고쳐야 한다면, 이와 같은 프로그램은 수정하기가 어렵다.
       개방-폐쇄 원칙은 시스템의 구조를 올바르게 재조직(리팩토링)하여 나중에 이와 같은 유형의 변경이 더 이상의 수정을 유발하지 않도록 하는 것이다. 개방-폐쇄 원칙이 잘
       적용되면, 기능을 추가하거나 변경해야 할 때 이미 제대로 동작하고 있던 원래 코드를 변경하지 않아도, 기존의 코드에 새로운 코드를 추가함으로써 기능의 추가나 변경이
       가능하다.
    2. 확장에 대해 열려 있다.
        1. 이것은 모듈의 동작을 확장할 수 있다는 것을 의미한다. 애플리케이션의 요구 사항이 변경될 때, 이 변경에 맞게 새로운 동작을 추가해 모듈을 확장할 수 있다.
           즉, 모듈이 하는 일을 변경할 수 있다.
    3. 수정에 대해 닫혀 있다
        1. 모듈의 소스 코드나 바이너리 코드를 수정하지 않아도 모듈의 기능을 확장하거나 변경할 수 있다. 그 모듈의 실행 가능한 바이너리 형태나 링크 가능한 라이브러리(
           예를 들어 윈도의 DLL이나 자바의 .jar)를 건드릴 필요가 없다.
3. ISP(Interface segregation principle, 인터페이스 분리 원칙)
   > "특정 클라이언트를 위한 인터페이스 여러 개가 범용 인터페이스 하나보다 낫다." - 로버트 마틴
    1.
4. LSP(Liskov Substitution Principle, 리스코프 치환 원칙)
   > "프로그램의 객체는 프로그램의 정확성을 깨뜨리지 않으면서 하위 타입의 인스턴스로 바꿀 수 있어야 한다."
    1.
6. DIP(Dependency Inversion Principle, 의존 역전 원칙)
   > 프로그래머는 "추상화에 의존해야지, 구체화에 의존하면 안된다." - 로머트 마틴
    1.

## 참고

- [https://ko.wikipedia.org/wiki/SOLID_(%EA%B0%9D%EC%B2%B4_%EC%A7%80%ED%96%A5_%EC%84%A4%EA%B3%84)](https://ko.wikipedia.org/wiki/SOLID_(%EA%B0%9D%EC%B2%B4_%EC%A7%80%ED%96%A5_%EC%84%A4%EA%B3%84))
    - [https://ko.wikipedia.org/wiki/%EB%8B%A8%EC%9D%BC_%EC%B1%85%EC%9E%84_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EB%8B%A8%EC%9D%BC_%EC%B1%85%EC%9E%84_%EC%9B%90%EC%B9%99?tableofcontents=0)
    - [https://ko.wikipedia.org/wiki/%EA%B0%9C%EB%B0%A9-%ED%8F%90%EC%87%84_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EA%B0%9C%EB%B0%A9-%ED%8F%90%EC%87%84_%EC%9B%90%EC%B9%99?tableofcontents=0)
    - [https://ko.wikipedia.org/wiki/%EB%A6%AC%EC%8A%A4%EC%BD%94%ED%94%84_%EC%B9%98%ED%99%98_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EB%A6%AC%EC%8A%A4%EC%BD%94%ED%94%84_%EC%B9%98%ED%99%98_%EC%9B%90%EC%B9%99?tableofcontents=0)
    - [https://ko.wikipedia.org/wiki/%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4_%EB%B6%84%EB%A6%AC_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EC%9D%B8%ED%84%B0%ED%8E%98%EC%9D%B4%EC%8A%A4_%EB%B6%84%EB%A6%AC_%EC%9B%90%EC%B9%99?tableofcontents=0)
    - [https://ko.wikipedia.org/wiki/%EC%9D%98%EC%A1%B4%EA%B4%80%EA%B3%84_%EC%97%AD%EC%A0%84_%EC%9B%90%EC%B9%99?tableofcontents=0](https://ko.wikipedia.org/wiki/%EC%9D%98%EC%A1%B4%EA%B4%80%EA%B3%84_%EC%97%AD%EC%A0%84_%EC%9B%90%EC%B9%99?tableofcontents=0)
- [https://mangkyu.tistory.com/194](https://mangkyu.tistory.com/194)
- [https://huisam.tistory.com/entry/SRP?category=705896](https://huisam.tistory.com/entry/SRP?category=705896)
- [https://huisam.tistory.com/entry/OCP?category=705896](https://huisam.tistory.com/entry/OCP?category=705896)
- [https://huisam.tistory.com/entry/LSP?category=705896](https://huisam.tistory.com/entry/LSP?category=705896)
- [https://huisam.tistory.com/entry/ISP?category=705896](https://huisam.tistory.com/entry/ISP?category=705896)
- [https://huisam.tistory.com/entry/DIP?category=705896](https://huisam.tistory.com/entry/DIP?category=705896)
- [https://velog.io/@ygh7687/OOP%EC%9D%98-5%EC%9B%90%EC%B9%99%EA%B3%BC-4%EA%B0%80%EC%A7%80-%ED%8A%B9%EC%84%B1](https://velog.io/@ygh7687/OOP%EC%9D%98-5%EC%9B%90%EC%B9%99%EA%B3%BC-4%EA%B0%80%EC%A7%80-%ED%8A%B9%EC%84%B1)