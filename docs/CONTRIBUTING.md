# Commit Rules:
Convention:

Example:

```
docs/CONTRIBUTE.md: commit example

initial commit for example, write file
name and message.

#add Trailer:
Signed-off-by: JaeHoon Lee <dlwognsdc610@gmail.com>
reviewed-by: Reviewer <email>

```

# Contributing Guide

## 브랜치 전략 (GitHub Flow)

- `main`: 항상 정상적으로 동작하는 상태를 유지합니다.
- `feature/*`: 기능 추가, 문서 작성 등 작업 단위별로 생성합니다.
- 모든 작업은 `feature/*` 브랜치에서 진행하고 PR을 통해 `main`에 병합합니다.

우리 팀은 작업 내용을 분리하고 서로의 변경 사항을 안전하게 확인하기 위해 GitHub Flow를 사용합니다.  
PR을 통해 코드 리뷰와 변경 이력을 남길 수 있습니다.  
또한 구조가 단순하여 소규모 팀 협업에 적합합니다.

## 브랜치 네이밍 규칙

아래 형식을 사용합니다.

```text
feature/<name>-<topic>
```

예시:

```text
feature/kim-math-utils
feature/lee-readme
feature/park-string-utils
```

## Commit Rules

### Convention

커밋 메시지는 아래 형식을 사용합니다.

```text
type: 작업 내용
```

주요 type:

```text
feat: 기능 추가
fix: 오류 수정
docs: 문서 수정
refactor: 코드 정리
```

예시:

```text
docs: CONTRIBUTING.md에 커밋 규칙 추가

feat: 문자열 변환 함수 추가

fix: 빈 문자열 처리 오류 수정
```

다음과 같이 변경 내용을 알기 어려운 메시지는 사용하지 않습니다.

```text
update
fix
wip
temp
final
```

### Commit Example

커밋 메시지에는 어떤 파일 또는 기능을 수정했는지 알 수 있도록 작성합니다.

예시:

```text
docs: CONTRIBUTING.md에 커밋 예시 추가
```

필요한 경우 본문에 변경 내용을 추가합니다.

```text
docs: CONTRIBUTING.md에 커밋 예시 추가

커밋 메시지 작성 방법과 Trailer 사용 방법을 추가한다.
```

### Trailer

커밋 하단에는 작성자와 리뷰어 정보를 Trailer 형식으로 추가할 수 있습니다.

예시:

```text
docs: CONTRIBUTING.md에 커밋 예시 추가

커밋 메시지 작성 방법과 Trailer 사용 방법을 추가한다.

Signed-off-by: JaeHoon Lee <dlwognsdc610@gmail.com>
Reviewed-by: Reviewer <email>
```

`Signed-off-by`는 해당 커밋 작성자를 나타내고, `Reviewed-by`는 해당 변경 내용을 검토한 리뷰어를 나타냅니다.

`Signed-off-by`는 아래 명령으로 자동 추가할 수 있습니다.

```bash
git commit -s -m "docs: CONTRIBUTING.md에 커밋 예시 추가"
```

## PR 규칙

PR 본문에는 아래 내용을 작성합니다.

```text
What: 무엇을 변경했는지
Why: 왜 변경했는지
How: 어떻게 확인했는지
Closes #이슈번호
```

예시:

```text
What:
- 문자열 변환 함수를 추가했습니다.

Why:
- 문자열 관련 유틸 기능이 필요하여 추가했습니다.

How:
- 로컬에서 함수를 실행하여 결과를 확인했습니다.

Closes #3
```

PR은 최소 1명의 리뷰와 승인을 받은 후 `main`에 병합합니다.

## 코드 리뷰 규칙

`LGTM`, `좋습니다`, `확인했습니다`와 같은 단순한 의견만 작성하지 않습니다.

코드 또는 문서의 구체적인 부분을 확인하고 의견을 작성합니다.

예시:

```text
이 함수는 빈 문자열이 들어오는 경우도 처리하면 좋을 것 같습니다.
```

```text
변수 이름을 조금 더 명확하게 변경하면 코드 이해가 쉬울 것 같습니다.
```

PR 작성자는 리뷰 의견을 확인하고 수정하거나 답글을 남깁니다.

## 충돌 대응 흐름

충돌이 발생하면 아래 순서로 처리합니다.

```text
충돌 발생
→ 관련 팀원에게 공유
→ 충돌 내용 확인
→ 해결 방법 결정
→ 충돌 해결
→ 정상 동작 확인
→ commit 및 push
→ conflict-resolution.md에 기록
```

충돌 해결 과정은 아래 문서에 기록합니다.

```text
docs/conflict-resolution.md
```