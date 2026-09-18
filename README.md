# newsletter-manuscript-writer 스킬

이 폴더는 뉴스레터 원고(.md)를 이 프로젝트 전용 포맷으로 작성해주는 Claude Code 스킬 `newsletter-manuscript-writer`가 설치되어 있습니다.

- 스킬 위치: `.claude/skills/newsletter-manuscript-writer/`
- 적용 범위: 이 폴더 안에서 작업할 때만 자동으로 로드됩니다.

## 이 스킬이 하는 일

공고문, 안내문, 프로모션 내용 등을 주면 아래 규칙을 지켜 뉴스레터 원고 `.md` 파일을 작성하거나 기존 원고를 수정합니다.

- `---`로 섹션을 구분
- 각 섹션 맨 위에 `## type: 키워드` 지정 (`hero`, `body`, `info-box`, `cta`, `card-list`, `highlight`, `box`, `footer`, `table`, `timeline`, `notice`)
- `- emoji:`, `- button:` 같은 보조 필드
- 표의 세로 병합 셀(`〃`) 표기, 강조 행(`**굵게**`) 표기

이렇게 작성된 원고는 이후 별도 단계에서 발송용 HTML로 변환됩니다. 이 스킬은 원고(.md) 작성까지만 담당하며, HTML 변환은 다루지 않습니다.

## 사용 방법

이 폴더에서 Claude Code에게 "OO 안내 뉴스레터 원고 써줘", "hero 섹션 추가해줘"처럼 자연어로 요청하면 스킬이 자동으로 트리거됩니다. 스킬 이름이나 "마크다운"이라는 단어를 언급할 필요는 없습니다.

## 원고 작성 문법 자체가 궁금하다면

마크다운 기본 문법과 이 프로젝트 규칙을 처음부터 차근차근 설명하는 가이드는 **`guide.html`**을 참고하세요. 브라우저로 열어 보면 됩니다.

관련 문서:
- `guide.html` — 마크다운 첫걸음 (기본 문법 + 프로젝트 규칙 정리본)
- `newsletter-manuscript-guide.md` — 위 가이드의 원본 마크다운
- `newsletter-figma-guide.md` — 원고 md에서 피그마에서 시안 만드는 스킬
- `.claude/skills/newsletter-manuscript-writer/assets/template.md` — 빈 템플릿

## 마크다운 첫걸음 (기본 문법 + 프로젝트 규칙 정리본)
[https://yujiseon.github.io/newsletter/guide.html] 에서 확인 가능합니다.
