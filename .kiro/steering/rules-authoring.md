---
inclusion: always
---
# 문서 작성 규칙 (Authoring Rules)

이 문서는 **5G Security Knowledge Base** GitBook 문서를 작성/확장할 때 반드시 지켜야 하는 규칙을 정의합니다.
AI 에이전트와 사람 기여자 모두 이 규칙을 기준으로 작업합니다.

> 이 리포지토리는 GitHub ↔ GitBook 동기화로 운영됩니다. 모든 문서는 GitHub과 GitBook 양쪽에서 올바르게 렌더링되어야 합니다.
> 이 규칙 파일은 `.kiro/steering/`에 있어 기본 에이전트 세션에 자동 로드됩니다.

---

## 1. 디렉토리 구조

이 리포지토리는 **지식의 성격(영역, domain)** 을 최상위로 두고, 그 아래에 하위 영역과
번호가 붙은 카테고리를 배치한다. 최상위는 "번호"가 아니라 "영역"이다.

```
5g-security-knowledge-base/
├── SUMMARY.md                      # GitBook 목차 (필수, 신규 문서 추가 시 반드시 갱신)
├── README.md                       # 사이트 소개 페이지
├── gitbook-docs.yaml               # GitBook 사이트 설정 (수정 지양)
├── security-fundamentals/          # [영역] 일반 보안 기초 (5G 무관: 암호, PKI, Zero Trust, 위협모델링 등)
│   └── README.md
├── 5g-security/                    # [영역] 5G 보안
│   ├── README.md
│   ├── fundamentals/               #   [하위영역] 5G 보안 개념/원리 (키 계층, SUCI, NAS/RRC 등)
│   │   └── 01-01-....md
│   ├── security-risks/             #   [하위영역] 위협/취약점 카탈로그 (100선)
│   │   ├── README.md
│   │   ├── 01-ue-privacy/          #     UE & Privacy Security
│   │   ├── 02-auth-nas/            #     Authentication & NAS Security
│   │   ├── 03-ran-security/        #     RAN Security
│   │   ├── 04-gnb-interfaces/      #     gNB Interfaces & Protocols
│   │   ├── 05-core-security/       #     Core Network Security
│   │   ├── 06-sba-security/        #     SBA & Service Security
│   │   ├── 07-network-slicing/     #     Network Slicing Security
│   │   ├── 08-nfv-cloud/           #     NFV & Cloud Native Security
│   │   ├── 09-oran-security/       #     O-RAN Security
│   │   └── 10-v2x-supply-chain/    #     V2X & Supply Chain Security
│   └── references/                 #   [하위영역] 표준·가이드라인·논문 정의
│       ├── README.md
│       ├── 3gpp-standards/         #     3GPP / O-RAN 표준 (TS/TR)
│       ├── enisa-framework/        #     EU ENISA 프레임워크 (EU-N)
│       ├── nist-series/            #     US NIST & CISA 가이드라인 (US-N)
│       └── research-papers/        #     참조 논문 (P-N)
├── subject/                        # 원본 마스터 데이터 (편집용, 사이트 목차엔 미포함)
├── ai/                             # 사람용 안내/프롬프트 (사이트 목차엔 미포함)
├── .gitbook/assets/                # 이미지/SVG (GitBook 표준 경로, 사이트 목차엔 미포함)
└── .kiro/steering/                 # AI 자동 로드 규칙 (rules-authoring.md, rules-diagrams.md)
```

### 콘텐츠 타입 (중요)
문서는 "타입"에 따라 배치 위치와 템플릿(§3)이 다르다.

| 타입 | 성격 | 위치 | 템플릿 |
|------|------|------|--------|
| `issue` | 5G 위협/취약점/리스크 | `5g-security/security-risks/NN-*/` | §3.1 10항목 풀 템플릿 |
| `concept` | 5G 보안 개념/원리 해설 | `5g-security/fundamentals/` | §3.2 개념 템플릿 |
| `general` | 5G 무관 일반 보안 지식 | `security-fundamentals/` | §3.2 개념 템플릿 |
| `reference` | 표준/기관/논문 정의 | `5g-security/references/*/` | §3.3 참조 템플릿 |

### 규칙
- **최상위는 영역**(`security-fundamentals/`, `5g-security/`)이다. 최상위에 번호 폴더를 두지 않는다.
- **번호는 `security-risks/` 하위 카테고리에서만** `NN-{kebab-case-name}/` 형식으로 쓴다. `NN`은 2자리 0-padding.
- `security-risks` 카테고리 번호는 `subject/subject-list.md`의 섹션(A~J) 분류 체계와 순서를 맞춘다.
  (subject-list의 A=UE/Privacy → `01-ue-privacy`, B=Auth/NAS → `02-auth-nas` … 순으로 대응)
- **각 `security-risks` 카테고리 폴더와 하위영역(`fundamentals`, `security-risks`, `references`)에는 `README.md`(개요 + 목록)를 둔다.** 이 README가 SUMMARY 계층의 부모 항목이 된다 (§4).
- `references/` 하위 폴더는 번호 없이 의미 이름(`3gpp-standards` 등)을 쓴다.
- `subject/`, `ai/`, `.kiro/`, `.gitbook/`은 **작업/설정용**이며 `SUMMARY.md` 목차에는 넣지 않는다.
- 새 영역이 필요하면(예: `cloud-security/`) 최상위 형제로 추가하고 §4의 SUMMARY 묶음(`##`)도 함께 추가한다.

---

## 2. 파일명 규칙

이슈 문서 파일명은 다음 패턴을 **정확히** 따른다.

```
NN-MM-{Issue_Name}.md
```

- `NN`: 카테고리 번호 (2자리, 폴더 번호와 동일). 예: `02`
- `MM`: 카테고리 내 이슈 순번 (2자리). 예: `01`
- `{Issue_Name}`: 영문 이슈명. **공백은 언더스코어(`_`)로 치환**한다.

> **파일명 공백 금지**: 이 리포지토리의 모든 파일명(문서·이미지·SVG 등)은 공백을 쓰지 않고
> 언더스코어(`_`)로 대체한다. URL 인코딩(`%20`)이 불필요해지고 링크가 안전해진다.

### 예시 (실제 파일)
```
5g-security/security-risks/01-ue-privacy/01-01-SUPI_Exposure.md
5g-security/security-risks/02-auth-nas/02-01-5G-AKA_Attack_Surface.md
5g-security/security-risks/06-sba-security/06-06-OAuth_Token_Abuse.md
```

### 규칙
- 이슈명은 `subject/subject-list.md` 테이블의 **Security Issue** 컬럼을 기준으로 하되,
  **공백은 `_`로 바꾸고**, 파일 시스템에서 문제가 되는 문자(`/`, `'`)는 아래처럼 정규화한다.
  - 공백 → `_` (예: `SUPI Exposure` → `SUPI_Exposure`)
  - `EAP-AKA'` → `EAP-AKA_prime` (예: `02-02-EAP-AKA_prime_Attack.md`)
  - `IMSI/SUPI` → `IMSI-SUPI` (예: `01-02-IMSI-SUPI_Catching.md`)
  - `HTTP/2` → `HTTP2` (예: `06-07-HTTP2_DoS.md`)
  - `AI/ML` → `AI-ML` (예: `09-05-AI-ML_Model_Poisoning.md`)
  - `Hardware/Platform` → `Hardware-Platform`
- 하이픈(`-`)은 구분자(`NN-MM-`) 및 기존 정규화(`IMSI-SUPI` 등)에만 쓰고, 단어 사이 공백 대체는 `_`로 한다.
- 개요/랜딩 페이지는 카테고리 폴더에 `README.md`로 둔다 (신규 카테고리는 `README.md`로 통일).

---

## 3. 문서 섹션 구조

문서는 **콘텐츠 타입**(§1)에 따라 다른 템플릿을 쓴다.
- `issue` → §3.1 10항목 풀 템플릿
- `concept` / `general` → §3.2 개념 템플릿
- `reference` → §3.3 참조 템플릿

### 3.1 이슈 문서 (`issue`) — 10항목 풀 템플릿

모든 이슈 문서(`5g-security/security-risks/`)는 `subject/5G_Security.md`가 제안한 **10항목 풀 템플릿**을 따른다.
아래 섹션을 **이 순서대로** 포함한다.

원문 제안 흐름: **Threat → Target → Vulnerability → Attack Scenario → Impact → 3GPP → ENISA(EU) → NIST/CISA·NSA(US) → Paper → Korean Explanation**

```markdown
# NN-MM. {Issue Name}

## 1. 개요 (What)
{이슈가 무엇인지 한국어 정의. subject-list.md의 "한국어 설명"을 기반으로 배경까지 2~3문단으로 서술.}

## 2. 공격 대상 (Target)
{공격이 노리는 대상. 관련 NF / 인터페이스 / 프로토콜 / 계층을 명시.
 예: UE → RAN(초기 접속) / gNB / RRC·NAS 등. 필요 시 표로 정리.}

## 3. 취약점 (Why possible)
{왜 이 공격이 가능한지. 표준/구현/설정상의 근본 원인. 4G 대비 차이가 있으면 함께 설명.}

## 4. 공격 시나리오 (Attack Scenario)
{공격 진행 단계. Mermaid sequenceDiagram 권장 + 단계별 텍스트 설명 병기.
 (rules-diagrams.md 준수, 다이어그램은 직접 작성)}

## 5. 영향 (Impact)
{C-I-A + 프라이버시 관점으로 영향 정리. 표 권장:
 기밀성 / 무결성 / 가용성 / 프라이버시 중 해당 항목과 구체적 피해.}

## 6. 대응 방안 (Countermeasure)
{예방 / 탐지 / 완화 통제. 표준이 정의한 보안기능과 운영 관점 대응을 구분해 서술.}

## 7. 3GPP / O-RAN 표준
{TS/TR 번호. 여러 개면 쉼표로. 예: TS 33.501, TR 33.809. → references/3gpp-standards 참조}

## 8. 관련 US 가이드라인
{US-N 형식. 예: US-2 또는 US-4,5. → references/nist-series 참조. 관점: NIST=구현/검증, CISA·NSA=위협/안보}

## 9. 관련 EU 가이드라인
{EU-N 형식. 예: EU-1. → references/enisa-framework 참조. 관점: ENISA=위협 지형}

## 10. 참조 논문
{P번호. 예: P1, P2. → references/research-papers 참조}
```

#### 규칙
- **10개 섹션 모두 포함**한다. 다만 근거가 부족한 섹션(예: 특정 이슈에 대한 논문 없음)은
  억지로 채우지 말고 "해당 없음" 또는 비워두고 사유를 남긴다 (환각 금지).
- 섹션 7~10의 **참조 코드(US-N, EU-N, P-N, TS/TR)**는 임의로 만들지 말고
  `subject/subject-list.md` 및 `subject/5G_Security.md`의 정의를 그대로 사용한다.
- references 링크 상대경로: security-risks 문서 → `../../references/{폴더}/README.md`.
- 섹션 2~6(공격 대상/취약점/시나리오/영향/대응)은 이 지식베이스의 **핵심 콘텐츠**다.
  단순 참조 나열에 그치지 말고 4대 출처(3GPP/ENISA/NIST/CISA·NSA)와 논문을 **연결·해설**한다.
- 관점 교차: 같은 이슈라도 ENISA(위협 지형) / NIST(구현·검증) / CISA·NSA(위협·안보) / 3GPP(표준)의
  서로 다른 시각을 본문에 녹인다.

#### 선택 섹션 (필요 시 추가)
```markdown
## 관련 이슈            # 다른 NN-MM 문서로의 상호 참조 링크
## 출처                 # 원문을 상당 부분 참고한 경우 (§6.5 참조)
```

### 3.2 개념 문서 (`concept` / `general`) — 개념 템플릿

5G 보안 개념(`5g-security/fundamentals/`)과 일반 보안 지식(`security-fundamentals/`)은
10항목 강제 없이 아래 자유형 템플릿을 기준으로 한다. 제목은 개념명(영문 유지 가능).

```markdown
# {Concept Name}

## 1. 개요 (What)
{개념이 무엇인지 한국어 정의.}

## 2. 배경 / 원리 (Why & How)
{왜 필요한가, 어떻게 동작하는가. 필요 시 다이어그램(rules-diagrams.md).}

## 3. 상세 (Details)
{구성요소·절차·수식·용어 등 핵심 내용. 소제목 자유 구성.}

## 4. 보안 관점 (Security Relevance)
{이 개념이 보안에 왜 중요한가. concept라면 관련 5G 이슈로 링크.}

## 관련 문서            # (선택) 관련 이슈/개념/참조 링크
## 출처                 # (선택) 외부 자료를 참고한 경우 (§6)
```

- `concept` 파일명은 이슈처럼 카테고리 순번을 쓸 수 있다(예: `01-01-5G_Key_Hierarchy.md`).
  단, 여기서 `NN`은 fundamentals 내부의 자체 순번이다(카테고리 번호와 무관).
- `general` 파일명은 의미 이름(kebab/underscore)을 쓴다(예: `pki-basics.md`, `zero-trust.md`). 공백 금지(§2).
- references 링크 상대경로: fundamentals 문서 → `../references/{폴더}/README.md`.

### 3.3 참조 문서 (`reference`) — 참조 템플릿

`5g-security/references/*/README.md`는 이슈 문서가 인용하는 표준·기관·논문의 **정의집**이다.
표(코드 ↔ 정식 명칭 ↔ 관련 이슈 영역) 형식을 기본으로 하며, 참조 코드(TS/TR, EU-N, US-N, P-N)를
`subject/`의 정의와 일치시킨다. 새 참조를 임의로 만들지 않는다(환각 금지, §5·§6).

---


## 4. SUMMARY.md 갱신 규칙

`SUMMARY.md`는 GitBook 목차의 단일 소스다. 문서를 추가/이동/삭제하면 **반드시** 함께 갱신한다.

### 계층 구조 (중요)
`SUMMARY.md`는 **2개 최상위 묶음(`##` 헤더)** 으로 구성한다.

```markdown
## Security Fundamentals   # 일반 보안 지식 (security-fundamentals/)
## 5G Security             # 5G 보안 영역 전체 (5g-security/)
```

`5G Security` 묶음은 **부모 항목(`5g-security/README.md`)** 아래에
`fundamentals` / `security-risks` / `references` 세 하위영역을 **들여쓰기로 중첩**한다.
그래야 GitBook 사이드바에서 `5G Security` 아래에 세 하위영역이 접기/펼치기로 보인다.

```markdown
## 5G Security
* [5G Security](5g-security/README.md)
  * [Fundamentals](5g-security/fundamentals/README.md)
    * [01-01 5G Key Hierarchy](5g-security/fundamentals/01-01-5G_Key_Hierarchy.md)
  * [Security Risks](5g-security/security-risks/README.md)
    * [NN. {Category Title}](5g-security/security-risks/NN-folder/README.md)
      * [NN-MM {Issue Name}](5g-security/security-risks/NN-folder/NN-MM-{Issue_Name}.md)
  * [References](5g-security/references/README.md)
    * [3GPP / O-RAN Standards](5g-security/references/3gpp-standards/README.md)
```

- **부모 항목**은 반드시 그 영역/하위영역/카테고리의 `README.md`를 가리킨다 (§1의 README 필수 규칙과 연동).
- **자식 항목**은 부모 아래 **공백 2칸씩 들여쓰기**로 둔다 → 이때만 GitBook이 접기 화살표를 만든다.
  security-risks 이슈는 `5g-security → security-risks → 카테고리 → 이슈`로 4단 들여쓰기(8칸)가 된다.
- `## 헤더`는 위 2개 최상위 묶음에만 쓴다. 하위영역을 `## 헤더`로 두면 `5G Security` 부모로 묶이지 않는다.
- 링크 경로는 리포지토리 루트 기준 전체 경로(`5g-security/...`)를 쓴다.

---

## 5. 언어 및 스타일

- 본문 설명은 **한국어**로 작성한다. (기존 문서 스타일 유지)
- 기술 용어(SUPI, gNB, NAS, RRC, NRF 등)와 표준 명칭(TS 33.501 등)은 원문 그대로 사용.
- 제목(`# NN-MM. Title`)의 이슈명은 영문 유지.
- `concept`/`general` 문서 제목은 개념명(영문 유지 가능)으로 자유롭게 쓴다(§3.2).
- 문장은 간결하게. 과장 없이 사실 위주로.
- 표준/논문을 인용할 때 없는 내용을 지어내지 않는다 (환각 금지). 근거가 없으면 명시하지 않는다.

---

## 6. 출처 및 저작권 규칙 (중요)

이 지식베이스는 ENISA / NIST / CISA·NSA / 3GPP / 연구논문 등 **외부 자료를 기반**으로 한다.
따라서 모든 문서는 아래 저작권·출처 규칙을 반드시 준수한다.
(근거: `subject/5G_Security.md`의 ENISA 재사용 정책 및 문서화 유의사항)

### 6.1 출처(오리진) 표시 의무
- 외부 자료를 참고한 내용에는 **반드시 출처를 명시**한다.
- ENISA 자료는 "출처 표시를 조건으로 재사용 허용"이며, 일부는 **CC BY 4.0**(출처표시 + 변경사항 표시)이다.
- 출처 표기 예시:
  - `Source: ENISA, "Threat Landscape for 5G Networks", 2020.`
  - `Source: NIST, CSWP 36A "Protecting Subscriber Identifiers with SUCI", 2026.`
  - `Source: CISA/NSA, "5G Network Slicing Security Considerations".`
  - `Source: 3GPP, TS 33.501.`
- 각 이슈 문서의 참조 코드(US-N/EU-N/P-N/TS·TR)는 이미 `5g-security/references/` 하위 정의 문서로 연결되므로,
  본문에서 원문 내용을 직접 옮겨 쓴 경우에만 별도 출처 문구를 추가한다.

### 6.2 원문과 작성자 해설을 구분
- 외부 자료의 요약과 **작성자(본 지식베이스)의 해설/분석을 명확히 구분**한다.
- 작성자의 추가 분석을 ENISA/NIST 등 기관의 공식 입장처럼 보이게 하지 않는다.
- 필요 시 소제목이나 인용구(`>`)로 "원자료 요약"과 "해설"을 시각적으로 분리한다.

### 6.3 원문 복사 금지 — 재구성 원칙
- 원문을 **그대로 복사·번역만 하지 않는다.** 핵심을 파악해 한국어로 재구성하고,
  3GPP 표준 + 논문 + 공격 시나리오 + 대응 방안을 **연결·해설**한다.
- 이 지식베이스의 가치는 "번역"이 아니라 "여러 출처를 연결한 재구성"에 있다.

### 6.4 그림·로고·제3자 자료
- **기관 로고(ENISA 등)를 사용하지 않는다.** 텍스트 출처 표기만 사용한다.
- 외부 문서 안의 **그림/사진/도표를 그대로 가져오지 않는다.** (제3자 저작권일 수 있음)
- 다이어그램이 필요하면 `rules-diagrams.md`에 따라 **직접 Mermaid/SVG로 새로 그린다.**

### 6.5 (선택) 출처 섹션
원문 내용을 상당 부분 참고한 문서는 10항목 섹션 뒤에 `## 출처` 섹션을 추가할 수 있다.
```markdown
## 출처
- ENISA, "Threat Landscape for 5G Networks", 2020. (EU-1)
- NIST, CSWP 36A, 2026. (US-2)
- 3GPP, TS 33.501. / 논문 P1
```

---

## 7. 인코딩 / 개행

- 파일 인코딩은 **UTF-8**. (기존 일부 파일에 BOM `﻿`이 있으나 신규 파일은 BOM 없는 UTF-8 권장)
- 개행은 리포지토리 기존 설정을 따른다.

---

## 8. 체크리스트 (문서 1건 작성/수정 후)

- [ ] 파일명이 `NN-MM-{Issue_Name}.md` 패턴과 일치하는가 (공백 없이 `_` 사용)
- [ ] 제목이 `# NN-MM. {Issue Name}` 형식인가
- [ ] 10항목 섹션(개요/공격대상/취약점/공격시나리오/영향/대응/3GPP·O-RAN/US/EU/논문)이 순서대로 있는가
- [ ] 핵심 콘텐츠 섹션(2~6)이 참조 나열이 아니라 실제 해설로 채워졌는가
- [ ] 참조 코드(7~10)가 `subject-list.md` 정의와 일치하는가 (지어내지 않았는가)
- [ ] 외부 자료 원문을 그대로 복사하지 않고 재구성했는가 (§6.3)
- [ ] 원문 내용을 옮겼다면 출처를 명시했는가 (§6.1)
- [ ] 원문 요약과 작성자 해설이 구분되는가 (§6.2)
- [ ] 로고/제3자 그림을 무단 사용하지 않았는가, 다이어그램은 직접 그렸는가 (§6.4)
- [ ] `SUMMARY.md`에 항목이 추가/갱신되었고 (카테고리 부모 README + 2칸 들여쓰기 자식 계층), 링크 경로가 실제 파일명(언더스코어)과 일치하는가
- [ ] 다이어그램을 넣었다면 `rules-diagrams.md` 규칙을 따랐는가
- [ ] GitHub/GitBook 양쪽에서 렌더링 가능한 문법만 사용했는가
