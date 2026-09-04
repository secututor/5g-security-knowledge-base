# .gitbook/assets

이미지/SVG 등 정적 자산을 두는 폴더입니다. **GitBook 웹 에디터가 이미지 업로드 시 사용하는 기본 경로**로,
GitHub 동기화 환경에서 직접 작성한 SVG와 웹 업로드본이 한 곳에 모입니다.

## 규칙 (`.kiro/steering/rules-diagrams.md` §2 참조)
- 다이어그램은 **Mermaid 우선**. 정교한 그림만 SVG로 여기에 둔다.
- **파일명은 그 그림이 들어가는 문서 파일명(stem)을 prefix + 그림 설명 suffix**. 공백 없이 `_` 사용.
  - 예: 문서 `02-05-False_Base_Station.md` → SVG `02-05-False_Base_Station_attack_flow.svg`
  - 그림이 하나면 suffix 생략 가능: `02-05-False_Base_Station.svg`
  - 여러 문서 공유 공통 개념도만 예외적으로 설명형 이름 허용
- SVG는 `viewBox` 명시, 텍스트는 `<text>` 요소로(이미지로 굽지 않음), 대비 확보.
- 문서에서 참조 시 상대경로 사용. 예(카테고리 폴더 안 문서 기준):
  ```markdown
  ![5G 키 계층 구조](../.gitbook/assets/01-01-5G_Key_Hierarchy.svg)
  ```
- 외부 문서의 그림/로고를 그대로 복사해 넣지 않는다 (§6.4 저작권 규칙).

> 이 폴더는 `SUMMARY.md` 목차에 포함하지 않는다.
