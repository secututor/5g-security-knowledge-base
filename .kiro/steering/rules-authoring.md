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

카테고리별로 번호가 붙은 디렉토리에 문서를 배치합니다.

```
5g-security-knowledge-base/
├── SUMMARY.md              # GitBook 목차 (필수, 신규 문서 추가 시 반드시 갱신)
├── README.md               # 사이트 소개 페이지
├── gitbook-docs.yaml       # GitBook 사이트 설정 (수정 지양)
├── 01-fundamentals/        # 기본 개념/개요
├── 02-ue-privacy/          # UE & Privacy Security
├── 03-auth-nas/            # Authentication & NAS Security
├── 04-ran-security/        # RAN Security
├── 05-gnb-interfaces/      # gNB Interfaces & Protocols
├── 06-core-security/       # Core Network Security
├── 07-sba-security/        # SBA & Service Security
├── 08-network-slicing/     # Network Slicing Security
├── 09-nfv-cloud/           # NFV & Cloud Native Security
├── 10-oran-security/       # O-RAN Security
├── 11-v2x-supply-chain/    # V2X & Supply Chain Security
├── 12-3gpp-standards/      # 3GPP 표준 참조
├── 13-enisa-framework/     # ENISA 프레임워크 참조
├── 14-nist-series/         # NIST 시리즈 참조 (US 가이드라인: NIST+CISA)
├── 15-research-papers/     # 참조 논문
├── subject/                # 원본 마스터 데이터 (편집용, 사이트 목차엔 미포함)
├── ai/                     # 사람용 안내/프롬프트 (사이트 목차엔 미포함)
├── .gitbook/assets/        # 이미지/SVG (GitBook 표준 경로, 사이트 목차엔 미포함)
└── .kiro/steering/         # AI 자동 로드 규칙 (rules-authoring.md, rules-diagrams.md)
```

### 규칙
- 새 카테고리는 `NN-{kebab-case-name}/` 형식으로 만든다. `NN`은 2자리 0-padding 번호.
- 카테고리 폴더 번호는 `subject/subject-list.md`의 섹션(A~J) 분류 체계와 일치시킨다.
- **모든 카테고리 폴더에는 `README.md`(개요 + 이슈 목록)를 둔다.** 이 README가 SUMMARY 계층의 부모 항목이 된다 (§4).
- `subject/`, `ai/`, `.kiro/`, `.gitbook/`은 **작업/설정용**이며 `SUMMARY.md` 목차에는 넣지 않는다.

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
02-ue-privacy/02-01-SUPI_Exposure.md
03-auth-nas/03-01-5G-AKA_Attack_Surface.md
07-sba-security/07-06-OAuth_Token_Abuse.md
```

### 규칙
- 이슈명은 `subject/subject-list.md` 테이블의 **Security Issue** 컬럼을 기준으로 하되,
  **공백은 `_`로 바꾸고**, 파일 시스템에서 문제가 되는 문자(`/`, `'`)는 아래처럼 정규화한다.
  - 공백 → `_` (예: `SUPI Exposure` → `SUPI_Exposure`)
  - `EAP-AKA'` → `EAP-AKA_prime` (예: `03-02-EAP-AKA_prime_Attack.md`)
  - `IMSI/SUPI` → `IMSI-SUPI` (예: `02-02-IMSI-SUPI_Catching.md`)
  - `HTTP/2` → `HTTP2` (예: `07-07-HTTP2_DoS.md`)
  - `AI/ML` → `AI-ML` (예: `10-05-AI-ML_Model_Poisoning.md`)
  - `Hardware/Platform` → `Hardware-Platform`
- 하이픈(`-`)은 구분자(`NN-MM-`) 및 기존 정규화(`IMSI-SUPI` 등)에만 쓰고, 단어 사이 공백 대체는 `_`로 한다.
- 개요/랜딩 페이지는 카테고리 폴더에 `README.md`로 둔다 (신규 카테고리는 `README.md`로 통일).

---

## 3. 문서 섹션 구조 (이슈 문서)

모든 이슈 문서는 `subject/5G_Security.md`가 제안한 **10항목 풀 템플릿**을 따른다.
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
{TS/TR 번호. 여러 개면 쉼표로. 예: TS 33.501, TR 33.809. → 12-3gpp-standards 참조}

## 8. 관련 US 가이드라인
{US-N 형식. 예: US-2 또는 US-4,5. → 14-nist-series 참조. 관점: NIST=구현/검증, CISA·NSA=위협/안보}

## 9. 관련 EU 가이드라인
{EU-N 형식. 예: EU-1. → 13-enisa-framework 참조. 관점: ENISA=위협 지형}

## 10. 참조 논문
{P번호. 예: P1, P2. → 15-research-papers 참조}
```

### 규칙
- **10개 섹션 모두 포함**한다. 다만 근거가 부족한 섹션(예: 특정 이슈에 대한 논문 없음)은
  억지로 채우지 말고 "해당 없음" 또는 비워두고 사유를 남긴다 (환각 금지).
- 섹션 7~10의 **참조 코드(US-N, EU-N, P-N, TS/TR)**는 임의로 만들지 말고
  `subject/subject-list.md` 및 `subject/5G_Security.md`의 정의를 그대로 사용한다.
- 섹션 2~6(공격 대상/취약점/시나리오/영향/대응)은 이 지식베이스의 **핵심 콘텐츠**다.
  단순 참조 나열에 그치지 말고 4대 출처(3GPP/ENISA/NIST/CISA·NSA)와 논문을 **연결·해설**한다.
- 관점 교차: 같은 이슈라도 ENISA(위협 지형) / NIST(구현·검증) / CISA·NSA(위협·안보) / 3GPP(표준)의
  서로 다른 시각을 본문에 녹인다.

### 선택 섹션 (필요 시 추가)
```markdown
## 관련 이슈            # 다른 NN-MM 문서로의 상호 참조 링크
## 출처                 # 원문을 상당 부분 참고한 경우 (§6.5 참조)
```

---


## 4. SUMMARY.md 갱신 규칙

`SUMMARY.md`는 GitBook 목차의 단일 소스다. 문서를 추가/이동/삭제하면 **반드시** 함께 갱신한다.

### 계층 구조 (중요)
GitBook 사이드바에서 카테고리가 **접기/펼치기(화살표)** 되게 하려면,
카테고리를 `## 헤더`로 두지 말고 **부모 항목(카테고리 README 링크) + 들여쓰기(2칸)한 자식**으로 작성한다.

```markdown
* [NN. {Category Title}](NN-folder/README.md)
  * [NN-MM {Issue Name}](NN-folder/NN-MM-{Issue_Name}.md)
  * [NN-MM {Issue Name}](NN-folder/NN-MM-{Issue_Name}.md)
```

- **부모 항목**은 반드시 그 카테고리의 `README.md`를 가리킨다 (§1의 카테고리 README 필수 규칙과 연동).
- **자식 항목**은 부모 아래 **공백 2칸 들여쓰기**로 둔다 → 이때만 GitBook이 접기 화살표를 만든다.
- `## 헤더`는 큰 묶음(예: `## 5G Security Issues`, `## References`)에만 쓴다.
  카테고리 자체를 `## 헤더`로 두면 평면(flat) 목록이 되어 접히지 않는다.

### 링크 경로
파일명에 공백이 없으므로(§2) **URL 인코딩(`%20`)이 필요 없다.** 실제 파일 경로를 그대로 쓴다.

- 리스트 라벨(`02-01 SUPI Exposure`)은 사람이 읽기 좋게 공백으로 표기해도 된다 (링크 경로만 정확하면 됨).
- 링크 경로는 실제 파일 경로(언더스코어 포함)와 정확히 일치시킨다.
- 항목 순서는 번호 오름차순 유지.

---

## 5. 언어 및 스타일

- 본문 설명은 **한국어**로 작성한다. (기존 문서 스타일 유지)
- 기술 용어(SUPI, gNB, NAS, RRC, NRF 등)와 표준 명칭(TS 33.501 등)은 원문 그대로 사용.
- 제목(`# NN-MM. Title`)의 이슈명은 영문 유지.
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
- 각 이슈 문서의 참조 코드(US-N/EU-N/P-N/TS·TR)는 이미 `12`~`15` 폴더의 정의 문서로 연결되므로,
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
