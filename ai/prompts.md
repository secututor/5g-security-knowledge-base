# 프롬프트 템플릿 (Prompt Templates)

5G Security Knowledge Base 문서를 생성/확장할 때 AI 에이전트에게 줄 수 있는 재사용 프롬프트 모음입니다.
모든 프롬프트는 `.kiro/steering/`의 `rules-authoring.md`, `rules-diagrams.md` 규칙 준수를 전제로 합니다.
(이 규칙 파일들은 기본 에이전트 세션에 자동 로드되므로 별도로 읽지 않아도 적용됩니다.)

> 사용 팁: 규칙은 자동 로드되지만, 참조 코드의 출처인 마스터 데이터
> `subject/subject-list.md`(및 `subject/5G_Security.md`)는 프롬프트 실행 전 읽도록 지시하세요.

## 콘텐츠 타입과 위치 (rules-authoring.md §1)

| 타입 | 성격 | 위치 | 템플릿 |
|------|------|------|--------|
| `issue` | 5G 위협/취약점/리스크 | `5g-security/security-risks/NN-*/` | §3.1 10항목 |
| `concept` | 5G 보안 개념/원리 | `5g-security/fundamentals/` | §3.2 개념 |
| `general` | 5G 무관 일반 보안 지식 | `security-fundamentals/` | §3.2 개념 |
| `reference` | 표준/기관/논문 정의 | `5g-security/references/*/` | §3.3 참조 |

> 경로 규칙: 위협 카테고리는 `5g-security/security-risks/NN-{name}/` (NN=01~10).
> references 하위는 번호 없이 `3gpp-standards / enisa-framework / nist-series / research-papers`.

---

## 프롬프트 1 — 이슈 문서 1건 생성 (`issue`)

```
(문서 작성 규칙은 .kiro/steering/에서 자동 로드된다. 준수 전제.)
subject/subject-list.md 에서 이슈 "{NN-MM}"({Issue Name}) 행을 찾아라.

5g-security/security-risks/{NN-folder}/{NN-MM}-{Issue Name}.md 파일을
rules-authoring.md §3.1의 10항목 풀 템플릿으로 작성하라.

- 제목: # {NN-MM}. {Issue Name}
- ## 1. 개요: subject-list.md 한국어 설명 기반, 배경까지 2~3문단
- ## 2. 공격 대상: 관련 NF/인터페이스/프로토콜/계층 명시
- ## 3. 취약점: 공격이 가능한 근본 원인 (표준/구현/설정, 4G 대비 차이)
- ## 4. 공격 시나리오: mermaid sequenceDiagram + 단계별 설명 (직접 작성)
- ## 5. 영향: C-I-A + 프라이버시 관점 표
- ## 6. 대응 방안: 예방/탐지/완화 (표준 보안기능 + 운영 관점 구분)
- ## 7. 3GPP / O-RAN 표준, ## 8. 관련 US 가이드라인, ## 9. 관련 EU 가이드라인, ## 10. 참조 논문:
  subject-list.md 값을 그대로 기입 (지어내지 말 것)

references 링크 상대경로: ../../references/{폴더}/README.md
핵심 콘텐츠(2~6)는 참조 나열이 아니라 실제 해설로 채운다.
외부 원문은 복사하지 말고 재구성하며, 옮긴 내용은 출처를 명시한다 (§6).
작성 후 SUMMARY.md 항목 존재/정확성과 링크 경로가 실제 파일 경로(언더스코어)와 일치하는지 점검하라.
```

---

## 프롬프트 2 — 기존 스켈레톤 이슈 문서를 풀 템플릿으로 업그레이드 (`issue`)

```
(문서 작성 규칙은 .kiro/steering/에서 자동 로드된다. 준수 전제.)

5g-security/security-risks/{NN-folder}/{NN-MM}-{Issue Name}.md 는 현재 참조 코드만 있는 스켈레톤이다.
이를 rules-authoring.md §3.1의 10항목 풀 템플릿으로 업그레이드하라.

- 기존 참조 값(US/EU/3GPP·O-RAN/논문)은 각각 7~10번 섹션으로 보존/이동
- 누락된 핵심 콘텐츠 섹션을 채운다:
  ## 2. 공격 대상, ## 3. 취약점, ## 4. 공격 시나리오(mermaid), ## 5. 영향(C-I-A), ## 6. 대응 방안
- 필요 시 ## 관련 이슈 / ## 출처 선택 섹션 추가

주의:
- 참조 코드는 subject-list.md 정의만 사용 (환각 금지)
- references 링크 상대경로: ../../references/{폴더}/README.md
- Mermaid는 권장 타입(sequenceDiagram/flowchart/stateDiagram-v2)만, 직접 작성
- 다이어그램에는 본문 텍스트 설명 병기
- 외부 원문 복사 금지(재구성), 옮긴 내용은 출처 명시 (§6)
```

---

## 프롬프트 3 — 카테고리 전체 일괄 생성 (`issue`)

```
(문서 작성 규칙은 .kiro/steering/에서 자동 로드된다. 준수 전제.)
subject/subject-list.md 의 카테고리 "{섹션 문자 A~J}" (폴더 5g-security/security-risks/{NN-folder})
테이블에 있는 모든 이슈에 대해, 각각 {NN-MM}-{Issue Name}.md 파일을
rules-authoring.md §3.1의 10항목 풀 템플릿으로 생성하라.

규칙:
- 파일명 규칙 적용: 공백→`_`, 특수문자 정규화 (EAP-AKA_prime, IMSI-SUPI, HTTP2, AI-ML 등)
- 각 행의 참조 값을 정확히 매핑
- references 링크 상대경로: ../../references/{폴더}/README.md
- 모든 파일 생성 후 SUMMARY.md 해당 섹션을 번호 오름차순으로 갱신
  (링크는 루트 기준 전체 경로 5g-security/security-risks/... , 공백/`%20` 없음)

생성한 파일 목록과 SUMMARY.md 변경 사항을 요약해서 보고하라.
```

---

## 프롬프트 4 — 카테고리/영역 개요(README) 작성

```
(문서 작성 규칙은 .kiro/steering/에서 자동 로드된다. 준수 전제.)
5g-security/security-risks/{NN-folder}/README.md 를 작성하라. 이 카테고리({Category Title})의 개요 페이지다.

포함할 내용:
- # {NN}. {Category Title}
- 이 카테고리가 다루는 보안 영역에 대한 한국어 개요 (1~2문단)
- 포함된 이슈 목록 (subject-list.md 기준, 각 이슈 문서로의 상대경로 링크; 라벨 번호도 새 NN에 맞춤)
- 필요하면 이 영역의 5G 아키텍처상 위치를 mermaid flowchart로 표현 (rules-diagrams.md 준수)

SUMMARY.md 에서 이 카테고리 부모 항목(README 링크)과 하위 이슈 들여쓰기 계층이 올바른지 확인하라.
```

---

## 프롬프트 5 — 5G 개념 문서 생성 (`concept`)

```
(문서 작성 규칙은 .kiro/steering/에서 자동 로드된다. 준수 전제.)
5g-security/fundamentals/{NN-MM}-{Concept_Name}.md 파일을
rules-authoring.md §3.2 개념 템플릿으로 작성하라. (NN-MM은 fundamentals 내부 자체 순번)

- 제목: # {Concept Name} (개념명, 영문 유지 가능)
- ## 1. 개요 (What): 개념의 한국어 정의
- ## 2. 배경 / 원리 (Why & How): 필요성과 동작 원리 (필요 시 mermaid, 직접 작성)
- ## 3. 상세 (Details): 구성요소·절차·수식·용어 (소제목 자유)
- ## 4. 보안 관점 (Security Relevance): 보안 중요성 + 관련 5G 이슈로 링크
- (선택) ## 관련 문서 / ## 출처

주의:
- references 링크 상대경로: ../references/{폴더}/README.md
- 관련 이슈 링크 상대경로: ../security-risks/{NN-folder}/{NN-MM}-....md
- asset(SVG) 링크: ../../.gitbook/assets/{파일명}.svg
- 환각 금지, 외부 원문 복사 금지(재구성), 옮긴 내용은 출처 명시 (§6)
작성 후 SUMMARY.md "5G Fundamentals" 묶음에 항목을 추가/갱신하라.
```

---

## 프롬프트 6 — 일반 보안 지식 문서 생성 (`general`)

```
(문서 작성 규칙은 .kiro/steering/에서 자동 로드된다. 준수 전제.)
security-fundamentals/{concept-name}.md 파일을
rules-authoring.md §3.2 개념 템플릿으로 작성하라. (5G에 국한되지 않는 일반 보안 지식)

- 파일명: 의미 이름(kebab/underscore), 공백 금지. 예: pki-basics.md, zero-trust.md
- 제목: # {Concept Name}
- ## 1. 개요 → ## 2. 배경/원리 → ## 3. 상세 → ## 4. 보안 관점
- 5G와 연결되는 지점이 있으면 ## 4에서 5g-security 문서로 링크
  (상대경로 예: ../5g-security/security-risks/{NN-folder}/{NN-MM}-....md)

주의:
- 특정 벤더/제품에 치우치지 말고 원리 중심으로 서술
- 외부 원문 복사 금지(재구성), 옮긴 내용은 출처 명시 (§6)
작성 후 SUMMARY.md "Security Fundamentals" 묶음에 항목을 추가/갱신하라.
```

---

## 프롬프트 7 — 일관성 검수 (감사)

```
.kiro/steering/rules-authoring.md, .kiro/steering/rules-diagrams.md 를 기준으로 리포지토리 전체를 검수하라.
아래 항목을 점검하고 위반 사항을 파일별로 리포트하라 (수정은 하지 말고 보고만):

1. 문서가 올바른 영역/타입 위치에 있는가
   (issue→5g-security/security-risks, concept→5g-security/fundamentals,
    general→security-fundamentals, reference→5g-security/references)
2. 이슈 파일명이 NN-MM-{Issue_Name}.md 패턴과 일치하는가 (공백 없이 `_`, 특수문자 정규화 포함)
3. 이슈 문서 제목이 # NN-MM. {Issue Name} 형식이고, 카테고리 번호(NN)가 폴더와 일치하는가
4. 이슈 문서에 10항목 섹션이 순서대로 존재하는가 / 개념 문서가 §3.2 템플릿을 따르는가
5. 참조 코드(US/EU/P/TS·TR)가 subject-list.md 정의와 일치하는가
6. SUMMARY.md의 모든 링크가 실제 파일을 가리키는가 (깨진 링크/누락)
7. SUMMARY.md가 4개 최상위 묶음(Security Fundamentals / 5G Fundamentals / 5G Security Risks / References)과
   올바른 들여쓰기 계층을 따르는가, 링크 경로가 실제 파일 경로(언더스코어)와 일치하는가
8. 상대경로(references/asset/교차링크)의 depth가 문서 위치에 맞는가
9. Mermaid 코드 블록이 권장 타입/문법을 따르는가

리포트는 위반 심각도(높음/중간/낮음)로 분류하라.
```

> 참고: 규칙 기반 문서 리뷰는 `.kiro/skills/doc-review/` 스킬로도 수행할 수 있다.

---

## 작성 시 공통 주의사항 (모든 프롬프트 적용)

- **환각 금지**: 표준 번호, 논문 번호, 가이드라인 코드는 마스터 데이터에 있는 것만 사용. 불확실하면 비워두고 표시.
- **출처·저작권 준수 (rules-authoring.md §6)**: 외부 원문을 그대로 복사·번역하지 말고 재구성한다. 원문 내용을 옮기면 출처를 명시하고, 원문 요약과 작성자 해설을 구분한다. 기관 로고·제3자 그림을 무단 사용하지 않고 다이어그램은 직접 그린다.
- **한국어 본문 / 영문 용어·제목** 원칙 유지.
- 문서를 새로 만들거나 옮기면 **SUMMARY.md 갱신은 필수**.
- 다이어그램은 보조 수단. 본문 텍스트 설명을 대체하지 않는다.
- GitHub/GitBook 양쪽 렌더링 호환 문법만 사용.
