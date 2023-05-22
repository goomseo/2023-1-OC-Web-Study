# GDSC 기초 웹 스터디 WIL - Week 8

(원문 URL: [GDSC 기초 웹 스터디 8주차 WIL - Notion](https://goomseo.notion.site/Week8-0520c586e9774de6bd06989ffedab890))

새로 알게 된 내용 혹은 기억하고 싶은 내용을 정리하였다.

# JavaScript 복습 내용 정리

## 1. 기본 개념과 동작 원리 이해의 중요성

- 요구 사항을 명확히 이해한 후 이를 이행하기 위한 문제 해결 능력이 필요하다. 요구 사항을 단순하게 분해하고 자료를 정리하고 구분해야하며 순서에 맞게 행위를 배열해야 한다. 이러기 위해서는 컴퓨터의 입장에서 문제를 바라볼 줄 알아야 한다. → Computational Thinking
- 프로그래밍 언어의 기본 개념과 동작 원리를 제대로 이해하여 기본기를 쌓는 것이 중요하다.

## 5. 자바스크립트의 기본 문법

- 데이터 타입
  - 원시 타입(primitive data type)
    - number
    - string
    - boolean
    - null
    - undefined
    - symbol
  - 객체 타입(object date type)
    - object
- Block-level scope가 아닌 Function-level scope만이 생성된다.
- JavaScript는 객체 기반의 스크립트 언어이며, 원시 타입을 제외한 거의 모든 것이 객체이다.

## 6. 데이터 타입과 변수

- JavaScript의 변수에는 고정된 타입이 없어 값이 변수에 할당되는 과정에서 자동으로 변수의 타입이 결정된다. 이를 타입 추론(Type Inference)라 한다. → JavaScript는 동적 타입(Dynamic Type) 언어이다.
- 숫자 타입은 하나로, double-precision 64-bit floating-point format을 따른다. 즉 1과 1.0은 같다.
- 자바스크립트의 문자열은 immutable하다. 즉 인덱싱이 가능하더라도 이를 통해 기존 문자열을 부분적으로 수정하는 것은 불가능하다.
- 아래 코드를 실행하게 되면 ‘Hello’ 문자열이 ‘world’로 수정되는 것이 아니라, 새로운 문자열 ‘world’가 ‘Hello’ 대신 변수 str에 할당되는 것이다.
  ```jsx
  var str = "Hello";
  str = "world";
  ```
- boolean 타입은 null, undefined, 0을 false로 간주한다.
- 선언 이후 값을 할당하지 않은 변수는 undefined 값을 가진다.
- typeof null의 결과는 null이 아닌 object가 나오는데, 이는 설계상의 오류이다. null 타입인 것을 확인하려면 아래와 같은 방식으로 해야한다.
  ```jsx
  var foo = null;
  console.log(typeof foo === null); // false (typeof foo의 결과가 object)
  console.log(foo === null); // true
  ```
- Hoisting: 모든 선언문이 해당 스코프의 선두로 옮겨진 것처럼 동작하는 특성. 즉 JavaScript는 모든 선언문이 선언되기 이전에 참조 가능하다.
- var 키워드보다는 const 키워드를 사용해야 한다.

## 7. 연산자

- === (일치 비교) 연산자는 == 연산자의 역할 && 두 값의 타입이 같은 지까지 체크한다.
- !==는 두 값의 값과 타입이 다른지 체크한다.
- NaN === NaN은 false이므로, NaN임을 알고 싶으면 isNaN 함수를 사용해야 한다.

## 9. 타입 변환과 단축 평가

- 의도치 않은 암묵적 타입 변환이 어떤 결과를 초래할 지 항상 유의해야 한다.

## 14. 프로토타입

- JavaScript는 클래스 기반의 객체지향 언어가 아닌 프로토타입 기반의 객체지향 언어이므로, 프로토타입의 개념을 잘 이해해야 한다.
- JavaScript는 클래스 없이도 객체를 생성할 수 있다.
- 모든 객체는 **proto** 프로퍼티로 자신의 부모 객체(프로토타입 객체)인 Object.prototype을 가리키고 있다. 결정된 프로토타입 객체는 다른 임의의 객체로 변경될 수 있으며, 이 특징을 이용하여 객체의 상속을 구현할 수 있다.
- 함수는 일반 객체와 달리 [[Prototype]] 인터널 슬롯을 갖는 동시에 prototype 프로퍼티도 소유하게 된다. prototype 프로퍼티는 함수 객체가 생성자로 사용될 때 이 함수를 통해 생성될 색체의 부모 역할을 하는 객체를 가리킨다.

## 15. 스코프

- 함수 레벨 스코프(function-level scope)를 따른다.

---

# ECMAScript6

## 1. let, const와 블록 레벨 스코프

- ES5까지는 var 키워드로만 변수를 선언할 수 있었는데, 이 때 전역 변수로 인해 많은 문제들이 발생할 수 있다. → ES6에서는 이를 방지하기 위해 let과 const 키워드를 도입하였다.
- let 키워드
  - 다른 언어에서처럼 블록 레벨 스코프를 따르는 변수를 선언할 수 있다.
  - 동일한 이름을 갖는 변수를 중복해서 선언할 수 없게 한다.
- const는 상수를 위해 사용되지만, 반드시 상수만을 위해 사용하지는 않다.
  - let과의 차이점: 재할당 금지 → 선언과 동시에 할당이 이루어져야 한다.
- **결론: var은 사용하지 말고, 디폴트로는 const를 사용하되 재할당이 필요한 경우에 한정하여 let을 사용한다.**
