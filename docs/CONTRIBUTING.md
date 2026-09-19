# 협업 가이드

## GitHub Flow

`main`을 항상 병합 가능한 상태로 유지하고 작업마다 짧은 브랜치를 만든다.
모든 변경은 PR과 팀원 리뷰를 거쳐 `main`에 병합한다.
작은 단위로 자주 병합하면 충돌과 변경 범위를 함께 줄일 수 있다.

## 작업 순서

1. 최신 `main`에서 작업 브랜치를 만든다.
2. 한 가지 목적의 변경을 작은 커밋으로 작성한다.
3. 브랜치를 push하고 PR을 연다.
4. 본인이 아닌 팀원에게 리뷰를 요청한다.
5. 리뷰를 반영한 커밋과 답글을 남긴다.
6. 승인 후 PR로 `main`에 병합한다.

브랜치 이름은 `<type>/<short-description>` 형식을 사용한다.

```text
feat/add-score-command
fix/empty-name
docs/commit-convention
```

## 커밋 메시지 규칙

제목은 `<type>[/<scope>]: <summary>` 형식을 사용한다.

| type | 용도 |
| --- | --- |
| `feat` | 새로운 기능 |
| `fix` | 버그 수정 |
| `docs` | 문서 변경 |
| `refactor` | 동작을 바꾸지 않는 코드 정리 |
| `test` | 테스트 추가 또는 수정 |
| `chore` | 설정, 빌드, 저장소 관리 |

- 제목은 변경 내용을 구체적으로 나타낸다.
- `test commit`, `update`처럼 의미가 드러나지 않는 제목은 사용하지 않는다.
- 본문에는 변경 이유와 필요한 배경을 적는다.
- 서로 다른 목적의 변경은 별도 커밋으로 나눈다.

```text
docs/CONTRIBUTING.md: add commit conventions

Document the message format used by the team so that commit history is
consistent and searchable.

Signed-off-by: JaeHoon Lee <dlwognsdc610@gmail.com>
```

`Reviewed-by` trailer는 실제로 해당 변경을 검토한 사람의 동의를 받은
경우에만 추가한다. 과제의 코드 리뷰 증빙은 trailer가 아니라 GitHub PR의
review와 실질적인 코멘트 링크로 남긴다.

## PR과 코드 리뷰

PR 본문에는 다음 세 항목을 작성한다.

- `What`: 무엇을 변경했는가
- `Why`: 왜 이 변경이 필요한가
- `How to Test`: 변경을 어떻게 확인할 수 있는가

세 항목 중 하나라도 빠졌다면 review 전에 작성자에게 보완을 요청한다.

PR과 리뷰 링크는 루트의 [`SUBMISSION.md`](../SUBMISSION.md)에 기록한다.

## 충돌과 히스토리

- `main`을 포함한 공유 브랜치에서 임의로 history를 다시 쓰지 않는다.
- force push와 rebase는 영향을 받는 팀원 전원의 합의 후에만 수행한다.
- 충돌 해결 과정은 [`conflict-resolution.md`](conflict-resolution.md)에
  원인, 선택, 검증과 함께 기록한다.
- amend, reset, revert, stash 실습은
  [`troubleshooting-log.md`](troubleshooting-log.md)에 기록한다.
