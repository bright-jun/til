# conflict

- `git`이 혼자서 `merge`할 수 없는 문제를 사람에게 위임하는 **기능**
- **장애가 아니다**

## 3 way merge

- 3 way
  - `commit_0`(base)
  - `commit_1`
  - `commit_2` 
- merge
  - `commit_0` -> `commit_1`으로의 변경분
  - `commit_0` -> `commit_2`으로의 변경분
  - 이 두개를 `merge`(전부 반영)
- `merge` 과정에서 `conflict`(겹치는 경우)가 생길 수 있음
  - 두개의 변경분 중 어떤 변경분을 선택하여 반영할 지 `git`은 결정할 수 없음
  - 사람에게 위임 `git conflict`

## 발생하는 경우

- [merge](./merge.md)
  - 전체 변경분을 가져옴
- [cherry-pick](./cherry-pick.md)
  - 특정 commit 에 해당하는 변경분만 가져옴
- [rebase](./rebase.md)
  - base commit 부터 rebase target commit까지 `cherry-pick`를 수행하여 변경분을 가져옴
  - branch 직렬화를 함
- [revert](./revert.md)
  - 특정 commit 에 해당하는 변경분만 반대로 가져옴

## 참고

- [git conflict - 알면 기능, 모르면 사고](https://www.youtube.com/watch?v=wVUnsTsRQ3g)