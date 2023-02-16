---
title:  "[Github] git request"
date:   2023-02-16
categories: [study]
tags: [github]
---
<br>

### 😸 협업시 새로운 branch 만들기

협업을 하다가 새로운 기능을 추가하고 싶을때, 혹은 협업인원이 많을때 새로운 branch를 생성하여 작업하는것이 좋다!

(방법)   
1. github 에서 브랜치를 직접 생성
2. 로컬에서 만든 브랜치를 push!

<br>

- 첫번째 방법

    ![img1](https://user-images.githubusercontent.com/115879536/219382549-13187858-3fc5-4c89-892c-c5d8ccd55558.png)
    
    ▲ main 브랜치 버튼을 누르면 새로운 브런치를 만들거나 바꿀수있다.

- 두번째 방법   

    ```powershell
    git branch newbranch
    git switch newbranch
    git add .
    git commit -m '새로운 branch 생성'    
    ```
    
    ▲ 이렇게 새로운 branch를 만들고 commit을 해준다.   
    
    그런다음에 push를 하면 되겠죠?

    ```powershell
    git push 원격저장소주소 로컬브랜치명
    ```   

    <strong>(주의!!)</strong>   
    ▲ `git push 원격저장소주소 로컬브랜치명` = 특정 로컬저장소 브랜치 -> 원격저장소    
    ▲ `git push 원격저장소주소` = 모든 로컬저장소 -> 원격저장소

<br>

### 😸 git request!

앞서 만든 새로운 브랜치에 기능을 추가하고 수정했다면 merge를 통해 git push !!!를 하면 참 좋을텐데 실상은 협업자와 검토를 해야한다💦   

그래서 해야할 것은 <strong>git request</strong> 

![image](https://user-images.githubusercontent.com/115879536/219398228-051568d3-39b3-49f5-a05a-4cc8d6f9f3fc.png)

▲ `pull request` 를 누르면 `new pull request` 가 생성된다.

![image](https://user-images.githubusercontent.com/115879536/219399497-9e1b2fe1-04e1-404c-943a-ad7fd8260ea8.png)

▲ 어떤 브랜치를 어디에 합칠것인지 선택하고 request를 진행하면 된당.

<br>

### 😸 request merge 옵션!

이렇게 착착 진행을 한다면 협업자들과 함께 코드를 리뷰하는(댓글기능)등을 이용해 검토 및 리뷰가 가능합니다:)

자, 리뷰가 잘 이루어 졌다면 마지막으로 merge를 해야겠지?   

아래의 옵션에 대해서 알아 보자

![image](https://user-images.githubusercontent.com/115879536/219400176-f7868470-dbd1-4254-a677-8e1ee2fda3ee.png)

<br>

#### 1. creat a merge commit

![image](https://user-images.githubusercontent.com/115879536/219402427-2b97eeb8-1bfa-4da5-a863-3467e5930413.png)


▲ 새로운 merge commit을 하나 생성해주는 3-way merge를 실행해줍니다. 

- main 브랜치 조회시 합쳐진 브랜치의 commit 내역도 전부 나옴  

- 터미널에 git log --oneline --graph 해보면 합쳐진 브랜치도 그림으로 나옴 

- 그래서 commit 내역이 많으면 복잡하고 더러워보일 수 있습니다. 

<br>

#### 2. squash and merge

![image](https://user-images.githubusercontent.com/115879536/219403433-4b909a51-2636-41f3-95a6-4ed4173bcbd3.png)

▲ squash and merge 하면 

- 합쳐질 브랜치의 commit 내역을 하나로 합쳐서 main 브랜치에 신규 commit을 생성해줍니다.

- git log --oneline --graph 해보면 합쳐진 브랜치 안나옴 

- commit을 하나로 합쳐서 main 브랜치로 순간이동 시켜주는 행위라 사람들이 깔끔하다고 좋아합니다. 

<br>

### 3. rebase and merge

![image](https://user-images.githubusercontent.com/115879536/219404465-6f4d1d98-7f4f-471a-bf6f-4d7b089ba89a.png)

▲ rebase and merge 하면 

- 합쳐질 브랜치를 main 브랜치 최신 commit으로 rebase하고나서 fast-forward merge 비슷한걸 해줍니다.

- 결과는 squash and merge와 비슷한데 합쳐질 브랜치의 commit 내역이 전부 보존됩니다. 

- 애도 git log --oneline --graph 해보면 합쳐진 브랜치 안나옴

🔺(참고)   
원격저장소의 commit 내역을 과거로 돌리고 싶을때   
`git reset --hard` `git push -f` 를 하면 가능하긴 하지만   
해당 브랜치에서 공동작업중인 협업자들이 모두 영향받기 때문에 안하는게 좋다...!!

