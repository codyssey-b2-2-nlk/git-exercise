# B2-2 제출 증빙

완료된 활동의 GitHub URL과 커밋을 기록한다. 계획이나 로컬 작업만으로
완료 처리하지 않는다.

## 저장소와 팀

- 팀 저장소: [codyssey-b2-2-nlk/git-exercise](https://github.com/codyssey-b2-2-nlk/git-exercise)
- 결과물: [`team/README.md` 팀 협업 결과](https://github.com/codyssey-b2-2-nlk/git-exercise/blob/main/team/README.md)

| 팀원 | GitHub 계정 | 기여 커밋 또는 PR |
| --- | --- | --- |
| JaeHoon Lee | `dlwognsdc610-maker` | [`ec50144` initial conventions](https://github.com/dlwognsdc610-maker/git-exercise/commit/ec50144e631db7e35a6b3cc4a29d71bcaaffcfa0) |
| 나상화 | `Sanghwa-Na` | [PR #9 팀 소개 업로드](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/9) |
| 김승현 | `nothingOld` | [PR #10 PR 템플릿 추가](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/10) |

## 요구사항 증빙

- [x] 3~5인 팀 구성과 전원의 Git 작업 참여: 위 팀원 표
- [x] 팀 저장소와 Branch Protection Rule:
  [저장소 README의 규칙](https://github.com/codyssey-b2-2-nlk/git-exercise#branch-protection-rule)
- [x] GitHub Flow 적용과 선택 이유:
  [`docs/CONTRIBUTING.md`](docs/CONTRIBUTING.md)
- [x] PR 생성과 병합 2개 이상: 아래 PR 표
- [x] 본인 PR을 제외한 실질적인 코드 리뷰 2개 이상: 아래 리뷰 표
- [x] 리뷰 반영 1회 이상: 아래 리뷰 반영 표
- [x] 커밋 메시지 컨벤션:
  [`docs/CONTRIBUTING.md`](docs/CONTRIBUTING.md)
- [x] 충돌 해결 2회 이상, 비자명 충돌 1회 포함:
  [`docs/conflict-resolution.md`](docs/conflict-resolution.md)
- [x] amend, reset --soft, revert, stash 전체 수행:
  [`docs/troubleshooting-log.md`](docs/troubleshooting-log.md)
- [x] 협업 문서 3종 작성: [`docs/`](docs/README.md)
- [x] 간단한 결과물과 팀원별 기여 커밋:
  [팀 결과물](https://github.com/codyssey-b2-2-nlk/git-exercise/blob/main/team/README.md), 위 팀원 표
- [x] Git graph:
  [`team/graph.png`](https://github.com/codyssey-b2-2-nlk/git-exercise/blob/main/team/graph.png)

### PR 생성과 병합

| PR | 작성자 | 변경 내용 | 병합 커밋 |
| --- | --- | --- | --- |
| [#1](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/1) | `dlwognsdc610-maker` | 커밋 메시지 컨벤션 추가 | [`9390e38`](https://github.com/codyssey-b2-2-nlk/git-exercise/commit/9390e388247d99b3eb5f6d01358c7d43d460368d) |
| [#2](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/2) | `nothingOld` | 협업 가이드 작성 | [`920ab14`](https://github.com/codyssey-b2-2-nlk/git-exercise/commit/920ab14709b698b17e832db36791bfa65f99e455) |

### 코드 리뷰

본인 PR에 남긴 코멘트는 세지 않는다. 구체적인 문제나 개선안을 담은
review 또는 line comment URL을 기록한다.

| 리뷰 | 리뷰어 | 대상 PR | 실질 코멘트 |
| --- | --- | --- | --- |
| [line comment](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/1#discussion_r4052294031) | `Sanghwa-Na` | [#1](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/1) | `Reviewer`와 이메일 사이 공백 추가 요청 |
| [PR comment](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/2#issuecomment-5739696585) | `dlwognsdc610-maker` | [#2](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/2) | `Signed-off-by` trailer 추가 요청 |

### 리뷰 반영

| PR | 리뷰 코멘트 | 수정 커밋 | 작성자 답글 |
| --- | --- | --- | --- |
| [#1](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/1) | [공백 추가 요청](https://github.com/codyssey-b2-2-nlk/git-exercise/pull/1#discussion_r4052294031) | [`ec50144`](https://github.com/dlwognsdc610-maker/git-exercise/commit/ec50144e631db7e35a6b3cc4a29d71bcaaffcfa0) | 별도 답글 없음 — amend로 반영 |

### 충돌 해결

상세 과정은 [`docs/conflict-resolution.md`](docs/conflict-resolution.md)에
기록한다.

| 사례 | 난이도 | 해결 커밋 또는 PR |
| --- | --- | --- |
| 1 | 일반 | [`2fde409`](https://github.com/dlwognsdc610-maker/git-exercise/commit/2fde4091b1e12297a36acf60d7eb47fdaedb3b71) |
| 2 | 비자명 | [`b2e92f2`](https://github.com/dlwognsdc610-maker/git-exercise/commit/b2e92f29cf51553baa0aeb94bf8993d66cf711e2) |

### Git 트러블슈팅

상세 과정은
[`docs/troubleshooting-log.md`](docs/troubleshooting-log.md)에 기록한다.

| 실습 | 증빙 커밋 또는 로그 |
| --- | --- |
| `commit --amend` | [`a9cac7f` → `ec50144`](docs/troubleshooting-log.md#commit---amend) |
| `reset --soft` | [`73a1603` → `052bba8`](docs/troubleshooting-log.md#reset---soft) |
| `revert` | [`1dd9d95` → `a487aed`](docs/troubleshooting-log.md#revert) |
| `stash` | [`stash@{0}` 생성·목록 확인·복원 로그](docs/troubleshooting-log.md#stash) |
