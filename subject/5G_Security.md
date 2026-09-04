오늘 오후 12:31  
\[1\] 3rd Generation Partnership Project. Study on 5g security enhancements against false base stations (fbs). Technical Report 33.809, 3GPP, 05 2023\. Version 18.1.0. \[2\] 3rd Generation Partnership Project. 5g; architecture enhancements for 5g system (5gs) to support vehicle-to-everything (v2x) services. Technical Report 23.287, 3GPP, 05 2024\. Version 18.3.0. \[3\] 3rd Generation Partnership Project. 5g; nr; medium access control (mac) protocol specification. Technical Report 38.321, 3GPP, 08 2024\. Version 18.2.0. \[4\] 3rd Generation Partnership Project. 5g; nr; multiplexing and channel coding. Technical Report 38.212, 3GPP, 08 2024\. Version 18.3.0. 16 \[5\] 3rd Generation Partnership Project. 5g; nr; nr and ng-ran overall description; stage-2. Technical Report 23.287, 3GPP, 08 2024\. Version 18.2.0. \[6\] 3rd Generation Partnership Project. 5g; nr; physical channels and modulation. Technical Report 38.211, 3GPP, 08 2024\. Version 18.3.0. \[7\] 3rd Generation Partnership Project. 5g; nr; physical layer procedures for control. Technical Report 38.213, 3GPP, 08 2024\. Version 18.3.0." 이런 5g 시큐리티 이슈, 문제 모아놓은 링크 없니?

응. 있습니다. 오히려 지금 올려주신 **3GPP 문서처럼 특정 기술 하나의 보안 이슈를 파고드는 자료**보다, 먼저 **“5G에서 어떤 공격/취약점이 실제로 존재하는가”를 한꺼번에 정리한 자료**를 보는 게 훨씬 좋습니다.

특히 지금 찾으시는 목적이라면 아래 순서가 좋습니다.

### **1\. 가장 추천 — ENISA 「5G Threat Landscape」**

ENISA가 만든 자료입니다.

[ENISA 5G Threat Landscape 공식 페이지](https://www.enisa.europa.eu/publications/enisa-threat-landscape-report-for-5g-networks?utm_source=chatgpt.com)

이게 상당히 좋습니다. 5G 전체 아키텍처를 놓고

* UE  
* RAN  
* 5G Core  
* Network Slicing  
* NFV  
* SDN  
* MEC  
* Virtualization  
* Management/Orchestration  
* Supply Chain  
* Privacy  
* DoS/DDoS  
* Rogue/False Base Station  
* signaling 공격  
* 인증/키 관리

등을 **Threat → Vulnerability → Impact → Security Control** 관점으로 정리합니다. ENISA는 3GPP, ITU, ETSI, ISO, NIST, GSMA 등의 자료까지 종합했습니다.

특히 **"5G 시큐리티 문제를 많이 모아놓은 자료"**라는 관점에서는 이게 1순위입니다.

---

### **2\. 더 실무적인 자료 — ENISA 5G Security Controls Matrix**

[ENISA 5G Security Controls Matrix](https://www.enisa.europa.eu/publications/5g-security-controls-matrix?utm_source=chatgpt.com)

이건 더 재미있습니다.

단순히

> "이런 공격이 있다"

에서 끝나는 게 아니라

> **Threat → Security Control → 대응 방법**

으로 연결해 놓았습니다.

2023년에 나온 자료이고 **스프레드시트 형태의 Security Controls Matrix**입니다. 5G 보안 평가나 컨설팅 관점에서 공부하기 좋습니다.

---

### **3\. 논문 중에서는 이게 딱 맞음 — 5G SA 공격 총정리**

**A survey of existing attacks on 5G SA**

[5G SA 공격 Survey 논문](https://www.sciencedirect.com/science/article/abs/pii/S1389128625005122?utm_source=chatgpt.com)

2025년 논문이라 비교적 최신입니다.

특히 공격을

**UE / RAN / Core Network**

로 나눠서 기존 공격들을 체계적으로 정리합니다.

그리고 각각에 대해

* Attack  
* Cause  
* Impact  
* Defense  
* 3GPP에서 해결됐는지  
* 실제 네트워크에 구현됐는지

까지 검토합니다.

**지금 질문하신 목적에는 이 논문을 강력 추천합니다.**

---

### **4\. 5G NSA 보안 취약점만 따로 정리한 자료**

[Security Vulnerabilities in 5G NSA: Systematic Analysis and Attack Taxonomy](https://www.mdpi.com/2624-800X/4/1/2?utm_source=chatgpt.com)

이것도 상당히 유용합니다.

특히 **5G NSA가 5G SA보다 보안상 취약할 수 있는 이유**를 다룹니다.

즉,

> 5G라고 해서 무조건 기존 4G 공격이 없어지는 것이 아니다.

라는 관점입니다.

4G에서 존재했던 공격이 NSA 환경에서 어떻게 이어질 수 있는지를 체계적으로 분류합니다.

---

### **5\. 5G 보안 이슈 전체를 공부하기 위한 Survey**

[A Systematic Survey on 5G and 6G Security Considerations](https://www.mdpi.com/1999-5903/16/3/67?utm_source=chatgpt.com)

여기는 조금 더 넓습니다.

**5G/6G Security**

관점에서

* Authentication  
* Privacy  
* Confidentiality  
* Integrity  
* Availability  
* Network slicing  
* IoT  
* MEC  
* SDN  
* NFV  
* AI security

등을 폭넓게 다룹니다.

---

## **그리고 중요한 게 하나 있습니다.**

지금 올려주신 참고문헌을 보면

> 33.809 — False Base Station  
>  23.287 — V2X  
>  38.321 — MAC  
>  38.212 — Channel Coding  
>  38.211 — Physical Channel  
>  38.213 — Physical Layer Control

이런 식으로 **5G 기술 표준 자체를 하나씩 파고드는 방식**인데,

만약 목적이 **"5G 보안 문제/취약점 사례를 많이 공부하고 싶다"**라면 저는 오히려 다음처럼 공부하는 걸 추천합니다.

| 분야 | 찾아볼 공격/문제 |
| ----- | ----- |
| **UE** | IMSI/Identity privacy, DoS, rogue network |
| **RAN** | False Base Station, jamming, spoofing |
| **5G NAS** | Authentication, signaling attack |
| **5G Core** | SBA/API attack, NF impersonation |
| **Network Slicing** | Slice isolation, cross-slice attack |
| **NFV/Cloud** | VM/container escape, multi-tenancy |
| **SDN** | Controller attack, flow manipulation |
| **MEC** | Edge attack, data leakage |
| **O-RAN** | xApp/rApp, API, near-RT RIC 공격 |
| **V2X** | Message spoofing, Sybil, DoS |
| **Privacy** | Location tracking, identity exposure |
| **Supply Chain** | Open source, third-party software |
| **Availability** | DoS/DDoS, signaling storm |
| **Physical Layer** | Jamming, spoofing, synchronization |
| **AI/ML** | Adversarial attack, poisoning |

이렇게 **공격 유형별로 모아놓고 → 관련 3GPP 표준을 찾아가는 방식**이 훨씬 효율적입니다.

그리고 최근에는 **2025년 5G SA 공격 Survey**가 나와 있기 때문에, 이 논문의 attack taxonomy를 뼈대로 잡고 각 공격마다 **관련 3GPP TS/TR 번호를 연결하는 방식**으로 공부하면 상당히 좋은 자료가 됩니다.

원하시면 제가 다음 단계로 \*\*"5G Security 문제/공격 사례 50\~100개"를 UE/RAN/Core/SBA/Network Slicing/NFV/O-RAN/V2X 등으로 분류해서, 각각에 대응하는 3GPP TS/TR 번호와 논문 링크까지 붙인 표\*\*를 만들어드릴 수 있습니다. 이게 아마 지금 찾으시는 것에 가장 가까울 겁니다.

네. **ENISA 사이트는 누구나 공개적으로 접근해서 자료를 읽을 수 있고**, 더 중요한 것은 ENISA가 공개 자료의 **재사용(reproduction)을 원칙적으로 허용**하고 있다는 점입니다. 다만 **“아무 내용이나 그대로 복사해서 내 사이트에 넣어도 된다”는 뜻은 아닙니다.**

제가 방금 ENISA의 저작권 정책을 다시 확인해봤는데, 꽤 명확합니다.

### **핵심은 이겁니다**

ENISA 공식 Legal Notice에는:

> **“Reproduction of ENISA material published on this website is authorized, provided the source is acknowledged”**

라고 되어 있습니다. 즉, **출처를 표시하면 ENISA 자료의 복제가 허용되는 것이 원칙**입니다. 다만 해당 자료에 별도의 제한이 표시되어 있으면 그 제한이 우선합니다.

그리고 실제 ENISA의 「5G Cybersecurity Standards」 PDF에는 아예 **CC BY 4.0**이라고 명시되어 있습니다. 이 라이선스에서는 **재사용 및 수정이 가능하고, 적절한 출처표시와 변경사항 표시가 필요**합니다.

---

## **그러면 질문하신 방식은?**

예를 들어 본인이 **5G Security 관련 사이트**를 만든다고 해보죠.

ENISA 자료에서:

> 5G Network Slicing  
>  Threat A  
>  Threat B  
>  Threat C

등을 보고,

본인 사이트에서

**「5G Network Slicing 보안 위협」**

이라는 페이지를 만들어

* ENISA가 설명한 위협  
* 본인의 한국어 해석  
* 본인의 추가 설명  
* 관련 3GPP TS/TR  
* 실제 공격 시나리오  
* 논문  
* 대응방법  
* 그림/도표

등을 정리하는 것은 **충분히 가능한 방향**입니다.

오히려 **단순 복사보다 이렇게 "재구성 \+ 해설"하는 것이 훨씬 좋습니다.**

### **예를 들면**

**원자료**

ENISA  
 *Threat Landscape for 5G Networks*

↓

**본인 사이트**

> ### **5G Network Slicing 공격 유형**

> Network Slicing은 하나의 물리적 네트워크를 여러 개의 논리적 네트워크로 분리하는 기술이다.

> **① Slice Isolation Failure**

> 공격자가 하나의 Slice에서 다른 Slice의 자원이나 데이터에 접근할 수 있는 경우 발생한다.

> **② Cross-Slice DoS**

> 특정 Slice에 자원 요청을 집중시켜 다른 Slice의 자원까지 고갈시키는 공격이다.

> **관련 표준**

> * 3GPP TS 23.501  
> * 3GPP TS 28.530  
> * 3GPP TS 33.501

> **참고**

> * ENISA, *Threat Landscape for 5G Networks*, 2020  
> * 관련 논문 ○○○

이런 형태라면 **교육/기술 해설 사이트로 상당히 좋은 콘텐츠**가 될 수 있습니다.

---

## **다만 꼭 지켜야 할 것 4가지**

### **① 출처를 명확하게 표시**

예를 들어:

> **Source:** ENISA, *ENISA Threat Landscape for 5G Networks*, 2020\.  
>  [https://www.enisa.europa.eu/](https://www.enisa.europa.eu/?utm_source=chatgpt.com)...

처럼 표시하는 게 좋습니다.

ENISA도 재사용 시 **source acknowledgement**를 요구합니다.

---

### **② ENISA 자료와 본인의 설명을 구분**

이게 상당히 중요합니다.

예를 들어:

> **ENISA 원자료 요약**

> ...

> **작성자 해설**

> 여기서 실제 5G SA 환경에서는 ...

이렇게 구분하면 훨씬 안전하고 전문적으로 보입니다.

특히 **본인이 추가한 분석을 ENISA의 공식 입장처럼 보이게 하면 안 됩니다.**

---

### **③ ENISA 로고는 별도 주의**

텍스트나 보고서 내용을 재사용할 수 있다고 해서 **ENISA 로고를 마음대로 사이트에 붙여도 된다는 의미는 아닙니다.**

ENISA는 로고 사용에 별도 조건을 두고 있고, 상업적 이용이나 ENISA와 공식적인 관계가 있는 것처럼 보이는 사용은 제한합니다.

그래서 저는 **처음에는 로고를 사용하지 않는 것**을 권합니다.

그냥

> **Source: European Union Agency for Cybersecurity (ENISA)**

정도로 표시하는 것이 깔끔합니다.

---

### **④ ENISA 자료 안의 제3자 자료는 별도 확인**

이것도 중요합니다.

ENISA 자체 자료는 재사용 정책이 있지만, ENISA 문서 안에 **다른 기관/저작권자의 사진, 그림, 제3자 자료**가 들어 있을 수 있습니다.

ENISA도 명확하게:

> ENISA copyright가 아닌 사진이나 기타 자료는 해당 저작권자로부터 허락을 받아야 한다.

고 안내합니다.

따라서 **ENISA PDF를 통째로 가져와서 그림까지 그대로 복사하는 것보다는**, 핵심 내용을 참고해서 **본인이 직접 그림/표를 새로 만드는 방식**이 가장 좋습니다.

---

# **오히려 제가 추천하는 방식**

지금까지 이야기한 걸 보면, 단순한 블로그가 아니라 **5G Security 지식 사이트**를 만들려고 하는 거라면 상당히 좋은 소재입니다.

예를 들어 이런 구조입니다.

5G Security

├── 01\. 5G Security Architecture  
│  
├── 02\. UE Security  
│    ├── SUPI / SUCI  
│    ├── False Base Station  
│    ├── Authentication  
│    └── NAS Security  
│  
├── 03\. RAN Security  
│    ├── Jamming  
│    ├── RACH Attack  
│    ├── RRC Attack  
│    └── gNB Security  
│  
├── 04\. 5G Core Security  
│    ├── AMF  
│    ├── SMF  
│    ├── UPF  
│    ├── UDM  
│    └── AUSF  
│  
├── 05\. SBA Security  
│    ├── NRF Attack  
│    ├── NF Impersonation  
│    ├── API Attack  
│    └── HTTP/2 Attack  
│  
├── 06\. Network Slicing Security  
│  
├── 07\. NFV / Cloud Security  
│  
├── 08\. MEC Security  
│  
├── 09\. O-RAN Security  
│  
├── 10\. V2X Security  
│  
└── 11\. 5G Security Standards  
     ├── 3GPP TS 33.501  
     ├── TR 33.809  
     ├── TS 24.501  
     ├── TS 38.331  
     └── ...

그리고 **각 공격 페이지를 똑같은 템플릿으로 만드는 겁니다.**

> **Attack Name**  
>  ↓  
>  **Attack Scenario**  
>  ↓  
>  **Affected Component**  
>  ↓  
>  **Vulnerability**  
>  ↓  
>  **Attack Procedure**  
>  ↓  
>  **Impact**  
>  ↓  
>  **3GPP Specification**  
>  ↓  
>  **Security Control**  
>  ↓  
>  **Research Papers**  
>  ↓  
>  **ENISA Reference**  
>  ↓  
>  **작성자 해설**

이렇게 만들면 단순히 ENISA를 번역한 사이트가 아니라 **ENISA \+ 3GPP \+ 논문을 연결해주는 5G Security 기술 데이터베이스**가 됩니다.

그리고 ENISA의 5G Threat Landscape 자체가 **5G architecture → asset → threat taxonomy → asset exposure → threat agent** 구조로 만들어져 있기 때문에, 이런 사이트의 기본 분류 체계를 잡는 데 상당히 좋은 출발점입니다.

**결론적으로:**  
 👉 **가능합니다.**  
 👉 ENISA 자료는 공개되어 있고 재사용도 원칙적으로 허용됩니다.  
 👉 다만 **출처표시 \+ 변경/해설 여부 표시 \+ 제3자 자료 확인 \+ ENISA 공식 사이트처럼 보이게 하지 않기**가 중요합니다.

그리고 이걸 실제로 사이트로 만들 생각이라면, \*\*제가 ENISA 5G Threat Landscape를 기준으로 “사이트에 그대로 넣을 수 있는 5G Security 콘텐츠 50개”를 저작권 문제를 피하도록 `원문 복사 없이 → 한국어 해설 + 3GPP 표준 + 논문 + 공격 시나리오` 형태로 재작성\*\*해드릴 수도 있습니다. 그 방식이 가장 깔끔합니다.

이런거 왜 유럽만 있니? 미국은 없니?

있습니다. **오히려 미국 쪽에도 상당히 좋은 자료가 있고, 2026년 현재는 NIST가 아주 적극적으로 만들고 있습니다.**  
 제가 앞에서 ENISA를 먼저 소개한 건 “5G 위협을 한꺼번에 정리한 자료”라는 측면에서 설명했기 때문이고, **미국 자료까지 포함하면 NIST \+ CISA/NSA 쪽을 반드시 같이 보는 게 좋습니다.**

특히 지금 하시려는 **5G Security 사이트를 만든다는 목적**이라면 저는 **ENISA \+ NIST \+ CISA/NSA \+ 3GPP**를 4개 축으로 잡겠습니다.

## **🇺🇸 1\. NIST — 미국에서는 여기가 가장 중요합니다**

NIST 5G Cybersecurity 프로젝트

NIST의 NCCoE가 실제 **5G 네트워크 테스트베드**를 구축해서 5G 보안 기능을 시험하고 있습니다. 단순히 "이론적으로 이런 위협이 있다" 수준이 아니라 **실제 5G 장비/구성에서 보안 기능을 어떻게 구현하고 검증하는지**를 다룹니다.

그리고 **2026년 3월에 아주 중요한 자료들이 정식으로 나왔습니다.**

### **NIST CSWP 36 시리즈**

[NIST CSWP 36 — Applying 5G Cybersecurity and Privacy Capabilities](https://csrc.nist.gov/news/2026/nist-releases-cswp-36-final-volumes-a-e?utm_source=chatgpt.com)

현재 다음과 같은 세부 자료가 있습니다.

| NIST 자료 | 다루는 문제 |
| ----- | ----- |
| **36A** | 5G Cybersecurity 전체 개요 |
| **36B** | Hardware Root of Trust / 플랫폼 무결성 |
| **36C** | Temporary Identity 재할당 |
| **36D** | No-SUPI-based Paging |
| **36E** | 5G Network Security Design Principles |
| **36F** | Initial NAS Message Security |

특히 **36C**는 SUPI/SUCI/GUTI와 가입자 위치추적 문제를 다룹니다.

**36D**는 paging 과정에서 SUPI가 노출되지 않도록 하는 보안 문제를 다룹니다.

그리고 아주 재미있는 게 **36F**입니다.

### **🔥 NIST CSWP 36F — Initial NAS Message Security**

[NIST CSWP 36F – Initial NAS Message Security](https://csrc.nist.gov/pubs/cswp/36/f/initial-nas-message-security-applying-5g-cybersecu/ipd?utm_source=chatgpt.com)

이 자료는 **2026년 8월 6일** 공개된 최신 draft입니다.

NIST가 설명하는 핵심은:

**4G**

Initial NAS Message  
 → 암호화/무결성 보호가 없는 민감 정보가 존재  
 → MITM 공격 가능

↓

**5G**

Initial NAS Message의 민감한 내용을  
 → **암호화 \+ Integrity Protection**

으로 보호할 수 있다는 것입니다.

이런 식의 자료가 바로 **당신이 만들려고 하는 사이트에 굉장히 좋은 소재**입니다.

---

# **🇺🇸 2\. CISA — 공격/위협 관점에서는 여기가 좋습니다**

[CISA 5G Security and Resilience Library](https://www.cisa.gov/5g-library?utm_source=chatgpt.com)

CISA에는 아예 **5G Library**가 있습니다.

여기에는 다음과 같은 자료가 들어 있습니다.

### **① Potential Threat Vectors to 5G Infrastructure**

5G 인프라를 여러 영역으로 나눠서 **어떤 위협 벡터가 존재하는지** 정리합니다.

### **② 5G Network Slicing**

특히

> **5G Network Slicing: Security Considerations for Design, Deployment, and Maintenance**

라는 자료가 있습니다.

즉, 우리가 앞에서 이야기했던 **Network Slicing 공격/보안 문제**를 미국 정부기관 관점에서 볼 수 있습니다.

### **③ 5G Cloud Security**

CISA에는 상당히 좋은 시리즈도 있습니다.

* Part I — Prevent and Detect Lateral Movement  
* Part II — Securely Isolate Network Resources  
* Part III — Data Protection  
* Part IV — Ensure Integrity of Cloud Infrastructure

입니다.

이건 **5G Core \+ NFV \+ Container \+ Cloud**를 공부할 때 상당히 유용합니다.

---

# **🇺🇸 3\. NSA \+ CISA — 이것도 상당히 중요**

특히 **5G Network Slicing**이나 **Cloud infrastructure** 같은 분야에서는 CISA와 NSA의 공동 Enduring Security Framework 자료가 좋습니다.

미국 쪽 특징은 ENISA와 조금 다릅니다.

### **ENISA**

**Threat Landscape**

> "5G에는 이런 위협들이 있다."

라는 관점이 강합니다.

### **NIST**

**Security Capability / Implementation**

> "이 보안 기능을 실제 5G 환경에서 어떻게 구현하고 검증할 것인가?"

에 가깝습니다.

### **CISA/NSA**

**National Security / Threat / Risk**

> "실제 운영 환경에서 어떤 공격 벡터가 문제가 되고 어떻게 위험을 줄일 것인가?"

에 가깝습니다.

그래서 셋을 같이 보면 굉장히 좋습니다.

---

# **그리고 재미있는 게 하나 있습니다.**

지금 만들려고 하는 사이트라면 **ENISA 하나만 가지고 만드는 것보다 미국 자료까지 합치는 게 훨씬 가치가 있습니다.**

예를 들어 사이트에서

## **False Base Station**

이라고 하면,

**ENISA**

→ Threat Landscape  
 → Rogue/False Base Station

↓

**3GPP**

→ TR 33.809  
 → TS 33.501

↓

**NIST**

→ Subscriber Identity Protection  
 → SUPI/SUCI/GUTI  
 → Temporary Identity Reallocation

↓

**논문**

→ False Base Station / IMSI Catcher / 5G Privacy Attack

↓

**내 사이트**

> **왜 5G에서 False Base Station 공격이 가능한가?**  
>  **4G와 무엇이 달라졌나?**  
>  **SUCI가 어떤 문제를 해결하는가?**  
>  **그런데 왜 여전히 공격 가능성이 남아 있는가?**  
>  **3GPP는 어떤 보안 절차를 정의했나?**  
>  **NIST는 실제 장비에서 어떻게 검증했나?**

이렇게 연결하는 겁니다.

---

# **저는 오히려 이 구조를 추천합니다**

                5G SECURITY  
                      │  
       ┌──────────────┼──────────────┐  
       ↓              ↓              ↓  
     THREAT         STANDARD       DEFENSE  
       │              │              │  
     ENISA          3GPP            NIST  
       │              │              │  
       └──────────────┼──────────────┘  
                      ↓  
                 US GOVERNMENT  
                      │  
                  CISA / NSA  
                      │  
                      ↓  
                  RESEARCH  
                      │  
                   Papers  
                      │  
                      ↓  
                YOUR EXPLANATION

이렇게 하면 **그냥 ENISA 번역 사이트가 아닙니다.**

**ENISA가 어떤 위협이라고 했는지 → 3GPP에서 어떤 프로토콜/보안기능으로 대응하는지 → NIST가 실제 환경에서 어떻게 구현·검증하는지 → CISA/NSA는 어떤 위험으로 보는지 → 관련 논문은 실제 공격을 어떻게 보여주는지**

를 한 페이지에서 연결해주는 겁니다.

### **그리고 이건 꽤 중요한 차이입니다.**

**ENISA \= 유럽 관점**  
 **NIST \= 미국의 기술/실무 관점**  
 **CISA/NSA \= 미국의 위협·국가안보 관점**  
 **3GPP \= 국제 이동통신 표준 관점**

이 4개를 연결하면 **5G Security 전문 사이트의 콘텐츠 소스가 상당히 풍부해집니다.**

특히 **2026년 3월 NIST가 5G 보안 백서를 대거 최종 발행했고, 2026년 8월에는 Initial NAS Message Security까지 새로 공개했기 때문에**, 지금 시작한다면 시점도 좋습니다.

원하시면 다음에는 제가 \*\*ENISA \+ NIST \+ CISA/NSA \+ 3GPP를 합쳐서 "5G Security 이슈 100개"를 만들고, 각 이슈마다 `미국자료 / 유럽자료 / 3GPP / 논문 / 사이트에 쓸 수 있는 한국어 설명`까지 연결한 콘텐츠 목록\*\*으로 만들어드릴게요. 이게 실제 사이트 구축용으로는 훨씬 유용합니다.

광고

이 광고에 관심이 있으신가요?

Create a list of 100 5G Security issues combining ENISA, NIST, CISA/NSA, and 3GPP with related US, Europe, 3GPP, papers, and Korean explanations for site use

네. 이번에는 **실제로 사이트 콘텐츠로 옮겨 쓸 수 있는 형태**로 잡아보겠습니다.

아래 목록은 **ENISA \+ NIST \+ CISA/NSA \+ 3GPP \+ 연구논문**을 하나의 프레임으로 묶은 **100개 5G Security Issue Database 초안**입니다.

중요한 점은 **ENISA/NIST/CISA가 각각 100개를 똑같이 정의했다는 뜻이 아니라**, 각 기관의 위협·보안통제 자료와 3GPP 표준, 연구문헌을 교차해서 **사이트의 100개 콘텐츠 주제**로 재구성한 것입니다.

특히 NIST는 2026년 3월 CSWP 36 시리즈를 최종 발행했고, 2026년 8월에는 **Initial NAS Message Security(36F)**까지 공개했습니다. 따라서 아래 목록에는 최신 NIST 내용도 반영했습니다.

---

# **1\. 먼저 사이트에서 사용할 출처 코드**

## **🇪🇺 Europe**

**EU-1 — ENISA 5G Threat Landscape**

[ENISA 5G Threat Landscape](https://www.enisa.europa.eu/publications/enisa-threat-landscape-report-for-5g-networks?utm_source=chatgpt.com)

5G 자산, 위협, 취약점, 공격 가능성 및 보안통제를 종합한 기본 자료입니다. ENISA는 3GPP, ITU, ETSI, ISO, NIST, GSMA 등의 자료도 종합했습니다.

**EU-2 — ENISA 5G Security Controls Matrix**

[ENISA 5G Security Controls Matrix](https://www.enisa.europa.eu/publications/5g-security-controls-matrix?utm_source=chatgpt.com)

특히 사이트 구축에는 매우 좋습니다. **399개 detailed security controls, 110개 asset types, 2개 5G architecture, 3개 cloud deployment model**을 포함합니다.

**EU-3 — ENISA Security in 5G Specifications**

[ENISA Security in 5G Specifications](https://www.enisa.europa.eu/publications/security-in-5g-specifications?utm_source=chatgpt.com)

3GPP 보안 규격과 주요 security control을 이해하기 위한 자료입니다.

---

## **🇺🇸 United States**

**US-1 — NIST CSWP 36**

[NIST CSWP 36 5G Cybersecurity Series](https://csrc.nist.gov/pubs/cswp/36/applying-5g-cybersecurity-and-privacy-capabilities/final?utm_source=chatgpt.com)

2026년 NIST의 최신 5G 보안 시리즈입니다. 실제 NCCoE 5G testbed에서 보안기능을 구현·시험했다는 점이 특히 중요합니다.

**US-2 — NIST 36A: SUCI**

[NIST CSWP 36A — SUCI](https://csrc.nist.gov/pubs/cswp/36/a/protecting-subscriber-identifiers-with-suci-applyi/final?utm_source=chatgpt.com)

**US-3 — NIST 36B: Hardware Root of Trust**

[NIST CSWP 36B](https://csrc.nist.gov/pubs/cswp/36/b/using-hardware-enabled-security-to-ensure-5g-syste/final?utm_source=chatgpt.com)

**US-4 — NIST 36C: Temporary Identity**

[NIST CSWP 36C](https://csrc.nist.gov/pubs/cswp/36/c/reallocation-of-temporary-identities-applying-5g-c/final?utm_source=chatgpt.com)

**US-5 — NIST 36D: No-SUPI Paging**

[NIST CSWP 36D](https://csrc.nist.gov/pubs/cswp/36/d/no-supi-based-paging-applying-5g-cybersecurity-and/final?utm_source=chatgpt.com)

**US-6 — NIST 36E: Network Security Design**

[NIST CSWP 36E](https://csrc.nist.gov/pubs/cswp/36/e/5g-network-security-design-principles/final?utm_source=chatgpt.com)

**US-7 — NIST 36F: Initial NAS Security**

[NIST CSWP 36F](https://csrc.nist.gov/pubs/cswp/36/f/initial-nas-message-security-applying-5g-cybersecu/ipd?utm_source=chatgpt.com)

36F는 **2026-08-06 공개된 Initial Public Draft**입니다.

---

## **🇺🇸 CISA / NSA**

**US-8 — CISA 5G Library**

[CISA 5G Security and Resilience Library](https://www.cisa.gov/5g-library?utm_source=chatgpt.com)

여기에 CISA/NSA의 **5G Network Slicing, Potential Threat Vectors, 5G Cloud Infrastructure** 등의 자료가 모여 있습니다.

특히 CISA/NSA는 Network Slicing을 별도의 위협영역으로 보고 **Design / Deployment / Maintenance** 관점의 보안지침까지 발표했습니다.

---

# **2\. 주요 논문/연구자료 코드**

사이트에서는 논문을 매번 새로 찾기보다 아래처럼 공통 Reference ID를 부여하는 게 좋습니다.

| 코드 | 연구자료 | 주로 사용하는 영역 |
| ----- | ----- | ----- |
| **P1** | *A survey of existing attacks on 5G SA*, Computer Networks, 2025 | UE/RAN/Core |
| **P2** | *Towards secure 5G networks: A Survey* | 5G 전체 |
| **P3** | *On Threats to the 5G Service Based Architecture* | SBA |
| **P4** | *5G core network control plane: Network security challenges and solution requirements* | 5GC |
| **P5** | *Security Threats, Requirements and Recommendations on Creating 5G Network Slicing System* | Slicing |
| **P6** | *A Survey on Network Slicing Security* | Slicing |
| **P7** | *NFV Security in 5G – Challenges and Best Practices* | NFV/Cloud |
| **P8** | *A Brief Survey of O-RAN Security* | O-RAN |
| **P9** | *Security of 5G-V2X: Technologies, Standardization and Research Directions* | V2X |

특히 **P1은 2025년 10월 Computer Networks에 발표된 survey**로 UE/RAN/Core 공격을 체계적으로 분석하기 때문에 기본 논문으로 쓰기 좋습니다.

---

# **3\. 100개 5G Security Issue Database**

## **A. UE / Subscriber / Privacy — 1\~15**

| \# | Security Issue | 관련 US | 관련 EU | 3GPP | 논문 | 사이트용 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 1 | SUPI Exposure | US-2 | EU-1 | TS 33.501 | P1,P2 | 가입자의 영구 식별자인 SUPI가 공격자에게 노출되는 문제 |
| 2 | IMSI/SUPI Catching | US-2 | EU-1 | TR 33.809, TS 33.501 | P1 | 가짜 기지국 등을 이용해 가입자 식별자를 수집하는 공격 |
| 3 | SUCI Null Scheme | US-2 | EU-3 | TS 33.501 | P1 | SUCI를 사용하더라도 null protection을 사용하면 식별정보 보호 효과가 제한되는 문제 |
| 4 | SUCI Misconfiguration | US-2 | EU-2 | TS 33.501 | P1 | SUCI 보안 설정 오류로 가입자 privacy가 약화되는 문제 |
| 5 | False Base Station | US-2 | EU-1 | TR 33.809 | P1 | 공격자가 정상 gNB처럼 위장해 UE를 유인하는 공격 |
| 6 | Rogue gNB | US-2 | EU-1 | TR 33.809, TS 33.501 | P1 | 악성 gNB를 이용한 가입자 및 signaling 공격 |
| 7 | Temporary Identity Tracking | US-4 | EU-1 | TS 33.501 | P1 | 임시 식별자의 장기간 사용을 이용한 사용자 추적 |
| 8 | GUTI Reallocation Failure | US-4 | EU-2 | TS 33.501 | P1 | 임시 ID를 적절히 갱신하지 않아 위치·신원 추적이 가능해지는 문제 |
| 9 | SUPI-based Paging | US-5 | EU-1 | TS 24.501, 23.502 | P1 | Paging에서 SUPI가 사용될 경우 가입자 위치정보가 노출될 수 있는 문제 |
| 10 | Paging Privacy Leakage | US-5 | EU-1 | TS 23.502 | P1 | Paging 패턴을 이용한 특정 가입자의 존재·위치 추적 |
| 11 | Initial NAS Information Exposure | US-7 | EU-3 | TS 24.501, TS 33.501 | P1 | Initial NAS Message에 민감정보가 노출될 수 있는 문제 |
| 12 | NAS Message Tampering | US-7 | EU-3 | TS 24.501, 33.501 | P1 | NAS signaling이 변조되는 공격 |
| 13 | NAS Replay | US-7 | EU-1 | TS 33.501 | P1 | 과거 NAS 메시지를 재전송해 정상 절차를 혼란시키는 공격 |
| 14 | UE Identity Tracking | US-4,5 | EU-1 | TS 33.501 | P1,P2 | 여러 무선 이벤트를 결합해 사용자를 지속적으로 추적하는 공격 |
| 15 | UE Privacy Configuration Error | US-2,4,5 | EU-2 | TS 33.501 | P1 | 표준에 있는 privacy 기능을 운영자가 제대로 활성화하지 않아 발생하는 문제 |

NIST가 특히 강조하는 것이 **SUCI, temporary identity, no-SUPI paging**입니다. 즉 이 세 가지를 별도 페이지로 만들어도 좋습니다.

---

# **B. Authentication / NAS / UE Control — 16\~25**

| \# | Security Issue | US | EU | 3GPP | Paper | 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 16 | 5G-AKA Attack Surface | US-1 | EU-3 | TS 33.501 | P1,P2 | 5G AKA 인증절차를 대상으로 하는 공격면 |
| 17 | EAP-AKA' Attack | US-1 | EU-3 | TS 33.501 | P1 | EAP 기반 인증 절차의 오용 또는 구현 취약점 |
| 18 | Authentication DoS | US-1 | EU-1 | TS 33.501 | P1,P4 | 인증 요청을 대량 발생시켜 네트워크 자원을 고갈시키는 공격 |
| 19 | Authentication Relay | US-1 | EU-1 | TS 33.501 | P1 | 정상 인증 메시지를 중계해 인증 절차를 우회하려는 공격 |
| 20 | Authentication Context Exposure | US-1 | EU-3 | TS 33.501 | P1 | 인증 관련 context가 잘못 관리되어 노출되는 문제 |
| 21 | Security Context Desynchronization | US-1 | EU-3 | TS 33.501 | P1 | UE와 네트워크의 보안 context가 서로 달라지는 문제 |
| 22 | NAS Security Downgrade | US-7 | EU-1 | TS 33.501 | P1 | 강력한 NAS 보안 대신 약한 보안 상태로 유도하는 공격 |
| 23 | Registration Request Flooding | US-8 | EU-1 | TS 24.501 | P1 | Registration 요청을 폭주시켜 AMF 자원을 소모시키는 공격 |
| 24 | Deregistration Abuse | US-1 | EU-1 | TS 24.501 | P1 | Deregistration 절차를 악용해 UE 서비스를 방해 |
| 25 | Service Request Abuse | US-1 | EU-1 | TS 24.501 | P1 | Service Request를 반복 발생시켜 signaling/resource를 소모 |

---

# **C. RAN / Radio Interface — 26\~40**

| \# | Security Issue | US | EU | 3GPP | Paper | 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 26 | RF Jamming | US-8 | EU-1 | TS 38.211 | P1,P2 | 무선 주파수를 방해해 통신 자체를 마비 |
| 27 | PDCCH Jamming | US-8 | EU-1 | TS 38.211, 38.213 | P1 | 제어채널을 집중적으로 방해 |
| 28 | PDSCH Jamming | US-8 | EU-1 | TS 38.211 | P1 | DL 데이터 전송을 방해 |
| 29 | PUSCH Jamming | US-8 | EU-1 | TS 38.211 | P1 | UL 데이터 전송을 방해 |
| 30 | PRACH Attack | US-8 | EU-1 | TS 38.211, 38.321 | P1 | Random Access 절차를 공격 |
| 31 | RACH Flooding | US-8 | EU-1 | TS 38.321 | P1 | RACH 요청을 폭주시켜 무선 자원을 고갈 |
| 32 | RRC Manipulation | US-1 | EU-1 | TS 38.331 | P1 | RRC 메시지를 악용한 제어 공격 |
| 33 | RRC Release Attack | US-1 | EU-1 | TS 38.331 | P1 | RRC 연결을 반복적으로 끊어 서비스 방해 |
| 34 | RRC Reconfiguration Abuse | US-1 | EU-1 | TS 38.331 | P1 | RRC 재구성 절차를 악용 |
| 35 | MAC CE Abuse | US-1 | EU-3 | TS 38.321 | P1 | MAC Control Element를 이용한 protocol abuse |
| 36 | HARQ Manipulation | US-8 | EU-1 | TS 38.321, 38.213 | P1 | HARQ 동작을 방해하여 통신 성능 저하 |
| 37 | Timing Attack | US-8 | EU-1 | TS 38.211, 38.213 | P1 | 시간 동기 관련 정보를 공격 |
| 38 | Synchronization Signal Attack | US-8 | EU-1 | TS 38.211 | P1 | synchronization signal을 이용한 공격 |
| 39 | Physical-layer Spoofing | US-8 | EU-1 | TS 38.211 | P1,P2 | 정상 무선 신호처럼 위조 |
| 40 | Radio Resource Exhaustion | US-8 | EU-1 | TS 38.300 series | P1 | 무선 자원을 고갈시키는 DoS |

---

# **D. gNB / NG-RAN Interfaces — 41\~50**

| \# | Security Issue | US | EU | 3GPP | Paper | 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 41 | gNB Impersonation | US-8 | EU-1 | TS 38.401 | P1 | 공격자가 정상 gNB로 위장 |
| 42 | NGAP Flooding | US-8 | EU-1 | TS 38.413 | P1,P4 | gNB-AMF 간 NGAP signaling 폭주 |
| 43 | NGAP Manipulation | US-1 | EU-3 | TS 38.413 | P1 | NGAP 메시지 변조 |
| 44 | XnAP Attack | US-8 | EU-1 | TS 38.423 | P1 | gNB 간 Xn signaling 공격 |
| 45 | Xn Interface DoS | US-8 | EU-1 | TS 38.423 | P1 | Xn interface 자원 고갈 |
| 46 | F1-C Attack | US-6 | EU-2 | TS 38.473 | P1 | CU-DU control interface 공격 |
| 47 | F1-U Attack | US-6 | EU-2 | TS 38.475 | P1 | CU-DU user-plane interface 공격 |
| 48 | E1 Attack | US-6 | EU-2 | TS 38.463 | P1 | CU-CP와 CU-UP 사이 interface 공격 |
| 49 | RAN Configuration Tampering | US-6 | EU-2 | TS 38.401 | P1 | gNB 설정값을 불법 변경 |
| 50 | RAN Signaling Storm | US-6 | EU-1 | TS 38.401 | P1 | 대량 signaling으로 RAN 자원을 고갈 |

---

# **E. 5G Core — 51\~60**

| \# | Security Issue | US | EU | 3GPP | Paper | 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 51 | AMF DoS | US-6 | EU-1 | TS 23.501, 23.502 | P1,P4 | AMF에 요청을 집중시켜 핵심 control-plane 마비 |
| 52 | SMF DoS | US-6 | EU-1 | TS 23.502 | P1,P4 | PDU Session 요청을 이용한 SMF 공격 |
| 53 | UPF DoS | US-6 | EU-1 | TS 23.501 | P1 | User-plane 자원 고갈 |
| 54 | UDM Data Exposure | US-6 | EU-2 | TS 29.503 | P4 | 가입자 데이터가 UDM에서 노출 |
| 55 | UDR Data Exposure | US-6 | EU-2 | TS 29.504 | P4 | 가입자 데이터 저장소 공격 |
| 56 | AUSF Attack | US-1 | EU-3 | TS 29.509 | P1,P4 | 인증 서버를 대상으로 한 공격 |
| 57 | PCF Manipulation | US-6 | EU-2 | TS 29.507 | P4 | 정책을 조작하여 가입자 서비스 변경 |
| 58 | NRF Attack | US-6 | EU-2 | TS 29.510 | P3,P4 | Network Function Repository 공격 |
| 59 | GTP-U Spoofing | US-8 | EU-1 | TS 29.281 | P1 | User-plane 패킷 위조 |
| 60 | PFCP Manipulation | US-8 | EU-2 | TS 29.244 | P1,P4 | SMF-UPF 사이 PFCP 제어 메시지 공격 |

---

# **F. SBA — 61\~70**

5G SBA는 **사이트의 핵심 콘텐츠 영역으로 따로 만드는 것을 추천**합니다. 5G Core가 cloud/API 기반으로 바뀌면서 기존 통신망과 다른 공격면이 생기기 때문입니다. NIST도 5G 표준 자체의 보안기능뿐 아니라 그 아래의 IT/cloud infrastructure까지 함께 고려해야 한다고 설명합니다.

| \# | Security Issue | US | EU | 3GPP | Paper | 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 61 | NF Impersonation | US-6 | EU-3 | TS 33.501 | P3 | 악성 NF가 정상 NF로 위장 |
| 62 | NF Discovery Poisoning | US-6 | EU-1 | TS 29.510 | P3 | NRF의 NF 정보를 조작 |
| 63 | NRF Compromise | US-6 | EU-2 | TS 29.510 | P3,P4 | NRF를 장악하여 NF 전체에 영향 |
| 64 | SBA API Abuse | US-6 | EU-2 | TS 29.500 | P3 | 정상 API 권한을 악용 |
| 65 | API Parameter Manipulation | US-6 | EU-2 | TS 29.501 | P3 | API 입력값을 조작 |
| 66 | OAuth Token Abuse | US-6 | EU-3 | TS 33.501 | P3 | 인증 token을 탈취하거나 악용 |
| 67 | HTTP/2 DoS | US-8 | EU-1 | TS 29.500 | P3,P4 | HTTP/2를 이용해 NF 자원 고갈 |
| 68 | HTTP/2 Stream Multiplexing Attack | US-8 | EU-1 | TS 29.500 | P3,P4 | 하나의 connection으로 다수 request를 보내 공격 |
| 69 | NF Service Flooding | US-8 | EU-1 | TS 29.500 | P3 | 특정 NF API를 대량 호출 |
| 70 | Inter-NF Trust Abuse | US-6 | EU-3 | TS 33.501 | P3,P4 | NF 간 신뢰관계를 악용 |

---

# **G. Network Slicing — 71\~80**

CISA/NSA가 별도의 **5G Network Slicing Security Considerations**를 발행할 정도로 중요한 영역입니다. CISA는 2022년 threat guidance에 이어 2023년에 **Design, Deployment, Operation/Maintenance** 관점의 보안지침을 발표했습니다.

| \# | Security Issue | US | EU | 3GPP | Paper | 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 71 | Inter-Slice Attack | US-8 | EU-1 | TS 23.501 | P5,P6 | 한 slice에서 다른 slice로 공격 확산 |
| 72 | Intra-Slice Attack | US-8 | EU-1 | TS 23.501 | P5,P6 | 동일 slice 내부의 자원/서비스 공격 |
| 73 | Slice Isolation Failure | US-8 | EU-2 | TS 23.501 | P5,P6 | slice 간 논리적 격리가 깨지는 문제 |
| 74 | Cross-Slice DoS | US-8 | EU-1 | TS 23.501 | P5,P6 | 한 slice의 공격이 다른 slice 자원까지 고갈 |
| 75 | Slice Configuration Tampering | US-8 | EU-2 | TS 28.530 | P5 | slice 설정을 불법 변경 |
| 76 | Slice Lifecycle Attack | US-8 | EU-2 | TS 28.530/531 | P5,P6 | 생성·변경·삭제 lifecycle 공격 |
| 77 | Slice Provisioning Attack | US-8 | EU-2 | TS 28.531 | P5 | slice provisioning 과정 공격 |
| 78 | Slice Tenant Isolation Failure | US-8 | EU-2 | TS 23.501 | P5,P6 | 서로 다른 tenant 간 데이터/자원 격리 실패 |
| 79 | Slice Resource Starvation | US-8 | EU-1 | TS 23.501 | P5,P6 | 특정 slice가 공유 자원을 과도하게 점유 |
| 80 | Slice Management API Attack | US-8 | EU-2 | TS 28.530 series | P5,P6 | slice 관리 API를 공격 |

---

# **H. NFV / Cloud / Container / MEC — 81\~90**

CISA의 5G Cloud Infrastructure 자료는 **lateral movement, resource isolation, data protection, cloud infrastructure integrity**를 별도 주제로 다룹니다.

| \# | Security Issue | US | EU | 3GPP | Paper | 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 81 | VM Escape | US-8 | EU-2 | TS 28.500 series | P7 | VNF VM에서 host 환경으로 탈출 |
| 82 | Container Escape | US-8 | EU-2 | TS 28.500 | P7 | CNF container에서 host로 탈출 |
| 83 | Hypervisor Attack | US-8 | EU-2 | TS 28.500 | P7 | virtualization layer를 공격 |
| 84 | Container Image Tampering | US-8 | EU-2 | TS 28.500 | P7 | 악성 container image를 배포 |
| 85 | VNF Image Tampering | US-8 | EU-2 | TS 28.500 | P7 | VNF image 변조 |
| 86 | Multi-Tenant Isolation Failure | US-8 | EU-2 | TS 23.501 | P7 | 서로 다른 고객의 자원 격리 실패 |
| 87 | Cloud Lateral Movement | US-8 | EU-2 | TS 28.500 | P7 | 하나의 cloud 자원 장악 후 다른 NF로 이동 |
| 88 | Orchestrator Compromise | US-8 | EU-2 | TS 28.500 | P7 | MANO/orchestrator 장악 |
| 89 | Cloud Configuration Tampering | US-6 | EU-2 | TS 28.500 | P7 | cloud configuration 변경 |
| 90 | Hardware/Platform Integrity Failure | US-3 | EU-2 | TS 33.501 | P7 | 서버 플랫폼 자체의 무결성을 신뢰할 수 없는 문제 |

NIST 36B는 바로 이 **platform integrity** 문제를 Hardware Root of Trust와 remote attestation으로 대응하는 방법을 실제 5G testbed에서 다룹니다.

---

# **I. O-RAN / Open RAN — 91\~95**

O-RAN은 3GPP와 별도로 O-RAN Alliance가 규격화하는 영역이므로 **3GPP 번호만으로 설명하면 안 됩니다.** 사이트에서는 `3GPP + O-RAN WG11`을 함께 표시하는 방식이 좋습니다.

| \# | Security Issue | US | EU | 3GPP / O-RAN | Paper | 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 91 | Near-RT RIC Compromise | US-6 | EU-1 | 38.401 \+ O-RAN WG11 | P8 | Near-RT RIC을 장악해 RAN 제어에 개입 |
| 92 | Malicious xApp | US-6 | EU-1 | O-RAN WG2/WG11 | P8 | 악성 xApp을 RIC에 설치 |
| 93 | E2 Interface Attack | US-6 | EU-1 | 38.401 \+ O-RAN E2/WG11 | P8 | RIC과 E2 Node 사이의 공격 |
| 94 | A1 Interface Attack | US-6 | EU-1 | O-RAN A1/WG11 | P8 | Non-RT RIC과 Near-RT RIC 사이 공격 |
| 95 | AI/ML Model Poisoning | US-6 | EU-1 | O-RAN WG11 | P8 | RAN 최적화에 사용되는 ML 모델을 오염 |

---

# **J. V2X / Operational / Supply Chain — 96\~100**

| \# | Security Issue | US | EU | 3GPP | Paper | 사이트용 한국어 설명 |
| ----- | ----- | ----- | ----- | ----- | ----- | ----- |
| 96 | V2X Message Spoofing | US-8 | EU-1 | TS 23.287, 33.536 | P9 | 차량 메시지를 위조하여 다른 차량을 속이는 공격 |
| 97 | V2X Sybil Attack | US-8 | EU-1 | TS 33.536 | P9 | 하나의 공격자가 여러 차량 identity를 만들어내는 공격 |
| 98 | V2X Replay Attack | US-8 | EU-1 | TS 33.536 | P9 | 과거 차량 메시지를 재전송 |
| 99 | Supply Chain Compromise | US-8 | EU-2 | TS 33.117, 33.501 | P7 | 장비·소프트웨어·오픈소스 공급망을 통해 공격 |
| 100 | 5G Security Misconfiguration | US-1,8 | EU-1,2,3 | TS 33.501 | P1,P7 | 표준에 보안기능이 존재하지만 실제 운영환경에서 잘못 설정해 발생하는 취약점 |

---

# **4\. 그런데 이 100개를 그냥 사이트에 올리면 아깝습니다**

제가 보기에는 **이 100개를 사이트의 최상위 메뉴로 쓰는 것보다**, 각각을 하나의 **Security Issue Page**로 만드는 게 훨씬 좋습니다.

예를 들어:

### **`False Base Station`**

사이트 페이지를 이런 식으로 만드는 겁니다.

**5G Security Issue \#05**

# **False Base Station**

### **① What is it?**

가짜 기지국을 이용해 UE가 정상 네트워크가 아닌 공격자 네트워크에 접속하도록 유도하는 공격.

### **② Why is it possible?**

5G 초기 접속 과정에서 UE와 네트워크 사이의 신뢰가 형성되는 과정에 공격면이 존재하기 때문.

### **③ Attack Target**

`UE → RAN → Authentication`

### **④ Attack Scenario**

UE  
 ↓  
Fake gNB  
 ↓  
NAS / RRC  
 ↓  
Attacker

### **⑤ Impact**

* Identity Privacy  
* Location Privacy  
* Availability  
* Authentication

### **⑥ 3GPP**

* TS 33.501  
* TR 33.809  
* TS 38.331

### **⑦ US Perspective**

NIST CSWP 36A  
 → SUCI protection

### **⑧ Europe Perspective**

ENISA 5G Threat Landscape

### **⑨ Research**

P1 — 5G SA Attack Survey

### **⑩ 한국어 해설**

> **쉽게 말하면:** 공격자가 진짜 기지국처럼 행동해서 휴대폰을 자기 쪽으로 끌어들이는 공격이다.

이런 식입니다.

---

# **5\. 특히 NIST 자료는 별도의 메뉴로 만들 가치가 있습니다**

2026년 NIST 자료가 상당히 좋습니다.

현재 NIST 5G CSWP 36 시리즈는:

**36A — SUCI**

↓

**36B — Hardware Root of Trust**

↓

**36C — Temporary Identity**

↓

**36D — No-SUPI Paging**

↓

**36E — Network Security Design**

↓

**36F — Initial NAS Message Security**

구조입니다.

즉 사이트에서 아예

> **🇺🇸 NIST 5G Security Lab**

같은 메뉴를 만들고 각각을 한국어로 해설하면 상당히 좋은 콘텐츠가 됩니다.

특히 **36F는 2026년 8월 6일 공개된 최신 Initial Public Draft**라서 지금 시점에서는 상당히 신선한 주제입니다. NIST는 Initial NAS Message의 민감정보 보호와 실제 배포 네트워크에서 이를 검증하는 방법까지 다룹니다.

---

# **6\. 그리고 ENISA는 "위협 데이터베이스"로 쓰면 좋습니다**

ENISA의 장점은 **공격 하나하나보다 전체적인 Threat Landscape를 보는 것**입니다.

ENISA 5G Threat Landscape는

**Asset**

→ **Vulnerability**

→ **Threat**

→ **Threat Agent**

→ **Impact**

→ **Security Control**

로 연결해서 보는 구조입니다.

그리고 ENISA Security Controls Matrix에는 무려 **399개 detailed security controls**가 있기 때문에, 위 100개 공격 항목에 대응하는 **Security Control Database**를 별도로 만들 수 있습니다.

---

# **7\. 사이트 전체 구조는 이렇게 만드는 것을 추천합니다**

5G SECURITY  
│  
├── 01\. 5G Security Fundamentals  
│  
├── 02\. UE & Privacy  
│    ├── SUPI Exposure  
│    ├── SUCI  
│    ├── False Base Station  
│    └── Temporary Identity  
│  
├── 03\. RAN Security  
│    ├── Jamming  
│    ├── RACH Attack  
│    ├── RRC Attack  
│    └── gNB Security  
│  
├── 04\. 5G Core Security  
│  
├── 05\. SBA Security  
│  
├── 06\. Network Slicing  
│  
├── 07\. NFV / Cloud  
│  
├── 08\. O-RAN  
│  
├── 09\. V2X  
│  
├── 10\. Supply Chain  
│  
├── 11\. 3GPP Security Standards  
│  
├── 12\. ENISA  
│  
├── 13\. NIST  
│  
├── 14\. CISA / NSA  
│  
└── 15\. Research Papers

그리고 각 Issue 페이지에는 **동일한 10개 항목**을 적용합니다.

> **Threat → Target → Vulnerability → Attack Scenario → Impact → 3GPP → ENISA → NIST/CISA/NSA → Paper → Korean Explanation**

이렇게 하면 사이트 전체가 **“5G 보안 논문을 번역해 놓은 사이트”가 아니라, 3GPP 표준과 미국·유럽 정부기관 자료와 논문을 서로 연결해주는 5G Security Knowledge Base**가 됩니다.

그리고 이 구조는 **나중에 ISMS-P/CSAP/정보시스템감리/5G 보안 컨설팅 자료로 활용하기에도 상당히 좋습니다.** 특히 NIST가 강조하듯 5G 표준에 보안 기능이 정의되어 있어도 실제 운영자가 어떻게 구성·구현하느냐에 따라 보안 수준이 달라질 수 있기 때문에, **“표준 요구사항 → 실제 설정 → 보안통제 → 검증방법”**까지 연결하는 것이 사이트의 차별점이 될 수 있습니다.

**다음 단계로는 이 100개를 제가 실제 웹사이트용 콘텐츠 DB 형태로 바꾸는 것이 가장 좋습니다.** 즉 각 항목을 `ID / 영문명 / 한글명 / 공격 시나리오 / 취약점 / 영향(C-I-A) / 대상 NF·인터페이스 / 3GPP TS·TR / ENISA 문서 / NIST 문서 / CISA·NSA 문서 / 논문 DOI / 500자 한국어 해설 / 난이도`로 확장하면 **엑셀로 바로 관리할 수 있는 100개짜리 5G Security 콘텐츠 데이터베이스**가 됩니다.

100개 이슈를 체계적으로 공부하실 수 있도록 각 출처의 **공식 접근 경로와 검색/활용 방법**을 정리해 드립니다.

3GPP나 NIST, ENISA 등 주요 기관의 개별 문서는 정적 URL이 변경되거나 직접 링크 연결 시 차단되는 경우가 많아, 각 기관이 공식적으로 제공하는 **검색 엔진 및 리소스 라이브러리**를 통해 접근하시는 것이 가장 정확합니다.

### **1\. 3GPP 표준 규격서 (TS / TR)**

3GPP 문서는 공식 FTP 서버 또는 검색 페이지에서 규격 번호(예: TS 33.501, TR 33.809)로 조회하여 최신 버전 PDF를 바로 다운로드할 수 있습니다.

* **3GPP Specification Search**: [https://www.3gpp.org/specifications-technologies/specifications-search](https://www.google.com/search?q=https://www.3gpp.org/specifications-technologies/specifications-search)  
* **3GPP FTP Server (전체 규격 저장소)**: [https://www.3gpp.org/ftp/Specs/archive/](https://www.3gpp.org/ftp/Specs/archive/)  
  **공부 팁**: `33 series`(Security) 폴더로 들어가면 `33.501`(5G Security Architecture) 및 `33.809`(FBS 대응) 등 핵심 보고서를 한눈에 볼 수 있습니다.

### **2\. 미국 NIST (CSWP 36 시리즈)**

NIST Computer Security Resource Center(CSRC)에서 5G 보안 가이드라인과 36 시리즈(36A\~36F)를 직접 검색하여 원문을 다운로드할 수 있습니다.

* **NIST CSRC Publications**: [https://csrc.nist.gov/publications](https://csrc.nist.gov/publications)  
  **검색 방법**: Search 키워드에 **`CSWP 36`** 또는 \*\*`Applying 5G Cybersecurity`\*\*를 입력하면 SUCI, Temporary Identity, Initial NAS Security 등 시리즈 전체 목록이 출력됩니다.

### **3\. 유럽 ENISA (Threat Landscape & Security Controls)**

유럽 사이버보안청의 5G 위협 보고서와 보안 통제 매트릭스 자료는 ENISA 공식 Publications 포털에서 제공됩니다.

* **ENISA Publications Portal**: [https://www.enisa.europa.eu/publications](https://www.enisa.europa.eu/publications)  
  **검색 방법**: 검색창에 **`5G Threat Landscape`** 또는 \*\*`5G Security Controls Matrix`\*\*를 입력하시면 보고서 및 Excel 스프레드시트 원본을 받으실 수 있습니다\[cite: 1\].

### **4\. 미국 CISA / NSA (5G Security Library)**

CISA의 5G 전용 라이브러리에서 Network Slicing, Cloud Infrastructure, Threat Vectors 관련 지침서를 확인할 수 있습니다.

* **CISA 5G Resource Library**: [https://www.cisa.gov/5g-library](https://www.cisa.gov/5g-library)\[cite: 1\]

### **5\. 추천 학습 로드맵 (4-Step Workflow)**

1. **개념 잡기 (ENISA / CISA)**: ENISA Threat Landscape 및 CISA 5G Library에서 해당 이슈의 **공격 시나리오와 위협 개요**를 먼저 읽습니다\[cite: 1\].  
2. **기술 표준 확인 (3GPP)**: 3GPP 검색 페이지에서 관련 **TS/TR 규격서**를 다운로드받아 프로토콜 수준의 메커니즘을 파악합니다.  
3. **실무 구현/검증 참고 (NIST)**: NIST CSWP 36 문서에서 해당 기술이 **실제 테스트베드에서 어떻게 검증/설정**되는지 확인합니다\[cite: 1\].  
4. **학술 연구 심화 (Google Scholar)**: [Google Scholar](https://scholar.google.com)에 `이슈 영문명 + 5G` (예: `"False Base Station" "5G"`)를 검색하여 최신 공격/방어 논문을 참조합니다.

