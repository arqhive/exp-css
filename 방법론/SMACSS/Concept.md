# SMACSS (Scalable and Modular Architecture for CSS)

- CSS에 대한 확장형 모듈식 구조
- 클래스명을 통한 예측
- 재사용
- 쉬운 유지보수
- 확장 가능

- 카테고리를 나누는 기준이 작성자에 따라서 애매함
- 코드를 나누어서 작성해야 하기 떄문에 더 번거로워 질수 있음

## 규칙

Base - 각 브라우저의 기본 스타일 (default.css, reset.css), 요소 element 스타일의 기본 정의 값

Layout - 큰 틀의 레이아웃, 요소를 배치, 구별하는데 적용
주요 컴포넘트 : header, footer, aside, container, content 등
하위 컴포넘트 : list, item, form 등
클래스명은 접수사 i-, layout-명시

Module - 모듈 규칙
페이지에서 재사용 가능한 요소 : 버튼, 배너, 아이콘, 박스 요소 등
각 모듈은 독립성을 가지게 스타일 선언 : 재사용이 가능하게 id, 태그 선택자는 사용하지 않음.

State - 상태 규칙
요소의 상태변화를 표현하는 요소 : 툴팁, 아코디언 등
active나 disable 등이며 suffix "is-"나 "s-"를 붙여서 사용
모듈과 레이아웃 모두 적용 가능

Theme - 테마 규칙
사용자가 선택 가능하도록 스타일을 재선언하여 사용.
Theme는 전반적인 Look and feel을 정의하며 suffix "theme-"를 붙인다.
 