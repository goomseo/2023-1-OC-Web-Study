# GDSC 기초 웹 스터디 WIL - Week 3

(원문 URL: [GDSC 기초 웹 스터디 3주차 WIL - velog](https://velog.io/@goomseo/GDSC-%EA%B8%B0%EC%B4%88-%EC%9B%B9-%EC%8A%A4%ED%84%B0%EB%94%94-WIL-Week-3))

# git과 github을 이용한 협업 맛보기

강사님이 작성해주신 과제 설명을 보고 차근차근 따라하여 성공적으로 과제를 수행하긴 하였지만, 원리를 모른 채로 넘어가질 못하는 성격이라 구체적인 원리는 시험이 끝나면 한 번 더 자세히 공부해야 할 것 같다. 

아래는 과제를 수행한 절차이다.

## Remote Repository를 fork 해오기
![](https://velog.velcdn.com/images/goomseo/post/f5a0407c-60a3-4ead-b862-56553cbd9854/image.png)
특정 Remote Repository를 fork 하게 되면 자신의 Remote Repository로 복사할 수 있다. 위 사진의 우측 상단을 보면 Fork 버튼이 있다. 이 버튼을 클릭하여 자신의 원격 저장소로 해당 레포지토리를 fork 해올 수 있다.

## Remote Repository를 clone 하기
이제 fork 해온 remote repository를 로컬로 불러오고 싶다. 이럴 때 사용할 수 있는 명령어가 git clone이다. 터미널에서 **git clone [repo url]** 을 입력하여 원격 저장소를 로컬로 복제할 수 있다.

fork와 clone 둘 다 원격 저장소를 복제하는 것인데, 어떤 차이가 있는 것일까? fork는 원격 저장소를 또다른 원격 저장소로 복제하는 것이고, clone은 로컬로 복제하는 것이다. 즉 복제를 하게 되는 위치에 차이가 있는 것이다. 아래 사진을 참고하도록 하자.

![](https://dejavuhyo.github.io/assets/img/2021-03-15-difference-between-git-clone-and-git-fork/git-clone-and-git-fork.png)
(이미지 출처 - [클릭](https://dejavuhyo.github.io/posts/difference-between-git-clone-and-git-fork/))

## 로컬에서 branch 생성 후 폴더 및 파일 추가
터미널에서 git checkout -b [branch name]을 입력하여 브랜치를 생성한 후 해당 브랜치로 위치를 이동하였다.

터미널에서 mkdir 명령어를 통해 복제해 온 레포지토리에 폴더를 생성하고, VSC에서 해당 폴더를 open하여 README.md 파일을 생성한 후 내용을 입력하였다.
![](https://velog.velcdn.com/images/goomseo/post/1587a25b-27f7-40ae-b494-93fd0c0f0eb8/image.png)

## Remote Repository로 push하기
터미널에서 git add .을 입력하여 발생시킨 변화를 Staging Area로 이동시킨 다음 git commit -m [commit message]명령어를 이용해 Local Repository로 commit을 함과 동시에 어떤 내용을 commit 하였는지 메세지를 입력하였다. 마지막으로 git push origin [branch name] 명령어를 통해 나의 원격 레포지토리로 push 해주었다.

이 때 commit message의 형식을 지키지 않아 강사님께서 커멘트를 남겨주셨다.
나는 [이 글](https://velog.io/@archivvonjang/Git-Commit-Message-Convention)을 보고 commit message convention에 대해서 학습하였다.

아래와 같이 브랜치가 두 개가 된 것을 확인할 수 있다.
![](https://velog.velcdn.com/images/goomseo/post/170d7d26-dea0-472a-ae8a-86680eec180f/image.png)

## Central Repository로 PR하기
이제 변경한 내용을 원본 레포지토리에 Pull Request(PR)을 보내야 한다.
![](https://velog.velcdn.com/images/goomseo/post/346d654e-8e75-46c9-8f85-76b5618317c2/image.png)
(스크린샷을 촬영한 시점에는 이미 pr을 한 상태라 원본 레포지토리와 차이가 없어 위와 같은 메세지가 뜬다.)

어떤 레포지토리에서(from)에서 어떤 레포지토리로(to) pull을 요청하는지 확인한 다음 Create pull request를 누르면 pr이 완료된다.

![](https://velog.velcdn.com/images/goomseo/post/9c2c8c58-72dc-4d41-983a-61c466b27fca/image.png)

정상적으로 pr이 완료된 모습이다.

(작성 : 홍익대 컴퓨터공학과 2학년 구민서)
