---
title:  "[Github] git push"
date:   2023-02-16
categories: [study]
tags: [github]
---
### 📌 Repository 란?
<br>
강의를 시작하기 전, repository의 개념을 정리하고 넘어가자!   
`repository`란 git이라는 친구가 파일버전을 저장두는 장소고, 로컬 작업폴더를 보면 `.git`이라는 폴더가 바로 repository이다. 
<br>
<br>
하지만, 로컬폴더이다 보니까 폴더가 날아가거나 컴퓨터가 고장나는 불상사가 생긴다면 나의 repository는 0에 수렴하게 된다.
그래서 github라는 `온라인 repository` (aka 원격저장소) 를 사용하는 것이다 :)
<br>
<br>
<br>

### ✏️ git push 해보기 
<br>

1. 작업폴더를 만들어 터미널을 열어서 `git init` 을 한다.   
-> 그것이 로컬 repository 생성 방법이다.   

2. 파일을 생성하여 commit을 해준다.   

3. 로컬저장소 -> 원격저장소 로 업로드 하기   
    ```powershell
    git push -u 원격저장소주소 main
    ```

    ▲ `-u` 옵션은 방금 입력한 주소(원격저장소주소)를 기억해두라는 뜻이라서, 다음 push를 할떄는 주소를 길게 입력하지 않고 `git push` 만 입력해도 된다.

<br>
<br>

#### Tip 원격저장소주소 매번 입력하는게 귀찮을때!
매번 원격저장소주소를 길게 입력하는게 귀찮을때는 아래의 방법을 통해 주소를 변수에 저장하여 사용할 수 있다!    
```powershell
git remote add origin(변수명) https://원격저장소주소.git
```
▲ `remote` 를 통해 `origin` 이라는 변수명에 원격저장소주소를 저장한것이다. 

```powershell
git push -u origin main
```
▲ 요롷게 간단 + 짧게 push가 가능해진다! 

<br>

### 📌 팁정리
- `-u` 는 방금입력한 주소를 기억해준다!
- `remote` 를 이용해 주소를 변수에 저장하여 사용할 수 있다!
- 변수목록을 살펴보고 싶을때는 `git remote -v` 로 확인할 수 있다.