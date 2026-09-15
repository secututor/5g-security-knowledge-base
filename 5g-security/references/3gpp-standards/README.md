# 12. 3GPP / O-RAN 표준

각 이슈 문서의 **3GPP / O-RAN 표준** 섹션에서 참조하는 TS(Technical Specification) / TR(Technical Report) 및 O-RAN 규격의 정의입니다.
국제 이동통신 표준 관점에서 5G 보안 메커니즘을 정의합니다.

> TS = 규범적 규격(정식 표준), TR = 연구/보고서(스터디). 번호는 시리즈별로 분류됩니다.

---

## 보안 아키텍처 (33 시리즈)

| 표준 | 제목 / 내용 | 관련 이슈 영역 |
|------|-------------|----------------|
| **TS 33.501** | 5G System 보안 아키텍처 및 절차 (핵심 보안 규격) | 인증, NAS/AS 보안, 키 관리, SUCI, SBA 보안 전반 |
| **TR 33.809** | False Base Station(FBS) 대응 보안 강화 연구 | FBS, Rogue gNB, IMSI/SUPI catching |
| **TS 33.536** | V2X 서비스 보안 | V2X 메시지 위조, Sybil, Replay |
| **TS 33.117** | 보안 보증(SCAS) 카탈로그 | Supply Chain |

## 시스템 아키텍처 (23 시리즈)

| 표준 | 제목 / 내용 | 관련 이슈 영역 |
|------|-------------|----------------|
| **TS 23.501** | 5G System 아키텍처 (Stage 2) | Core, Slicing, Multi-tenant |
| **TS 23.502** | 5G System 절차 (Stage 2) | AMF/SMF, Paging |
| **TS 23.287** | V2X 지원 아키텍처 강화 | V2X |

## NAS / 프로토콜 (24 시리즈)

| 표준 | 제목 / 내용 | 관련 이슈 영역 |
|------|-------------|----------------|
| **TS 24.501** | 5GS Non-Access-Stratum(NAS) 프로토콜 | NAS 메시지, Registration/Deregistration/Service Request |

## NR 무선 (38 시리즈)

| 표준 | 제목 / 내용 | 관련 이슈 영역 |
|------|-------------|----------------|
| **TS 38.211** | NR 물리 채널 및 변조 | Jamming, Physical-layer spoofing, Sync signal |
| **TS 38.212** | NR 다중화 및 채널 코딩 | 물리 계층 |
| **TS 38.213** | NR 물리 계층 제어 절차 | PDCCH, HARQ, Timing |
| **TS 38.300** | NR 및 NG-RAN 전체 설명 (Stage 2) | Radio resource exhaustion |
| **TS 38.321** | NR MAC 프로토콜 | RACH, MAC CE, HARQ |
| **TS 38.331** | NR RRC 프로토콜 | RRC 조작/해제/재구성 |
| **TS 38.401** | NG-RAN 아키텍처 | gNB, RAN 설정/시그널링 |
| **TS 38.413** | NGAP (NG Application Protocol) | NGAP flooding/manipulation |
| **TS 38.423** | XnAP (Xn Application Protocol) | Xn 공격/DoS |
| **TS 38.463** | E1AP (E1 인터페이스) | E1 attack (CU-CP↔CU-UP) |
| **TS 38.473** | F1AP (F1-C 인터페이스) | F1-C attack (CU-DU control) |
| **TS 38.475** | F1-U (F1 user plane) | F1-U attack (CU-DU user-plane) |

## Core / SBI (29 시리즈)

| 표준 | 제목 / 내용 | 관련 이슈 영역 |
|------|-------------|----------------|
| **TS 29.244** | PFCP (SMF-UPF 제어) | PFCP manipulation |
| **TS 29.281** | GTP-U (User-plane 터널링) | GTP-U spoofing |
| **TS 29.500** | 5GC SBI 일반 (Service Based Interface) | SBA API, HTTP/2, NF flooding |
| **TS 29.501** | SBI — API 설계 원칙 및 규약 | API parameter manipulation |
| **TS 29.503** | UDM 서비스 | UDM data exposure |
| **TS 29.504** | UDR 서비스 | UDR data exposure |
| **TS 29.507** | PCF 정책 서비스 | PCF manipulation |
| **TS 29.509** | AUSF 인증 서버 서비스 | AUSF attack |
| **TS 29.510** | NRF (NF Repository) 서비스 | NRF/NF discovery |

## 관리 / 오케스트레이션 (28 시리즈)

| 표준 | 제목 / 내용 | 관련 이슈 영역 |
|------|-------------|----------------|
| **TS 28.500** | 관리 개념/NFV 관리 (series) | VM/Container escape, Orchestrator, Cloud |
| **TS 28.530** | Network Slicing 관리 개념/요구사항 | Slice 설정/lifecycle/관리 API |
| **TS 28.531** | Network Slicing provisioning | Slice provisioning/lifecycle |

## O-RAN Alliance 규격

3GPP 외에 O-RAN Alliance가 규격화하는 영역은 **O-RAN WG(Working Group)**을 함께 표기한다.

| 규격 | 내용 | 관련 이슈 영역 |
|------|------|----------------|
| **O-RAN WG11** | 보안 워킹그룹 (Security) | Near-RT RIC, xApp, E2/A1, AI/ML |
| **O-RAN WG2** | Non-RT RIC / A1 | Malicious xApp, A1 |
| **O-RAN E2 / A1 인터페이스** | RIC ↔ 노드 인터페이스 규격 | E2/A1 interface attack |

---

## 공식 접근 경로

- 3GPP Specification Search: `https://www.3gpp.org/specifications-technologies/specifications-search`
- 3GPP FTP (전체 규격 저장소): `https://www.3gpp.org/ftp/Specs/archive/`
  - 팁: `33 series`(Security) 폴더에서 33.501, 33.809 등 핵심 보안 규격 확인
- O-RAN Alliance 규격: O-RAN Alliance 공식 사이트의 Specifications

> 표준 번호/제목은 마스터 데이터(`subject/5G_Security.md`, `subject/subject-list.md`) 기준이다.
> 버전(Release)은 시점에 따라 다르므로, 정확한 버전이 필요하면 3GPP 검색으로 최신 버전을 확인한다.
