# GDSC 기초 웹 스터디 WIL - Week 5

(원문 URL: [GDSC 기초 웹 스터디 5주차 WIL - Notion](https://goomseo.notion.site/Week5-d2247ad1cd224edfa8cbd7c36b5c2fa7))

새로 알게 된 내용 혹은 기억하고 싶은 내용을 정리하였다.

# HTML5 복습 내용 정리

## HTML5 기본 문법

- Empty Element(Self-Closing Element): content를 가질 수 없는 요소. Attribute만을 가질 수 있다.
  - 예시:
    ```html
    <meta charset="utf-8" />
    ```
- Attribute: element의 성질, 특징을 정의하는 명세. 시작 태그에 위치해야 하며 name과 value가 쌍을 이룬다.
- 주석: <!—로 열고 —>로 닫기

## 시맨틱 요소와 검색 엔진

- 검색 엔진의 Crawler가 Crawling을 수행하여 전세계의 웹사이트 정보를 수집한다. 그리고 검색 엔진의 Indexer가 Indexing을 수행하여 검색 사이트 이용자가 검색할 만한 키워드를 미리 예상하여 검색 키워드에 대응하는 index를 만들어둔다.
  - Indexing에서는 크롤러가 수진한 정보, 즉 웹사이트의 HTML 코드를 사용한다. 즉, 검색 엔진은 HTML 코드만으로 의미를 인지하여햐 하는데, 이 때 Semantic Element를 해석하게 된다. 이를 해석함으로써 그 데이터를 활용할 수 있는 Semantic Web이 실현될 수 있는 것이다.
  - Semantic Element는 브라우저, 검색 엔진, 개발자 모두에게 content의 의미를 명확히 설명하는 역할을 한다.

## 웹페이지를 구성하는 기본 태그

- head tag에 들어가는 요소
  - ling tag: 외부 리소스와의 연계 정보를 정의한다. 주로 HTML과 외부 CSS 파일을 연계에 사용한다.
  - script tag: client-side JavaScript를 정의한다.
  - meta tag: description, keywords, author, 기타 메타데이터 정의에 사용되며, 메타데이터는 브라주어와 검색 엔진 등에 의해 사용된다.
- body tag: 메타데이터를 제외한 웹페이지를 구성하는 댑주분의 요소가 이 내부에 기술된다.

## 텍스트 관련 태그

- Text Formatting 태그
  - b 태그와 strong 태그의 차이: 전자는 semantic적 중요성이 없고, 후자는 있다. 후자를 사용하는 것이 바람직하다.
  - i 태그와 em 태그도 위와 동일한 차이를 보인다.
- 본문 태그
  - br 태그는 empty element이다. 또한 종료 태그가 없다.
  - HTML에서는 1개 이상의 연속된 공백 혹은 줄바꿈은 모두 1개로 처리된다. 공백을 연속으로 사용하려면 &nbsp를 이용하면 된다.

---

# CSS 복습 내용 정리

## CSS 기본 문법

- CSS(Cascading Style Sheet): HTML이나 XML과 같은 구조화된 문서를 화면, 종이 등에 어떻게 렌더링할 것인지를 정의하기 위한 언어이다. 즉 HTML의 각 Element의 스타일을 정의하여 화면 등에 어떻게 렌더링하면 되는지 브라우저에게 설명하기 위한 언어이다. HTML과는 다른 문법을 갖는 별개의 언어이다.
- HTML은 CSS를 포함할 수 있지만, HTML없이 단독으로 존재하는 CSS는 의미가 없다.
- Selector: 스타일을 적용하고자 하는 HTML 요소를 선택하기 위한 수단
  - 셀렉터로 HTML 요소를 선택하고 중괄호 내에서 property: property value를 나열하여 다양한 스타일을 정의할 수 있다.
- CSS와 HTML을 연동하는 방법
  - Link Style: link 태그 이용하여 외부에 있는 CSS 파일을 로드하기. 이 방법이 일반적이다.
  - Embedding Style: HTML 내부에 CSS를 포함시키는 방식
  - Inline style: HTML 요소의 style property에 CSS를 기술하는 방식

## 셀렉터

- 수많은 종류의 셀렉터가 있다. 모두 암기할 필요는 없으며 차차 익혀 나가도록 한다.

## CSS Property 값의 단위

- 각 프로퍼티에 따라 사용할 수 있는 키워드가 존재한다.
- 크기 단위
  - 대부분 브라우저의 폰트 사이즈 dafault: 16px, 1em, 100%. 픽셀은 절대값이고, 나머지 둘은 상대값이다.
  - rem, viewport(vw, vh, vmin, vmax) 등이 존재한다.
- 색상 표현 단위
  - 키워드로 색상을 지정하는 것은 제한적이다.
  - 더욱 다양한 색상을 표현하기 위해 HEX, RGB, RGBA, HSL, HSLA와 같은 색상 표현 단위를 사용할 수 있다.

## 박스 모델

- 모든 HTML 요소는 박스 형태의 영역을 가지고 있으며, 이 박스는 Content, Padding, Border, Margin으로 구성된다.
  - Content: 요소의 텍스트나 이미지 등의 실제 내용이 위치하는 영역. width, height 프로퍼티를 갖는다.
  - Padding: Border 안쪽에 위치하는 요소의 내부 여백 영역이다. Padding 프로퍼티 값은 패딩 영역의 두께를 의미하며 기본색은 투명이다. 요소에 적용된 배경의 컬러, 이미지는 패딩 영역까지 적용된다.
  - Border: 테두리 영역으로 border 프로퍼티 값은 테두리의 두께를 의미한다.
  - Margin: 테두리 바깥에 위치하는 요소의 외부 여백 영역이다. margin 프로퍼티 값은 마진 영역의 두께를 의미한다. 기본적으로 투명하며 배경색을 지정할 수 없다.
- 브라우저는 박스 모델의 크기(Dimension)와 프로퍼티, 위치를 근거로 하여 렌더링을 실행한다.
