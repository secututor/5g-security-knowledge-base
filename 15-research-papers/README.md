# 15. 참조 논문 (Research Papers)

각 이슈 문서의 **참조 논문** 섹션에서 사용하는 `P-N` 코드의 정의입니다.
논문마다 공통 Reference ID(P1~P9)를 부여해 이슈 문서에서 반복 인용합니다.

---

## 논문 코드 정의

| 코드 | 논문 | 주요 대상 영역 |
|------|------|----------------|
| **P1** | *A survey of existing attacks on 5G SA* (Computer Networks, 2025) | UE / RAN / Core |
| **P2** | *Towards secure 5G networks: A Survey* | 5G 전체 |
| **P3** | *On Threats to the 5G Service Based Architecture* | SBA |
| **P4** | *5G core network control plane: Network security challenges and solution requirements* | 5G Core |
| **P5** | *Security Threats, Requirements and Recommendations on Creating 5G Network Slicing System* | Network Slicing |
| **P6** | *A Survey on Network Slicing Security* | Network Slicing |
| **P7** | *NFV Security in 5G – Challenges and Best Practices* | NFV / Cloud |
| **P8** | *A Brief Survey of O-RAN Security* | O-RAN |
| **P9** | *Security of 5G-V2X: Technologies, Standardization and Research Directions* | V2X |

---

## 설명

- **P1**은 2025년 *Computer Networks*에 발표된 survey로, UE/RAN/Core 공격을 체계적으로 분석한다.
  각 공격에 대해 Attack / Cause / Impact / Defense / 3GPP 해결 여부 / 실제 구현 여부까지 검토하므로,
  대부분의 UE·RAN·Core 이슈에서 기본 논문으로 인용한다.
- **P3/P4**는 SBA·5G Core control plane 공격(NF 위장, NRF, API, HTTP/2 등)에 사용.
- **P5/P6**은 Network Slicing 격리·lifecycle 공격에 사용.
- **P7**은 NFV/Cloud/Container 및 Supply Chain 관련 이슈에 사용.
- **P8**은 O-RAN(RIC, xApp, E2/A1, AI/ML) 이슈에 사용.
- **P9**는 V2X(메시지 위조, Sybil, replay) 이슈에 사용.

---

## 공식 접근 경로

- Google Scholar: `https://scholar.google.com` — 검색어 예: `"False Base Station" "5G"`, 논문 제목 직접 검색
- 논문마다 DOI/게재지가 다르므로, 확정된 서지정보(저자, 게재지, 연도, DOI)는 실제 원문 확인 후 각 이슈 문서 또는 이 표에 보강한다.

> 주의: 위 서지정보는 마스터 데이터(`subject/5G_Security.md`) 기준이다.
> 저자·DOI 등 상세 서지는 원문 확인 전까지 임의로 채우지 않는다 (환각 금지).
