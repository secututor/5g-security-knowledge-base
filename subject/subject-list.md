# 100개 5G Security Issue Database

> **개요**: 5G 네트워크 보안 이슈 100선에 대한 표준(3GPP, O-RAN), 글로벌 보안 가이드라인(US NIST/CISA/NSA, EU ENISA), 논문 참조 및 한국어 상세 설명 데이터베이스입니다.

---

## A. UE / Subscriber / Privacy (02-01 ~ 02-15)

> 💡 **NIST 강조 사항**: NIST 가이드라인에서는 특히 **SUCI, Temporary Identity, No-SUPI Paging** 관련 보안 대책을 강조합니다.

| # | Security Issue | 관련 US | 관련 EU | 3GPP Standard | 논문 | 사이트용 한국어 설명 |
|---|---|---|---|---|---|---|
| 02-01 | **SUPI Exposure** | US-2 | EU-1 | TS 33.501 | P1, P2 | 가입자의 영구 식별자인 SUPI가 공격자에게 노출되는 문제 |
| 02-02 | **IMSI/SUPI Catching** | US-2 | EU-1 | TR 33.809, TS 33.501 | P1 | 가짜 기지국 등을 이용해 가입자 식별자를 수집하는 공격 |
| 02-03 | **SUCI Null Scheme** | US-2 | EU-3 | TS 33.501 | P1 | SUCI를 사용하더라도 null protection을 사용하면 식별정보 보호 효과가 제한되는 문제 |
| 02-04 | **SUCI Misconfiguration** | US-2 | EU-2 | TS 33.501 | P1 | SUCI 보안 설정 오류로 가입자 privacy가 약화되는 문제 |
| 02-05 | **False Base Station** | US-2 | EU-1 | TR 33.809 | P1 | 공격자가 정상 gNB처럼 위장해 UE를 유인하는 공격 |
| 02-06 | **Rogue gNB** | US-2 | EU-1 | TR 33.809, TS 33.501 | P1 | 악성 gNB를 이용한 가입자 및 signaling 공격 |
| 02-07 | **Temporary Identity Tracking** | US-4 | EU-1 | TS 33.501 | P1 | 임시 식별자의 장기간 사용을 이용한 사용자 추적 |
| 02-08 | **GUTI Reallocation Failure** | US-4 | EU-2 | TS 33.501 | P1 | 임시 ID를 적절히 갱신하지 않아 위치·신원 추적이 가능해지는 문제 |
| 02-09 | **SUPI-based Paging** | US-5 | EU-1 | TS 24.501, TS 23.502 | P1 | Paging에서 SUPI가 사용될 경우 가입자 위치정보가 노출될 수 있는 문제 |
| 02-10 | **Paging Privacy Leakage** | US-5 | EU-1 | TS 23.502 | P1 | Paging 패턴을 이용한 특정 가입자의 존재·위치 추적 |
| 02-11 | **Initial NAS Information Exposure** | US-7 | EU-3 | TS 24.501, TS 33.501 | P1 | Initial NAS Message에 민감정보가 노출될 수 있는 문제 |
| 02-12 | **NAS Message Tampering** | US-7 | EU-3 | TS 24.501, TS 33.501 | P1 | NAS signaling이 변조되는 공격 |
| 02-13 | **NAS Replay** | US-7 | EU-1 | TS 33.501 | P1 | 과거 NAS 메시지를 재전송해 정상 절차를 혼란시키는 공격 |
| 02-14 | **UE Identity Tracking** | US-4,5 | EU-1 | TS 33.501 | P1, P2 | 여러 무선 이벤트를 결합해 사용자를 지속적으로 추적하는 공격 |
| 02-15 | **UE Privacy Configuration Error** | US-2,4,5 | EU-2 | TS 33.501 | P1 | 표준에 있는 privacy 기능을 운영자가 제대로 활성화하지 않아 발생하는 문제 |

---

## B. Authentication / NAS / UE Control (03-01 ~ 03-10)

| # | Security Issue | US | EU | 3GPP Standard | Paper | 한국어 설명 |
|---|---|---|---|---|---|---|
| 03-01 | **5G-AKA Attack Surface** | US-1 | EU-3 | TS 33.501 | P1, P2 | 5G AKA 인증절차를 대상으로 하는 공격면 |
| 03-02 | **EAP-AKA' Attack** | US-1 | EU-3 | TS 33.501 | P1 | EAP 기반 인증 절차의 오용 또는 구현 취약점 |
| 03-03 | **Authentication DoS** | US-1 | EU-1 | TS 33.501 | P1, P4 | 인증 요청을 대량 발생시켜 네트워크 자원을 고갈시키는 공격 |
| 03-04 | **Authentication Relay** | US-1 | EU-1 | TS 33.501 | P1 | 정상 인증 메시지를 중계해 인증 절차를 우회하려는 공격 |
| 03-05 | **Authentication Context Exposure** | US-1 | EU-3 | TS 33.501 | P1 | 인증 관련 context가 잘못 관리되어 노출되는 문제 |
| 03-06 | **Security Context Desynchronization** | US-1 | EU-3 | TS 33.501 | P1 | UE와 네트워크의 보안 context가 서로 달라지는 문제 |
| 03-07 | **NAS Security Downgrade** | US-7 | EU-1 | TS 33.501 | P1 | 강력한 NAS 보안 대신 약한 보안 상태로 유도하는 공격 |
| 03-08 | **Registration Request Flooding** | US-8 | EU-1 | TS 24.501 | P1 | Registration 요청을 폭주시켜 AMF 자원을 소모시키는 공격 |
| 03-09 | **Deregistration Abuse** | US-1 | EU-1 | TS 24.501 | P1 | Deregistration 절차를 악용해 UE 서비스를 방해 |
| 03-10 | **Service Request Abuse** | US-1 | EU-1 | TS 24.501 | P1 | Service Request를 반복 발생시켜 signaling/resource를 소모 |

---

## C. RAN / Radio Interface (04-01 ~ 04-15)

| # | Security Issue | US | EU | 3GPP Standard | Paper | 한국어 설명 |
|---|---|---|---|---|---|---|
| 04-01 | **RF Jamming** | US-8 | EU-1 | TS 38.211 | P1, P2 | 무선 주파수를 방해해 통신 자체를 마비 |
| 04-02 | **PDCCH Jamming** | US-8 | EU-1 | TS 38.211, TS 38.213 | P1 | 제어채널을 집중적으로 방해 |
| 04-03 | **PDSCH Jamming** | US-8 | EU-1 | TS 38.211 | P1 | DL 데이터 전송을 방해 |
| 04-04 | **PUSCH Jamming** | US-8 | EU-1 | TS 38.211 | P1 | UL 데이터 전송을 방해 |
| 04-05 | **PRACH Attack** | US-8 | EU-1 | TS 38.211, TS 38.321 | P1 | Random Access 절차를 공격 |
| 04-06 | **RACH Flooding** | US-8 | EU-1 | TS 38.321 | P1 | RACH 요청을 폭주시켜 무선 자원을 고갈 |
| 04-07 | **RRC Manipulation** | US-1 | EU-1 | TS 38.331 | P1 | RRC 메시지를 악용한 제어 공격 |
| 04-08 | **RRC Release Attack** | US-1 | EU-1 | TS 38.331 | P1 | RRC 연결을 반복적으로 끊어 서비스 방해 |
| 04-09 | **RRC Reconfiguration Abuse** | US-1 | EU-1 | TS 38.331 | P1 | RRC 재구성 절차를 악용 |
| 04-10 | **MAC CE Abuse** | US-1 | EU-3 | TS 38.321 | P1 | MAC Control Element를 이용한 protocol abuse |
| 04-11 | **HARQ Manipulation** | US-8 | EU-1 | TS 38.321, TS 38.213 | P1 | HARQ 동작을 방해하여 통신 성능 저하 |
| 04-12 | **Timing Attack** | US-8 | EU-1 | TS 38.211, TS 38.213 | P1 | 시간 동기 관련 정보를 공격 |
| 04-13 | **Synchronization Signal Attack** | US-8 | EU-1 | TS 38.211 | P1 | synchronization signal을 이용한 공격 |
| 04-14 | **Physical-layer Spoofing** | US-8 | EU-1 | TS 38.211 | P1, P2 | 정상 무선 신호처럼 위조 |
| 04-15 | **Radio Resource Exhaustion** | US-8 | EU-1 | TS 38.300 series | P1 | 무선 자원을 고갈시키는 DoS |

---

## D. gNB / NG-RAN Interfaces (05-01 ~ 05-10)

| # | Security Issue | US | EU | 3GPP Standard | Paper | 한국어 설명 |
|---|---|---|---|---|---|---|
| 05-01 | **gNB Impersonation** | US-8 | EU-1 | TS 38.401 | P1 | 공격자가 정상 gNB로 위장 |
| 05-02 | **NGAP Flooding** | US-8 | EU-1 | TS 38.413 | P1, P4 | gNB-AMF 간 NGAP signaling 폭주 |
| 05-03 | **NGAP Manipulation** | US-1 | EU-3 | TS 38.413 | P1 | NGAP 메시지 변조 |
| 05-04 | **XnAP Attack** | US-8 | EU-1 | TS 38.423 | P1 | gNB 간 Xn signaling 공격 |
| 05-05 | **Xn Interface DoS** | US-8 | EU-1 | TS 38.423 | P1 | Xn interface 자원 고갈 |
| 05-06 | **F1-C Attack** | US-6 | EU-2 | TS 38.473 | P1 | CU-DU control interface 공격 |
| 05-07 | **F1-U Attack** | US-6 | EU-2 | TS 38.475 | P1 | CU-DU user-plane interface 공격 |
| 05-08 | **E1 Attack** | US-6 | EU-2 | TS 38.463 | P1 | CU-CP와 CU-UP 사이 interface 공격 |
| 05-09 | **RAN Configuration Tampering** | US-6 | EU-2 | TS 38.401 | P1 | gNB 설정값을 불법 변경 |
| 05-10 | **RAN Signaling Storm** | US-6 | EU-1 | TS 38.401 | P1 | 대량 signaling으로 RAN 자원을 고갈 |

---

## E. 5G Core (06-01 ~ 06-10)

| # | Security Issue | US | EU | 3GPP Standard | Paper | 한국어 설명 |
|---|---|---|---|---|---|---|
| 06-01 | **AMF DoS** | US-6 | EU-1 | TS 23.501, TS 23.502 | P1, P4 | AMF에 요청을 집중시켜 핵심 control-plane 마비 |
| 06-02 | **SMF DoS** | US-6 | EU-1 | TS 23.502 | P1, P4 | PDU Session 요청을 이용한 SMF 공격 |
| 06-03 | **UPF DoS** | US-6 | EU-1 | TS 23.501 | P1 | User-plane 자원 고갈 |
| 06-04 | **UDM Data Exposure** | US-6 | EU-2 | TS 29.503 | P4 | 가입자 데이터가 UDM에서 노출 |
| 06-05 | **UDR Data Exposure** | US-6 | EU-2 | TS 29.504 | P4 | 가입자 데이터 저장소 공격 |
| 06-06 | **AUSF Attack** | US-1 | EU-3 | TS 29.509 | P1, P4 | 인증 서버를 대상으로 한 공격 |
| 06-07 | **PCF Manipulation** | US-6 | EU-2 | TS 29.507 | P4 | 정책을 조작하여 가입자 서비스 변경 |
| 06-08 | **NRF Attack** | US-6 | EU-2 | TS 29.510 | P3, P4 | Network Function Repository 공격 |
| 06-09 | **GTP-U Spoofing** | US-8 | EU-1 | TS 29.281 | P1 | User-plane 패킷 위조 |
| 06-10 | **PFCP Manipulation** | US-8 | EU-2 | TS 29.244 | P1, P4 | SMF-UPF 사이 PFCP 제어 메시지 공격 |

---

## F. SBA (Service Based Architecture) (07-01 ~ 07-10)

> 💡 **특이 사항**: 5G Core가 Cloud/API 기반으로 전환되면서 기존 통신망과 다른 공격면이 생성되었습니다. NIST 가이드에 따라 5G 표준 자체 보안 기능뿐만 아니라 기반 IT/Cloud Infrastructure 관점의 분석이 요구됩니다.

| # | Security Issue | US | EU | 3GPP Standard | Paper | 한국어 설명 |
|---|---|---|---|---|---|---|
| 07-01 | **NF Impersonation** | US-6 | EU-3 | TS 33.501 | P3 | 악성 NF가 정상 NF로 위장 |
| 07-02 | **NF Discovery Poisoning** | US-6 | EU-1 | TS 29.510 | P3 | NRF의 NF 정보를 조작 |
| 07-03 | **NRF Compromise** | US-6 | EU-2 | TS 29.510 | P3, P4 | NRF를 장악하여 NF 전체에 영향 |
| 07-04 | **SBA API Abuse** | US-6 | EU-2 | TS 29.500 | P3 | 정상 API 권한을 악용 |
| 07-05 | **API Parameter Manipulation** | US-6 | EU-2 | TS 29.501 | P3 | API 입력값을 조작 |
| 07-06 | **OAuth Token Abuse** | US-6 | EU-3 | TS 33.501 | P3 | 인증 token을 탈취하거나 악용 |
| 07-07 | **HTTP/2 DoS** | US-8 | EU-1 | TS 29.500 | P3, P4 | HTTP/2를 이용해 NF 자원 고갈 |
| 07-08 | **HTTP/2 Stream Multiplexing Attack** | US-8 | EU-1 | TS 29.500 | P3, P4 | 하나의 connection으로 다수 request를 보내 공격 |
| 07-09 | **NF Service Flooding** | US-8 | EU-1 | TS 29.500 | P3 | 특정 NF API를 대량 호출 |
| 07-10 | **Inter-NF Trust Abuse** | US-6 | EU-3 | TS 33.501 | P3, P4 | NF 간 신뢰관계를 악용 |

---

## G. Network Slicing (08-01 ~ 08-10)

> 💡 **CISA/NSA 지침 참조**: CISA/NSA는 *5G Network Slicing Security Considerations* (2022 Threat Guidance 및 2023 Design, Deployment, Operation/Maintenance) 지침을 별도로 발행하였습니다.

| # | Security Issue | US | EU | 3GPP Standard | Paper | 한국어 설명 |
|---|---|---|---|---|---|---|
| 08-01 | **Inter-Slice Attack** | US-8 | EU-1 | TS 23.501 | P5, P6 | 한 slice에서 다른 slice로 공격 확산 |
| 08-02 | **Intra-Slice Attack** | US-8 | EU-1 | TS 23.501 | P5, P6 | 동일 slice 내부의 자원/서비스 공격 |
| 08-03 | **Slice Isolation Failure** | US-8 | EU-2 | TS 23.501 | P5, P6 | slice 간 논리적 격리가 깨지는 문제 |
| 08-04 | **Cross-Slice DoS** | US-8 | EU-1 | TS 23.501 | P5, P6 | 한 slice의 공격이 다른 slice 자원까지 고갈 |
| 08-05 | **Slice Configuration Tampering** | US-8 | EU-2 | TS 28.530 | P5 | slice 설정을 불법 변경 |
| 08-06 | **Slice Lifecycle Attack** | US-8 | EU-2 | TS 28.530, TS 28.531 | P5, P6 | 생성·변경·삭제 lifecycle 공격 |
| 08-07 | **Slice Provisioning Attack** | US-8 | EU-2 | TS 28.531 | P5 | slice provisioning 과정 공격 |
| 08-08 | **Slice Tenant Isolation Failure** | US-8 | EU-2 | TS 23.501 | P5, P6 | 서로 다른 tenant 간 데이터/자원 격리 실패 |
| 08-09 | **Slice Resource Starvation** | US-8 | EU-1 | TS 23.501 | P5, P6 | 특정 slice가 공유 자원을 과도하게 점유 |
| 08-10 | **Slice Management API Attack** | US-8 | EU-2 | TS 28.530 series | P5, P6 | slice 관리 API를 공격 |

---

## H. NFV / Cloud / Container / MEC (09-01 ~ 09-10)

> 💡 **NIST SP 800-218B (NIST 36B) 참조**: Platform Integrity 문제를 해결하기 위해 Hardware Root of Trust와 Remote Attestation 기법을 실제 5G Testbed에 적용하는 방안을 기술합니다. CISA 역시 Lateral Movement, Isolation, Infrastructure Integrity를 별도 핵심 다룹니다.

| # | Security Issue | US | EU | 3GPP Standard | Paper | 한국어 설명 |
|---|---|---|---|---|---|---|
| 09-01 | **VM Escape** | US-8 | EU-2 | TS 28.500 series | P7 | VNF VM에서 host 환경으로 탈출 |
| 09-02 | **Container Escape** | US-8 | EU-2 | TS 28.500 | P7 | CNF container에서 host로 탈출 |
| 09-03 | **Hypervisor Attack** | US-8 | EU-2 | TS 28.500 | P7 | virtualization layer를 공격 |
| 09-04 | **Container Image Tampering** | US-8 | EU-2 | TS 28.500 | P7 | 악성 container image를 배포 |
| 09-05 | **VNF Image Tampering** | US-8 | EU-2 | TS 28.500 | P7 | VNF image 변조 |
| 09-06 | **Multi-Tenant Isolation Failure** | US-8 | EU-2 | TS 23.501 | P7 | 서로 다른 고객의 자원 격리 실패 |
| 09-07 | **Cloud Lateral Movement** | US-8 | EU-2 | TS 28.500 | P7 | 하나의 cloud 자원 장악 후 다른 NF로 이동 |
| 09-08 | **Orchestrator Compromise** | US-8 | EU-2 | TS 28.500 | P7 | MANO/orchestrator 장악 |
| 09-09 | **Cloud Configuration Tampering** | US-6 | EU-2 | TS 28.500 | P7 | cloud configuration 변경 |
| 09-10 | **Hardware/Platform Integrity Failure** | US-3 | EU-2 | TS 33.501 | P7 | 서버 플랫폼 자체의 무결성을 신뢰할 수 없는 문제 |

---

## I. O-RAN / Open RAN (10-01 ~ 10-05)

> 💡 **O-RAN 표준 구분**: O-RAN은 3GPP 규격 외에도 **O-RAN Alliance (WG11 등)** 표준 규격을 함께 명시 및 참조해야 합니다.

| # | Security Issue | US | EU | 3GPP / O-RAN Standard | Paper | 한국어 설명 |
|---|---|---|---|---|---|---|
| 10-01 | **Near-RT RIC Compromise** | US-6 | EU-1 | 38.401 + O-RAN WG11 | P8 | Near-RT RIC을 장악해 RAN 제어에 개입 |
| 10-02 | **Malicious xApp** | US-6 | EU-1 | O-RAN WG2/WG11 | P8 | 악성 xApp을 RIC에 설치 |
| 10-03 | **E2 Interface Attack** | US-6 | EU-1 | 38.401 + O-RAN E2/WG11 | P8 | RIC과 E2 Node 사이의 공격 |
| 10-04 | **A1 Interface Attack** | US-6 | EU-1 | O-RAN A1/WG11 | P8 | Non-RT RIC과 Near-RT RIC 사이 공격 |
| 10-05 | **AI/ML Model Poisoning** | US-6 | EU-1 | O-RAN WG11 | P8 | RAN 최적화에 사용되는 ML 모델을 오염 |

---

## J. V2X / Operational / Supply Chain (11-01 ~ 11-05)

| # | Security Issue | US | EU | 3GPP Standard | Paper | 사이트용 한국어 설명 |
|---|---|---|---|---|---|---|
| 11-01 | **V2X Message Spoofing** | US-8 | EU-1 | TS 23.287, TS 33.536 | P9 | 차량 메시지를 위조하여 다른 차량을 속이는 공격 |
| 11-02 | **V2X Sybil Attack** | US-8 | EU-1 | TS 33.536 | P9 | 하나의 공격자가 여러 차량 identity를 만들어내는 공격 |
| 11-03 | **V2X Replay Attack** | US-8 | EU-1 | TS 33.536 | P9 | 과거 차량 메시지를 재전송 |
| 11-04 | **Supply Chain Compromise** | US-8 | EU-2 | TS 33.117, TS 33.501 | P7 | 장비·소프트웨어·오픈소스 공급망을 통해 공격 |
| 11-05 | **5G Security Misconfiguration** | US-1,8 | EU-1,2,3 | TS 33.501 | P1, P7 | 표준에 보안기능이 존재하지만 실제 운영환경에서 잘못 설정해 발생하는 취약점 |
