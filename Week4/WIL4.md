# GDSC 기초 웹 스터디 WIL - Week 4

(원문 URL: [GDSC 기초 웹 스터디 4주차 WIL - Notion](https://goomseo.notion.site/Week4-998fe523a8a04a1883e13932f20a6946))

# HTML이란?

![HTML은 프로그래밍 언어와는 분명한 차이가 있다. (출처 - [클릭](https://www.reddit.com/r/ProgrammerHumor/comments/axm4xv/html_is_not_a_programming_language/))](https://i.redd.it/4c9uyah5gbk21.jpg)

HTML은 프로그래밍 언어와는 분명한 차이가 있다. (출처 - [클릭](https://www.reddit.com/r/ProgrammerHumor/comments/axm4xv/html_is_not_a_programming_language/))

Hyper Text Markup Language ➡️ HTML

HTML은 웹사이트의 모습을 기술하기 위한 마크업 언어이다. 컴퓨터공학도라면 한 번쯤은 들어봤을, 웹의 아버지라고 불리는 팀 버너스리(Tim Berners-Lee, 영국)가 고안하였다.

> Q. 그렇다면 마크업 언어(MarkUp Language)란 무엇일까? 그리고 우리는 마크다운(MarkDown)에 들어봤는데, 이 둘은 무슨 차이일까?
>
> A. 마크다운 언어는 마크업의 한 종류이다. 마크다운 언어는 경량 마크업 언어라고 할 수 있다. 마크업 언어에 비해 문법이 쉽고 간단하며, 이에 반해 마크업 언어는 온갖 태그들로 구성되어 마크다운 언어보다 다소 번잡해 보일 수 있다.

HTML은 태그(Tag)들로 이루어져 있는데, HTML을 기술하기 위하여 사용하는 명령어의 집합을 태그라고 한다.

속성(Attribute)는 태그의 동작을 제어하기 위해 여는 태그 안에서 사용되는 특수 용어로, 요소 유형의 기본 기능을 수정하거나 스스로 기능하지 못하는 특정한 요소 유형에 기능을 제공한다.

---

# 과제 수행 - Bingo.html

아래 이미지와 최대한 비슷하게 만들고, 주제를 정해 빙고를 만드는 것이 과제이다.

![https://oopy.lazyrockets.com/api/v2/notion/image?src=https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F1bb5f2dd-81e1-44a9-ab39-6f38211f47ab%2FUntitled.png&blockId=92541ce1-500b-4904-a996-5ac302fd6e36](https://oopy.lazyrockets.com/api/v2/notion/image?src=https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F1bb5f2dd-81e1-44a9-ab39-6f38211f47ab%2FUntitled.png&blockId=92541ce1-500b-4904-a996-5ac302fd6e36)

다음은 html로 작성한 과제물이다.

과제물에서 사용한 모든 태그와 속성들에 대해 정리하였다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>구민서 지하철 노선 빙고</title>
  </head>
  <body>
    <h1>구민서 지하철 노선 빙고</h1>
    지하철 노선을 주제로 만든 빙고입니다.<br />
    <ul>
      <li><mark>가장 좋아하는 노선을 </mark>형광펜으로 그어봅시다.</li>
      <li>
        <b><u>가장 싫어하는 노선</u></b
        >을 볼드체와 밑줄로 강조해봅시다.
      </li>
    </ul>

    <table border="1">
      <tr>
        <td>수인분당선</td>
        <td>2호선</td>
        <td>5호선</td>
      </tr>
      <tr>
        <td><mark>6호선</mark></td>
        <td>공항철도</td>
        <td>9호선</td>
      </tr>
      <tr>
        <td>3호선</td>
        <td>
          <b><u>경의중앙선</u></b>
        </td>
        <td>1호선</td>
      </tr>
    </table>

    <br />

    <label for="inputLine">이번 차례 체크할 노선 : &nbsp;</label
    ><input type="text" placeholder="노선 이름을 입력하세요.." id="inputLine" />
  </body>
</html>
```

- DOCTYPE html : 마크업 언어용 DTD(Document Type Definition) 선언이다. html 태그를 정의하기 전에 가장 먼저 선언되어야만 한다. 선언된 페이지의 HTML 머전이 무엇인지 웹 브라우저에게 알려주는 역할을 한다.
- html : HTML이 작용하는 범위는 지정하는 태그이다. DTD 선언을 제외한 전체를 이 태그로 둘러싸는데, C언어로 따지면 main함수와 비슷하다고 할 수 있겠다.
- head : HTML 문서의 속성 범위를 지정하기 위한 태그로, 메타 태그와 타이틀 태그가 내부에 주로 작성된다.
  - meta : HTML의 부가 정보를 선언하는 태그이다. 위 코드를 보면 인코딩 방식 등을 선언하는 것을 알 수 있다.
  - title : HTML의 제목을 선언하는 태그로, 웹 브라우저의 탭에 뜨는 이름이 이것이다.
- body : HTML 문서의 본문 범위를 지정하기 위한 태그로, 표시될 문서의 레이아웃을 이 태그 안에 넣는다.
  - h1 - h6 : 제목(Heading)을 표시할 때 사용하는 태그로, 숫자가 작을수록 크게 표시된다.
  - br : 문단 내 줄바꿈(line break)을 수행하는 태그이다.
  - ul : 순서 없는 리스트(Unordered List)를 표시하는 태그이다.
    - li : 리스트의 각 항목(List Item)은 이 사이에 삽입한다.
  - mark : 형광펜으로 하이라이트를 적용한다.
  - b : 볼드(Bold)체 효과를 주는 태그이다. 수업 때 이를 사용하여 과제에서도 b 태그를 사용하였는데, strong 태그로 대체하여 사용할 것을 권장한다고 한다.
  - u : 밑줄(Underline)을 표시하는 태그이다.
  - table : 테이블을 만드는 태그이다. 여기에서 사용한 border 속성은 테이블의 윤곽선을 지정하는 역할을 한다.
    - tr : 테이블의 행(Table Row)을 시작할 때 사용하는 태그이다.
    - td : 표의 내용(Table Data)을 표현할 때 사용하는 태그이며, tr 태그로 둘러쌓인 영역에서 작성한다.
  - label : 요소의 이름을 지정하는 것으로, 이 이름을 클릭하면 이에 해당하는 요소가 자동으로 선택된다. 여기에서 사용한 for 속성에는 어떤 요소와 연결할 것인지 입력할 수 있다. 또한 &nbsp라는 HTML 엔티티가 사용되었는데, 이는 No-Break-SPace의 약자로서 공백 한 칸을 삽입하는 역할을 한다.
  - input : 입력값 요소를 지정하는 태그로, type 속성에 따라 다른 입력값을 취한다. 여기서는 텍스트로 입력을 받도록 하였다. placeholder 속성은 입력 필드에 사용자가 적절한 값을 입력할 수 있도록 도와주는 도움말을 명시해주며, id 속성은 해당 요소의 고유 식별자로서 label 태그와 상호작용 할 수 있게 해준다.

아래는 결과이다.

![https://goomseo.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F7798d47e-1f9b-4a77-8a69-e37b2156e2ab%2F%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-04-10_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_11.52.35.png?id=3e8708fe-7187-4cda-84c4-57f7aa9f62eb&table=block&spaceId=cae03794-17b8-4ef4-ba76-6b600ee8c90f&width=860&userId=&cache=v2](https://goomseo.notion.site/image/https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fsecure.notion-static.com%2F7798d47e-1f9b-4a77-8a69-e37b2156e2ab%2F%25E1%2584%2589%25E1%2585%25B3%25E1%2584%258F%25E1%2585%25B3%25E1%2584%2585%25E1%2585%25B5%25E1%2586%25AB%25E1%2584%2589%25E1%2585%25A3%25E1%2586%25BA_2023-04-10_%25E1%2584%258B%25E1%2585%25A9%25E1%2584%2592%25E1%2585%25AE_11.52.35.png?id=3e8708fe-7187-4cda-84c4-57f7aa9f62eb&table=block&spaceId=cae03794-17b8-4ef4-ba76-6b600ee8c90f&width=860&userId=&cache=v2)
