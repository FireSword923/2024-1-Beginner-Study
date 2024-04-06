3주차 스터디에서 배운 것
===============
# commit id
깃 허브를 사용한다면, 여러 번의 commit을 하게 된다. 따라서 각각의 commit을 식별할 필요가 있으므로 40개의 16진수 숫자들로 이루어진 고유 식별 번호다.

2주차에서 배운 **Merge**에서 옵션을 **Rebase and merge**로 골랐다면 이 **commit id**가 변한다고 언급이 됐었다.

# 명령어 - "git log"
## 사용법
명령어 입력칸에

    git log
를 입력 시 터미널에 commit 기록을 최신 순으로 보여준다. 

이 경우 
1. commit id 전부 다 
2. 누가 언제 커밋했는지 
3. 커밋 메세지

이 세 개를 보여주기 떄문에 커밋 하나 보여주는 데도 여러 줄을 사용한다. 만약 이렇게까지 자세하게 보고 싶지 않고 커밋 기록만 빠르게 보고 싶으면 

    git log --oneline
를 입력하면 
1. commit id를 앞에서 7개까지
2. 커밋 메세지

이 두 개만 보여준다.

## git log 상태에서 탈출하기
"--oneline" 옵션을 썼든 말든 커밋 기록을 확인했다면, **터미널에 'q'를 눌러야만 다른 명령어를 입력할 수 있게 된다.**

 'q'를 누르지 않으면 명령어를 입력하려고 키보드를 두들겨봤자 의도하지 않은 기능들만 작동하므로 확인할 거 다 했으면 'q'를 꾹 누르자.

# HEAD
**HEAD**는 현재 작업 중인 위치를 가리킨다.

현재 작업중인 브랜치의 가장 최근 **commit**을 가리키며, 새로운 **commit**이 생기면 **HEAD**는 그 **commit**으로 변경된다.

# 명령어 - "git status"
세 가지 상태에 따라 파일을 분류하여 확인하는 명령어. 

각 상태별로 아래와 같이 터미널에 표시된다.


## git에서 작업중인 폴더에 있는 파일 중 "git add" 명령어를 안 쓴 경우

    Untracked files:
        (use ""git add <file>..." to include in what will be committed)
            <해당 파일>

## "git add" 명령어를 써서 stage 상태가 됐을 경우

    changes to be comitted:
        (use ""git restore --staged <file>..." to unstage)
            new file: <해당 파일>

## 어떤 파일을 수정했을 경우

    Changes not staged for commit:
        (use ""git add <file>..." to include in what will be committed)
        (use ""git restore --staged <file>..." to unstage)
            modified: <해당 파일>
참고로 어떤 파일을 수정할 경우, **Staging area**에는 수정 전 파일이, **Working directory**에는 수정 된 파일이 존재한다. 

"git add"를 사용해서 **Staging area**로 보내는 것은, **<span style="color:Yellow">파일을 이동시키는 게 아니라 복사하는 것**이기 때문에, 파일을 수정할 경우 **Staging area**쪽 파일은 그대로고 **Working directory**에 있는 것만 수정되는 것이다.

# 명령어 - "git commit --ammend"
가장 최근의 commit의 메세지를 바꾸고 싶을 때 사용하는 명령어.

    git commit --amend
입력 시 **vim**이라는 텍스트 편집기로 들어가서 commit 메세지를 수정하게 된다.

단 commit id가 바뀌므로 다른 사람이 작업 기반으로 삼고 있는 commit을 amend하면 안 된다.

만약 **vim**을 쓰기 싫다면,

    git commit --amend -m "커밋 메세지"
를 입력하면 되며, 메세지를 수정하지 않고 commit만 수정하고 싶다면

    git commit --amend --no-edit
를 입력하면 된다.

# 명령어 - "git reset <commit>"
commit을 제거하는 데 사용하는데, 총 3가지 옵션이 존재한다.

    git reset '--option' "<commit id>"
로 입력한다. 따움표 안에 있는 문자들을 바꿔서 써야 한다.

## git reset --soft "<commit id>"
commit만 취소하는 것. **Repo**에 있던 변경 사항이 **Staging Area**로 되돌아간다.

## git reset --mixed "<commit id>"
**reset**의 디폴트 설정. **Repo**에 있던 변경 사항이 **Working directory**로 되돌아간다.

## git reset --hard "<commit id>"
**Repo**에 있던 변경 사항을 모두 제거해버린다.

# 명령어 - "git revert <commit id>"
reset이랑 비슷하지만, commit을 제거하지 않으며, 이전 commit의 내용들을 새로운 commit에 기록한다. 

commit을 제거하지 않는다는 점에서 **reset**보다 안전하다.

commit 메세지를 수정하기 위해 편집기로 진입을 하게 되는데, 딱히 수정할 게 없다면

    git revert --no-deit <commit id>
를 입력하면 된다.

revert 내용을 commit하지 않고 **Staging area**에 올려두는 것 까지만 하고 싶다면

    git revert --no-commit <commit id>
를 입력하면 된다.

