---
title:  "[Github] git pull"
date:   2023-02-16
categories: [study]
tags: [github]
---
<br>

### ☝️ git pull 첫번째 단계!

협업을 위해 파일을 공유해야 하는데 서로에게 기존 소스파일이 없다면?

첫번째로 해야할일은 기존 소스를 다운받는것이다.
새로운 작업폴더의 터미널에 아래와 같이 입력해보자
```powershell
git clone 원격저장소주소
```
_▲ 다만 그 팀원의 아이디를 collaborators 메뉴에 등록해야 협업이 가능함_

<br>

### ✌️ git pull 두번째 단계!
그렇지만 우리는 아직 마음대로 push를 할 수 없다...

예를들어... 팀원이 새로운 파일을 만들어 commit + push을 하고, 나또한 새로운 파일을 만들어 동일하게 진행해 주면!!!!

<br>

에러남 ㅎㅎ

<br>

이유는 `원격저장소와 로컬저장소의 내용이 다르다면 로컬저장소에서 push가 안되기 때문이다.`   

그렇다면 우리는 어떻게 협업을 해야할까?

<br>

### 👌git pull 세번째 단계!
답은 `git pull` 을 이용하면 쉽게 해결할 수 있다.

```powershell
git pull 원격저장소주소
```

▲ 원격저장소에 있던 모든 브랜치 내용을 로컬저장소에 가져와 합치라는 뜻이다.

<br>

#### 📌 Tip!
git pull 명령어는 git fetch + git merge 의 축약어!!

git pull을 입력하면 자동으로 git fetch + git merge를 해준다.   
git fetch = 원격저장소에 있는 commit 중에 로컬에 없는 신규를 가져와라.   
git merge = 그걸 합쳐라 
