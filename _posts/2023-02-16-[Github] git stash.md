---
title:  "[Github] git stash"
date:   2023-02-16
categories: [study]
tags: [github]
---
<br>

### 😸 git stash 란?

`git stash` 란 코드 임시보관소(?) 같은 곳이다.   

```html
aaaaaaaaaaaaa <!-- 기존 코드 -->
추가한 코드 ~! 
```
🔺 위와 같은 상황에서 추가한 코드를 잠깐 삭제하고 싶을때 `git stash` 명령어를 사용할 수 있다!


<br>

### 😸 git stash 적용해보기

```powershell
git stash
```

▲ 요 명령어를 입력하면 아까 "추가한 코드~!" 는 잠깐 다른 공간에 보관되며 파일들이 최근 commit 상태로 돌아가 "aaaa~"만 남게된다.   

- `git stash` 는 여러번 할 수 있다!
- staging 된 것이든 아니든 추적중인 파일을 다 이동된다고 한다
- 새로 만든 파일인데 staging 안되었다면 이동안된다.

<br>

```powershell
git stash save "코드 임시보관 함당~"
```

▲ 요런식으로 메모도 입력할 수 있다

```powershell
git stash list
```
▲ 현재 stash 되어 있는 코드 목록을 전부 출력해주는 명령어

<br>

### 🙂 staging 코드 다시 불러오기

```powershell
git stash pop
```

▲ 임시보관 했던 코드를 다시 불러올 수 있다.   

- git stash 했던 코드가 여러개라면 가장 최근에 보관한 코드먼저 불러온다.
- stash 뒤에 붙은 숫자를 이용해 특정 코드만 불러오는것도 가능!   

<br>

#### 📌 기타 명령어

```powershell
git stash drop 삭제할id 
git stash clear 
```
1. 특정 stash만을 삭제한다.
1. 모든 stash를 삭제한다.   
_삭제할id 는 stash list 에서 보이는 stash 뒤에붙은 숫자!_

```powershell
git stash -p
```
▲ 전체 말고 일부 코드만 git stash 하고 싶다면 위의 명령어를 사용

<br>

#### 📌 주의사항

굳이 필요없는 코드를 주석처리 하지 않고 stash 처리하는 이유는...!!    
주석처리된 코드는 commit에 반영되기 떄문에 기록이 남아 그것이 더러워질 수 있다고 합니다...!