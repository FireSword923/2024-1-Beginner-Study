1주차 스터디에서 배운 것
================
## 1. github란?
* 자신의 컴퓨터에 git을 설치하면 자신의 컴퓨터에 저장된 데이터들을 gitgub같은 사이트와 연동이 되며, 이렇게 자신의 레포지토리에 들어있는 작업물을 github의 레포지토리로 보내 다른 개발자들과 공유할 수 있게 된다.

## 2. git과 VSCode를 이용한 github 사용법
* 컴퓨터 내에서 폴더를 만든 후 VSCode에서 폴더를 열고 Git bash 터미널에 **git init**을 입력해 해당 폴더에 .git 폴더를 만들어 레포지토리를 만들고, 

    **git add <파일 이름>** (**git .** 을 입력 시 폴더 내 모든 것을 대상)

을 입력해 원하는 파일을 관리 대상으로 추가한다. 추가한 파일을 레포지토리로 옮기려면 
    
    **git commit** 

을 입력하면 되며, 여기에 부연 설명(커밋 메세지)을 쓰고 싶으면 

    **git commit -m <메세지>**

를 입력하면 된다. 가독성을 위해 feat, refactor, fix, chore, dox, test 등등의 type을 앞에 써두는 게 좋다.

여기까지는 로컬에서의 관리이고, 파일들을 github에 올리기 위해선 일단 github사이트에 레포지토리를 생성 후 
    
    git remote add origin <github 레포지토리의 주소.git>
    git branch -M main
    git push -u origin main

를 입력하면 로컬 레포지토리와 github 레포지토리가 서로 연동되며, github로 파일이 올라가게 된다. 
이후 기존 파일을 수정해서 다시 올리려면

    git add <파일 이름>** (**git .** 을 입력 시 폴더 내 모든 것을 대상)
    git commit(-m <메세지>)

로 로컬에서의 관리 이후

    git push origin main
    
를 입력하면 github로 파일이 수정돼 올라가게 된다.

## 3. 마크다운 문법 일부
들여쓰기, 제목이나 머리말 쓰는 법, 강조하기 등 일부 문법을 알게 됐다.