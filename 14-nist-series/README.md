# 14. US 보안 가이드라인 (NIST & CISA/NSA)

미국 정부기관의 5G 보안 자료입니다. 각 이슈 문서의 **관련 US 가이드라인** 섹션에서 참조하는 `US-N` 코드의 정의입니다.

- **US-1 ~ US-7**: NIST (National Institute of Standards and Technology) — 기술·실무 구현/검증 관점
- **US-8**: CISA / NSA — 위협·국가안보·운영 위험 관점

> NIST는 NCCoE 5G 테스트베드에서 보안 기능을 실제로 구현·시험합니다. CISA/NSA는 실제 운영 환경의 공격 벡터와 위험 완화에 초점을 둡니다.

---

## NIST CSWP 36 시리즈

NIST의 5G Cybersecurity 백서 시리즈입니다. "Applying 5G Cybersecurity and Privacy Capabilities"라는 이름으로 발행되었습니다.

| 코드 | 자료 | 다루는 문제 |
|------|------|-------------|
| **US-1** | NIST CSWP 36 (시리즈 전체) | 5G Cybersecurity & Privacy 전체 개요 |
| **US-2** | NIST CSWP 36A | SUCI — 가입자 식별자(SUPI) 보호 |
| **US-3** | NIST CSWP 36B | Hardware(-enabled) Root of Trust / 플랫폼 무결성 |
| **US-4** | NIST CSWP 36C | Temporary Identity(GUTI 등) 재할당 |
| **US-5** | NIST CSWP 36D | No-SUPI-based Paging (Paging 시 SUPI 노출 방지) |
| **US-6** | NIST CSWP 36E | 5G Network Security Design Principles |
| **US-7** | NIST CSWP 36F | Initial NAS Message Security (Initial Public Draft) |

### 특징
- **36A(US-2)**: SUCI로 SUPI를 암호화해 식별자 노출/추적을 막는 방법.
- **36B(US-3)**: Hardware Root of Trust + Remote Attestation으로 플랫폼 무결성을 보장.
- **36C(US-4)**: 임시 식별자를 적절히 갱신(재할당)해 위치·신원 추적을 방지.
- **36D(US-5)**: Paging 과정에서 SUPI가 노출되지 않도록 하는 설계.
- **36E(US-6)**: 5G 네트워크(코어/인프라) 보안 설계 원칙.
- **36F(US-7)**: Initial NAS Message의 민감정보를 암호화·무결성 보호로 지킨다.

> NIST가 특히 강조하는 프라이버시 3대 주제: **SUCI, Temporary Identity, No-SUPI Paging** (US-2/US-4/US-5).

---

## CISA / NSA (US-8)

| 코드 | 자료 | 다루는 문제 |
|------|------|-------------|
| **US-8** | CISA 5G Security and Resilience Library | 5G 인프라 위협 벡터, Network Slicing, Cloud Infrastructure 보안 |

### 포함 자료 (CISA 5G Library)
- **Potential Threat Vectors to 5G Infrastructure** — 5G 인프라 영역별 위협 벡터
- **5G Network Slicing: Security Considerations for Design, Deployment, and Maintenance** (CISA/NSA/ODNI, Enduring Security Framework)
- **5G Cloud Security** 시리즈 (CISA/NSA)
  - Part I — Prevent and Detect Lateral Movement
  - Part II — Securely Isolate Network Resources
  - Part III — Data Protection
  - Part IV — Ensure Integrity of Cloud Infrastructure

---

## 공식 접근 경로

문서의 정적 URL은 자주 바뀌므로 공식 검색/라이브러리를 통해 접근하는 것을 권장합니다.

- NIST CSRC Publications: `https://csrc.nist.gov/publications` — 검색어 `CSWP 36` 또는 `Applying 5G Cybersecurity`
- CISA 5G Resource Library: `https://www.cisa.gov/5g-library`

---

## 출처 표기 원칙
- 원문을 그대로 복사하지 말고, 핵심을 한국어로 재구성하며 출처를 명시한다.
- 예: `Source: NIST, CSWP 36A "Protecting Subscriber Identifiers with SUCI", 2026.`
- 예: `Source: CISA/NSA, "5G Network Slicing Security Considerations".`
