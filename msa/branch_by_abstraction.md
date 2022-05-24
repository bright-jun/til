# Branch By Abstraction

- "Branch by Abstraction"은 소프트웨어 시스템에 대한 대규모 변경을 점진적으로 수행하는 기술
- 변경이 진행 중인 동안 시스템을 정기적으로 릴리스할 수 있음
    - Monolithic Architecture -> Micro Service Architecture 변경 시

- 1단계
    - ![step-1](https://martinfowler.com/bliki/images/branch-by-abstraction/step-1.png)
    - 소프트웨어 시스템의 다양한 부분이 교체하고자 하는 모듈, 라이브러리 또는 프레임워크에 의존하는 상황
    - `Client Code`
      - 소프트웨어 시스템의 다양한 부분 
    - `Flawed Supplier`
      - 교체하고자 하는 모듈, 라이브러리 또는 프레임워크
- 2단계
    - ![step-2](https://martinfowler.com/bliki/images/branch-by-abstraction/step-2.png)
    - `Abstraction Layer`을 생성
        - `Client Code`의 한 섹션과 `Flawed Supplier`간의 상호 작용을 캡처하는 역할
        - `Abstraction Layer`을 통해 전적으로 `Flawed Supplier`를 호출하도록 `Client Code`의 해당 섹션을 변경
- 3단계
    - ![step-3](https://martinfowler.com/bliki/images/branch-by-abstraction/step-3.png)
    - `Client Code`를 `Abstraction Layer`으로 점진적으로 이동
        - 최종적으로는 `Flawed Supplier`와의 모든 상호 작용이 `Abstraction Layer`에 의해 이루어질 때까지
        - `Abstraction Layer`을 통해 `Flawed Supplier`의 단위 테스트 적용 범위를 개선할 수 있게 됨
- 4단계
    - ![step-4](https://martinfowler.com/bliki/images/branch-by-abstraction/step-4.png)
    - 동일한 `Abstraction Layer`을 사용하여 `Client Code`의 한 부분에 필요한 기능을 구현하는 `New Supplier`를 구축
    - 준비가 되면 `Client Code`의 해당 섹션을 전환하여 `New Supplier`를 사용
- 5단계
    - ![step-5](https://martinfowler.com/bliki/images/branch-by-abstraction/step-5.png)
    - `Flawed Supplier`를 `New Supplier`로 점진적으로 교체
      - 모든 `Client Code`가 `New Supplier`를 사용할 때까지
      - `Flawed Supplier`가 필요하지 않으면 삭제할 수 있게 됨
      - 마이그레이션에 더 이상 필요하지 않은 `Abstraction Layer`을 삭제할 수도 있음

## 참고

- [https://martinfowler.com/bliki/BranchByAbstraction.html](https://martinfowler.com/bliki/BranchByAbstraction.html)