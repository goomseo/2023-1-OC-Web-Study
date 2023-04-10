# GDSC 기초 웹 스터디 WIL - Week 2

(원문 URL: [GDSC 기초 웹 스터디 2주차 WIL - Notion](https://goomseo.notion.site/Week2-f89722dc352c480788e43dddad5c1267))

# Week 1 복습

## URI? URL? URN...?

![https://velog.velcdn.com/images/goomseo/post/f19b6674-b28f-47fc-9188-18b851e7b345/image.png](https://velog.velcdn.com/images/goomseo/post/f19b6674-b28f-47fc-9188-18b851e7b345/image.png)

(이미지 출처 - [클릭](https://www.researchgate.net/figure/The-illustration-of-the-URL-URN-and-URI-26_fig4_346585530))

우선 URI에 URL과 URN이 포함되어 있다는 사실을 알고 넘어가자.
또한 uniform과 resource의 의미를 짚고 넘어가도록 하자.

> uniform: 리소스를 식별하는 통일된 방식
> 

> resource: 자원, URI로 식별할 수 있는 모든 것
> 
- URI: Uniform Resource Identifier, 통합 자원 식별자
URI는 인터넷에 있는 리소스가 어디에 있는지 리소스 자체를 식별하는 방법으로, 인터넷에 있는 리소스를 나타내는 유일한 주소이다. URI의 존재는 인터넷에서 요구되는 기본 조건으로서 인터넷 프로토콜에 항상 붙어 다닌다. 즉 URI는 특정 자원을 식별하는 문자열을 의미한다.

URI에는 두 가지의 형태가 있는 것인데, 그것들이 바로 URL과 URN이다.

- URL: Uniform Resoure Locator
URL은 특정 서버의 한 리소스에 대한 구체적인 위치를 서술하며, 리소스가 정확히 어디에 있고 어떻게 접근할 수 있는지 분명이 알려준다.
- URN: Uniform Resource Name
URN은 콘텐츠를 이루는 한 리소스에 대해 그 리소스의 위치에 영향을 받지 않는 유일무이한 이름의 역할을 한다. 즉 리소스를 여기저기로 옮기더라도 URN은 이로부터 독립적이기에 문제없이 동작한다.

---

## DNS (Domain Name System)

![https://velog.velcdn.com/images/goomseo/post/5200e70d-df67-4e9c-bbf2-697fa1e991c7/image.webp](https://velog.velcdn.com/images/goomseo/post/5200e70d-df67-4e9c-bbf2-697fa1e991c7/image.webp)

(이미지 출처 - [클릭](https://hanamon.kr/%EB%84%A4%ED%8A%B8%EC%9B%8C%ED%81%AC-%EA%B8%B0%EB%B3%B8-%EB%8F%84%EB%A9%94%EC%9D%B8%EA%B3%BC-dns-%EB%84%A4%EC%9E%84%EC%84%9C%EB%B2%84%EB%9E%80-%EA%B0%9C%EB%85%90%ED%8E%B8/))

숫자로 이루어진 ip 주소는 외우기 힘들고 타이핑 또한 번거로우므로 편의를 위해 문자로 된 텍스트(도메인 주소)로 ip 주소를 치환한다.

사용자가 브라우저에서 도메인 주소를 입력하면 **도메인 주소 = ip 주소**를 기억하고 있는 DNS 서버가 브라우저에게 ip 주소를 반환해주어 사용자가 원하는 웹사이트로 접속할 수 있도록 해준다.

---

# Week 2 복습

아래는 2주차 수업의 뼈대가 되는 사진이다. git의 작동 원리를 한 눈에 보여준다.

![https://velog.velcdn.com/images/goomseo/post/bb22e0b2-ffd0-4d6d-8d77-e5d6e31342d1/image.png](https://velog.velcdn.com/images/goomseo/post/bb22e0b2-ffd0-4d6d-8d77-e5d6e31342d1/image.png)

(이미지 출처 - [클릭](https://www.alibabacloud.com/blog/a-detailed-explanation-of-the-underlying-data-structures-and-principles-of-git_597391))

## git의 기본적인 명령어

### 1. add

Working Directory에서 발생한 변화들을 Staging Area로 옮기기 위하여 add 명령어를 사용한다. 이 때 Working Directory는 현재 내가 코드를 짜고 있는 작업 공간이다.

### 2. commit

add 명령어에 의해 Staging Area에 변화들이 축적이 되는데, 이 변화들을 묶어 Local Repository로 옮기고 싶을 때 commit 명령어를 사용할 수 있다. 즉, Staging Area는 Local Repository로 파일들의 변화가 가기 전에 거치는 중간 공간 역할을 한다.

그렇다면 왜 한 번에 Local Repository로 향하게 하지 않고 중간에 다른 곳을(Staging Area) 거치게 하는 것일까? 이는 여러 변화들을 축적시킨 뒤 원하는 변화끼리 묶어 이름을 붙여 하나의 묶음으로 변화를 반영하기 위함이라고 할 수 있다. 또한 commit은 어떤 것을 삭제하고 추가 하였는지 타임 라인을 볼 수 있다.

이 때 git에서 Local Repository의 역할은 .git directory가 수행한다. git init을 터미널에 입력하면 프로젝트에서 .git 폴더가 보일 것이다. 만약 보이지 않는다면 mac os에서는 command + shift + .을 누르면 숨김 폴더 및 파일들이 보인다.

### 3. push

눈치가 빠른 사람은 add와 push에 대한 설명을 읽었다면 아직 변화들이 github로는 전달되지 않았음을 알아챘을 수도 있을 것이다. (add와 commit을 수행한 후 변화들이 머무르게 되는 최종 위치는 **Local** Repository이기 때문이다.) git은 많은 사람들과 협업을 하기 위한 툴이라고 알고 있는데, 아직 그 기능을 수행하지 못하는 것이다.

commit까지 완료한 변화들을 외부와 공유하기 위해 **Remote Repository**가 필요한 것이다. 이 때 우리가 사용하게 되는 Remote Repository를 제공하는 서비스가 **Github**인 것이다.

push 명령어를 이용하면 변화들을 Local Repository에서 Remote Repository로 밀어넣을(push) 수 있다.

---

## git pull과 fetch의 차이점

상단에 첨부하였던 사진을 다시 한 번 살펴보자.

![https://velog.velcdn.com/images/goomseo/post/bb22e0b2-ffd0-4d6d-8d77-e5d6e31342d1/image.png](https://velog.velcdn.com/images/goomseo/post/bb22e0b2-ffd0-4d6d-8d77-e5d6e31342d1/image.png)

(이미지 출처 - [클릭](https://www.alibabacloud.com/blog/a-detailed-explanation-of-the-underlying-data-structures-and-principles-of-git_597391))

"pull/rebase"가 쓰여있는 화살표와 두 줄 아래 우측에 "fetch"라고 쓰여있는 화살표가 보인다.

사진 상으로 확인 가능한 공통점은 오른쪽에서 왼쪽, 즉 Remote Server에서 Local로 향하고 있다는 것이다. 이는 둘 다 Remote Respository의 내용을 Local로 가져온다는 의미이다.

pull과 fetch는 Remote Repository에서 가져온 변경 사항들을 **자동으로 병합을 해주는지의 여부**에 차이가 있다.

우선 fetch에 대해 알아보자.

- fetch는 Remote Repository와 Local Repository의 변경 사항들이 다를 때 용이하다. Remote Repoisoty에 있는 변경 사항들을 Local Repository에 저장하기 전에 두 공간에서 어떤 차이가 있는지 확인하고자 할 때 fetch 명령어를 쓸 수 있다. fetch 명령어를 사용한 후 checkout을 하면 fetch로 가져온 변경 사항들을 Local Repository에 저장 되지 않은 채로 확인할 수 있다. fetch 명령어를 이용하면 Remote Repository에서 가져온 내용들을 병합(merge)하기 전에 병합을 할지 말지 확인을 할 수 있다.

pull은 무엇일까?

- pull은 Remote Repository에 있는 변경 사항들을 Local Repository로 가져와 병합을 수행한다. **fetch 명령어와 다르게 pull 명령어는 Local Repository에 변경 내용을 병합하여 저장한다.** 확인을 거치지 않고 무조건 병합을 진행하기 때문에 충돌이 일어날 수도 있다.

결론 - **fetch 후 pull 하는 것이 좋다!**
