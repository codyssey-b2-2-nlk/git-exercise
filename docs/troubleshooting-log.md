# Git 트러블슈팅 기록

각 실습은 실제 작업 중 생긴 상황, 실행한 명령, 전후 상태와 결과를
기록한다. 공유 브랜치의 history는 다시 쓰지 않는다.

## `commit --amend`

- 일시와 작업자: 2026-09-19, JaeHoon Lee
- 상황: 최초 컨벤션 커밋의 메시지에 trailer를 추가했다.
- 실행 전 커밋: `a9cac7ff0449d35376a03a08a00e1bd726aa9cee`
- 실행한 명령: `git commit --amend`
- 실행 후 커밋: `ec50144e631db7e35a6b3cc4a29d71bcaaffcfa0`
- 확인 결과: reflog에서 amend와 전후 커밋을 확인했고, 작업 브랜치와
  원격 브랜치가 새 커밋을 가리킨다.
- 후속 확인: 이 커밋의 `Reviewed-by` 이메일에서 닫는 `>`가 빠졌지만
  PR #1로 `main`에 이미 병합됐다. 공유 이력을 다시 쓰지 않고 이후
  커밋과 `CONTRIBUTING.md` 예시에 올바른 trailer를 기록했다.

## `reset --soft`

- 일시와 작업자: 2026-09-19, JaeHoon Lee
- 상황: 팀 기여 기록 안내를 커밋한 뒤 제목의 `contribtuion` 오타를
  발견했다. 원격에 올리기 전이라 변경 내용은 유지하고 커밋만 다시
  작성했다.
- 실행 전 커밋: `73a1603be92b3e629d92740a0596ad1e1f4a847f`
- 실행한 명령: `git reset --soft HEAD^`
- index와 working tree 상태: `team/README.md`의 4줄 변경이 index에
  staged 상태로 남았고 unstaged 변경은 없었다.
- 다시 작성한 커밋: `052bba8a08640d3b57ea0e1f37e638b80bd4a858`
  (`docs/team: describe contribution records`)
- 확인 결과: 전후 커밋의 tree 내용은 같고 커밋 제목의 오타만 바로잡힌
  것을 `git diff 73a1603 052bba8`과 `git log -2 --oneline`으로 확인했다.

## `revert`

- 일시와 작업자: 2026-09-19, JaeHoon Lee
- 되돌릴 커밋과 이유: `1dd9d95579c71ba5a9b3134bcddfbc67b8009e9f`가
  루트 `README.md`에 실수로 `wiort`를 추가했기 때문에 공유 이력을
  지우지 않고 역변경을 남겼다.
- 실행한 명령:
  `git revert -s --no-edit 1dd9d95579c71ba5a9b3134bcddfbc67b8009e9f`
- 생성된 revert 커밋:
  `a487aedada62ac19bb7cb7faa1b85c58324e706b`
- 확인 결과: `git show --stat a487aed`에서 `README.md`의 2줄 삭제를
  확인했고, 원래 커밋과 revert 커밋이 모두 이력에 남아 있다.

## `stash`

- 일시와 작업자: 2026-09-19, JaeHoon Lee
- 보관해야 했던 변경: `team/README.md`에 팀 결과물과 구성원별 기여를
  정리할 위치라는 설명을 추가하던 중, stash 실습을 위해 미완성 변경을
  작업 트리에서 잠시 치웠다.
- 실행한 명령:

  ```console
  $ git stash push -m "wip: document team workspace"
  Saved working directory and index state On ljh: wip: document team workspace
  $ git stash list
  stash@{0}: On ljh: wip: document team workspace
  ```

- `stash list` 증빙: `stash@{0}`의 객체 ID는
  `4eac5632d085796f6d25716b7a21ed340f159606`이었다.
- 복원 명령과 결과: `git stash pop`으로 변경을 복원했다. Git은
  `team/README.md`를 수정 상태로 되돌린 뒤 위 stash를 drop했다.
- 확인 결과: stash 직후 `git status --short` 출력은 비어 있었고,
  복원 후에는 ` M team/README.md`가 표시됐다. `git diff`로 추가한 설명이
  그대로 복원된 것을 확인했으며, 마지막 `git stash list`는 비어 있었다.
