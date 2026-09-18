---
name: newsletter-manuscript-writer
description: Writes and edits newsletter manuscript (.md) files in this project's custom email-newsletter format — plain markdown split into sections by "---", where each section opens with "## type: 키워드" (hero, body, info-box, cta, card-list, highlight, box, footer, table, timeline, notice) plus optional "- emoji:" / "- button:" fields. This manuscript is later converted to send-ready HTML, so getting the type/section structure exactly right matters. Use this skill whenever the user asks to draft, write, add to, or fix a newsletter manuscript / "뉴스레터 원고" .md file, wants to turn a notice, press release, program announcement, or promotion into this newsletter format, or asks to add/edit a specific section like "hero 섹션 추가해줘", "cta 버튼 문구 바꿔줘", "표에 병합된 셀 어떻게 써?". Trigger even without the word "스킬" or "마크다운" — requests like "이 공고문으로 뉴스레터 원고 하나 써줘" or "수출바우처 협약체결 안내 뉴스레터 만들어줘" qualify. Do not use this for converting the manuscript into final HTML — that is a separate step.
---

# Newsletter Manuscript Writer

뉴스레터 원고(.md)를 이 프로젝트 전용 포맷으로 작성하거나 수정하는 스킬입니다. 이 원고는 나중에 발송용 HTML로 변환되므로, 구조가 정확해야 변환기가 올바르게 읽습니다.

## 왜 이 포맷을 쓰는가

이메일 뉴스레터는 일반 웹페이지가 아니라 표(`<table>`) 기반의 제한된 레이아웃으로 변환됩니다. 자유 형식 마크다운 대신 "섹션 + type 태그" 구조를 쓰는 이유는, 변환기가 각 섹션을 어떤 컴포넌트(헤더, 버튼, 표 등)로 렌더링할지 기계적으로 판단해야 하기 때문입니다. 그래서 아래 두 가지 규칙만큼은 절대 어긋나면 안 됩니다.

1. **`---`로 섹션을 나눈다.** 뉴스레터 한 편은 여러 섹션(블록)의 연속이고, 섹션과 섹션 사이는 항상 `---` 한 줄로 구분합니다.
2. **각 섹션 맨 위에 `## type: 키워드`를 붙인다.** 이 섹션이 어떤 종류(헤더/본문/버튼 등)인지 알려주는 태그입니다. 키워드 철자가 틀리면 변환기가 그 섹션을 인식하지 못합니다.

기본 틀:
```
---

## type: body
여기에 본문 내용을 씁니다.

---
```

## type 키워드 (정확한 철자만 허용)

| type 키워드 | 용도 | 비고 |
|---|---|---|
| `hero` | 뉴스레터 맨 위, 가장 크게 보여줄 헤더 |  |
| `body` | 일반 본문 텍스트 | |
| `info-box` | 날짜·기한처럼 눈에 띄게 강조할 정보 박스 | |
| `cta` | 클릭을 유도하는 버튼 영역 (Call To Action) | `- button:` 필드와 거의 항상 같이 씀 |
| `card-list` | 아이콘 + 텍스트로 된 카드 목록 | `- 항목` 리스트, 인용구(`>`) 조합 가능 |
| `highlight` | 강조하고 싶은 한두 문장 | |
| `box` | 배경이 있는 카드 안에 내용을 담을 때 | 목록 + `- button:` 혼합 가능 |
| `footer` | 맨 하단 마무리 문구 | |
| `table` | 표 형태 데이터 | 아래 "표 작성 규칙" 참고 |
| `timeline` | 순서가 있는 절차/프로세스 | 번호 목록(`1. 2. 3.`) 사용 |
| `notice` | 유의사항, 경고, 규정 안내 | `#### 소제목`으로 하위 항목을 나눠도 됨 |

이 목록에 없는 키워드는 만들어내지 말고, 가장 가까운 기존 키워드로 매핑하세요. 애매하면 사용자에게 어떤 type이 맞을지 물어보는 것보다, 내용 성격상 가장 합리적인 type을 고르고 왜 그렇게 골랐는지 한 줄로 알려주세요.

## 보조 필드

섹션 본문 안에 다음 줄을 추가할 수 있습니다.

- `- emoji: 📢` — 그 섹션을 대표하는 이모지 지정 
- `- button: 02-6265-2100 (내선2번)` — 버튼처럼 보일 텍스트 지정 

이모지는 유니코드 이모지만 사용하세요. 아이콘 폰트나 이미지 태그는 이메일 클라이언트 다수에서 깨집니다.

## 표 작성 규칙

표준 마크다운 표 문법(`| 항목 | 내용 |` + `|---|---|` 구분선)을 그대로 쓰되, 이 프로젝트에서만 쓰는 두 가지 표기법이 있습니다.

**1. 세로 병합 셀 → `〃`**

원본 자료(엑셀, PPT 등)에 여러 행에 걸쳐 같은 값을 갖는 셀(세로 병합)이 있으면, 값이 처음 나오는 행에만 값을 쓰고 이어지는 행에는 `〃`(같은 값) 기호를 씁니다.

```
| 지원분야 | 내용 |
|---|---|
| 조사/일반컨설팅 | ... |
| 〃 | 디자인개발 |
| 〃 | 브랜드개발·관리 |
```

`〃`를 하나라도 쓴 표라면, 표 바로 아래에 각주를 반드시 한 줄 추가해서 의미를 밝혀주세요:
```
> ※ 〃 는 바로 위 행과 같은 값입니다.
```

**2. 행 전체 강조 → 셀 내용을 전부 `**굵게**`**

표 안 특정 행 전체를 강조하고 싶다면(예: 마감일처럼 놓치면 안 되는 정보), 그 행의 모든 셀 내용을 굵게 씁니다. 변환 시 그 행 전체에 옅은 음영이 들어갑니다.

```
| 항목 | 내용 |
|---|---|
| 공고명 | 수출지원기반활용사업 참여기업 모집 |
| **마감일** | **2026년 9월 17일까지** |
```

## 작성 절차

1. 사용자가 준 원본 자료(공고문, 안내문, 이전 뉴스레터 등)에서 핵심 메시지를 뽑아낸다.
2. 메시지를 성격별로 나눠 어떤 type 섹션들로 구성할지 정한다. 보통 `hero`(제목) → `info-box` 또는 `body`(핵심 정보/설명) → `table`/`timeline`(구조화된 데이터/절차) → `notice`(유의사항, 있다면) → `cta`(문의/신청) → `footer`(맺음말) 순서가 자연스럽지만, 내용에 안 맞는 섹션을 억지로 넣지 않는다.
3. 각 섹션을 `---` 로 감싸고 `## type: 키워드`를 맨 위에 붙인다.
4. 표가 있다면 위 표 작성 규칙(병합 `〃`, 강조 행)을 적용한다.
5. 완성된 파일을 `.md` 확장자로 저장한다. 기존 파일을 수정하는 요청이면 기존 구조와 톤을 최대한 유지하면서 필요한 섹션만 바꾼다.

## 흔한 실수 체크리스트 (제출 전 스스로 확인)

- [ ] 섹션 사이마다 `---`가 빠짐없이 있는가?
- [ ] `## type: 키워드` 철자가 위 표의 11개 키워드 중 하나와 정확히 일치하는가?
- [ ] 표를 썼다면 `|---|---|` 구분선이 있는가?
- [ ] `〃`를 썼다면 바로 아래 각주(`> ※ 〃 는 바로 위 행과 같은 값입니다.`)를 추가했는가?
- [ ] `- button:`, `- emoji:` 앞에 `-`와 띄어쓰기가 정확한가?
- [ ] 파일 확장자가 `.md`인가?

## 예시: 미니 뉴스레터

```
---

## type: hero
### 가을맞이 신제품 안내
지금 바로 확인해보세요!
- emoji: 🍂

---

## type: body
안녕하세요, 고객님.
이번 가을 새롭게 출시된 제품을 소개해 드립니다.

---

## type: cta
### 📞 자세히 문의하기
- button: 02-1234-5678

---
```

더 긴 예시(표, 타임라인, notice 포함)가 필요하면 `assets/template.md`를 참고하세요 — 모든 type 키워드를 한 번씩 보여주는 전체 템플릿입니다.
