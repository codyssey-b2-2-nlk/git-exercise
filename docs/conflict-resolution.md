# 충돌 해결 기록

최소 두 건을 기록하며, 그중 한 건은 양쪽 변경의 의도를 판단해야 하는
비자명 충돌이어야 한다. 단순히 충돌 표시를 지운 사실보다 왜 그 결과를
선택했는지와 어떻게 확인했는지를 남긴다.

## 사례 1 — 일반 충돌

- 일시: 2026-09-19
- 참여자: JaeHoon Lee — 충돌 재현과 해결
- 관련 브랜치와 PR: `exercise/commit-evidence`,
  `exercise/pr-evidence`; PR 없음
- 충돌 파일: `team/README.md`
- 충돌 원인: 두 브랜치가 구성원별 결과물에 연결할 증빙의 종류를 같은
  문장에서 각각 커밋 링크와 PR 링크로 바꿨다.
- 양쪽 변경의 의도: `exercise/commit-evidence`는 개별 커밋을 직접
  추적하려 했고, `exercise/pr-evidence`는 리뷰와 병합 맥락까지 남기려
  했다.
- 선택한 해결 방법과 이유: 두 링크 모두 유효한 기여 증빙이므로 한쪽을
  버리지 않고 “커밋 또는 PR 링크”로 합쳤다.
- 확인한 명령 또는 테스트: `git diff --cached --check`, conflict marker
  검색, `git show --cc --stat 2fde409`
- 해결 커밋: [`2fde409`](https://github.com/dlwognsdc610-maker/git-exercise/commit/2fde4091b1e12297a36acf60d7eb47fdaedb3b71)

## 사례 2 — 비자명 충돌

- 일시: 2026-09-19
- 참여자: JaeHoon Lee — 충돌 재현과 해결
- 관련 브랜치와 PR: `docs/pr-template`, `docs/review-scope`; PR 없음
- 충돌 파일: `docs/CONTRIBUTING.md`
- 상황: 두 브랜치가 `PR과 코드 리뷰`의 같은 문단을 서로 다른 내용으로
  바꾼 뒤 `ljh` 브랜치에서 차례로 병합했다.
- 충돌 원인: `docs/pr-template`은 PR 본문의 `What`, `Why`,
  `How to Test`를 필수화했고, `docs/review-scope`는 PR의 변경 범위와
  실질적인 리뷰 기준을 같은 hunk에 추가했다. Git은 어느 문단을 남길지
  자동으로 판단할 수 없었다.
- 해결 과정: `git diff --cc`로 양쪽 내용을 비교했다. 한쪽을 선택하는
  대신 한 PR의 목적을 먼저 제한하고, 세 가지 본문 항목을 작성한 뒤,
  리뷰어가 구체적인 근거와 제안을 남기도록 순서를 다시 구성했다.
- 결과: 두 브랜치의 요구가 중복 없이 모두 남았고 conflict marker를
  제거했다.
- 확인한 명령 또는 테스트: `git diff --check`, conflict marker 검색,
  `git log --oneline --graph --all`
- 해결 커밋: [`b2e92f2`](https://github.com/dlwognsdc610-maker/git-exercise/commit/b2e92f29cf51553baa0aeb94bf8993d66cf711e2)
- 배운 점: 같은 hunk의 충돌도 양쪽 의도가 서로 배타적이라는 뜻은 아니다.
  규칙의 적용 순서를 정하면 두 변경을 함께 보존할 수 있다.
