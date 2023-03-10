# 1장 설계와 아키텍처란?

## 설계(design) vs 아키텍처(architecture)

- 설계(design)
    - 저수준의 구조 또는 결정 사항 등을 의미할 때 사용
- 아키텍처(architecture)
    - 저수준의 세부 사항과는 분리된 고수준의 무언가를 가리킬 때 사용

둘 사이에는 아무런 차이가 없다.

전체 설계의 구성요소에는 저수준의 세부 사항, 고수준의 결정 사항이 모두 포함되어 있기 때문이다.

고수준에서 저수준으로 향하는 의사결정의 연속성만이 있을 뿐이다.

## 목표는?

> 소프트웨어 아키텍처의 목표는 필요한 시스템을 만들고 유지보수하는 데 투입되는 인력을 최소화하는 데 있다.

- 설계 품질의 척도 = 고객의 요구를 만족시키는 데 드는 비용을 재는 척도
- 비용이 낮으며, 시스템의 수명이 다할 때까지 낮게 유지할 수 있으면 좋은 설계
- 새로운 기능을 출시할 때마다 비용이 증가한다면 나쁜 설계

> 좋은 설계란 이처럼 단순명료하다.

## 사례 연구

- 출시일 - 직원 수
    - 정비례 함수
- 출시일 - 코드 라인 생산성
    - 수렴하는 로그함수
- 출시일 - 코드 라인당 비용
    - 정비례 함수

여덟 번째 출시한 제품의 코드는 처음 제품보다 40배나 더 많은 비용이 들어감.

WHY?

## 엉망진창이 되어 가는 신호

- 출시일 - 개발자의 생산성
    - 100%에서 시작해서 0%로 수렴하는 함수

개발자의 노력은 기능 개발보다는 엉망이 된 상황에 대처하는 데 소모되기 시작한다.

## 경영자의 시각

- 출시일 - 월 인건비
    - 정비례 함수

- 초기 출시일
    - 수십만 달러의 비용으로 많은 기능 탑재
- 마지막 출시일
    - 2천만 달러를 들이고도 얻은 게 거의 없음

## 무엇이 잘못되었나?

> 느려도 꾸준하면 이긴다.

> 발 빠른 자가 경주에 이기는 것도 아니며, 힘센 자가 싸움에서 이기는 것도 아니다.

> 급할수록 돌아가라

- 이터레이션 - 걸린 시간, TDD 적용 여부
    - TDD를 적용하면 그렇지 않은 경우보다 작업속도가 오히려 빨라진다.
    - 심지어 여러 번 동일한 반복을 거친 후의 작업이라 하더라도

> 빨리 가는 유일한 방법은 제대로 가는 것이다.

### 생산성 감소, 비용 증가 현상을 되돌릴 수 있는 유일한 방법

- 개발자로 하여금 토끼처럼 과신하려는 믿음을 버리고, 만들어 낸 엉망진창인 코드를 개발자가 책임지도록 하는 것뿐

다시 처음부터 설계하면 되지 않는가?
> 자신을 과신한다면 재설계하더라도 원래의 프로젝트와 똑같이 엉망으로 내몰린다.

## 결론

- 어떤 경우라도 개발 조직이 할 수 있는 최고의 선택지
    - 조직에 스며든 과신을 인지하여 방지
    - 소프트웨어 아키텍처의 품질을 심각하게 고민하기 시작하는 것

- 앞으로
    - 훌륭하고 깔끔한 아키텍처와 설계가 무엇인지 설명한다
    - 소프트웨어 개발자가 장기간에 걸쳐 수익을 창출하는 시스템을 만들 수 있도록 한다.