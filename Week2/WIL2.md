2주차 스터디에서 배운 것
================
## Fork
Github에서는 다른 사용자의 레포지토리를 자신의 계정에 새로운 레포지토리를 만들고 그 곳에 복사하여 독립적으로 수정하고 관리하는 것을 뜻한다.

### 사용법
누군가의 레포지토리로 들어가면 우측 상단에 Fork 버튼이 있다. 그것을 클릭 시 새로운 Fork를 만드는 창으로 이동하는데, 레포지토리 이름을 정한 후 **Create fork** 를 클릭하면 복사가 된다.

### 삭제법
삭제하고 싶을 경우 해당 레포지토리로 들어간 후, 좌측 상단쪽에 있는 여러 개의 탭 중에서 **Settings**를 클릭한다. 그리고 밑으로 쭉 스크롤 하면 Danger Zone이라는 영역이 나오는데, 여기서 **<span style="color:red">Delete this repository**를 클릭한다.

총 2번의 확인 메세지를 받은 후 박스에 **"<해당 레포지토리의 주소>"** 를 입력하고, 마지막으로 github 계정의 비밀 번호를 입력하면 Fork를 이용해 복사한 레포지토리의 삭제가 완료된다.

## Star
크롬이나 마이크로소프트 엣지같은 웹 브라우저는
**사이트 북마크(즐겨찾기)** 표시를 별(star) 모양으로 표시한다. github 에서도 그와 마찬가지로, **star**란 레포지토리를 **북마크**하는 것이다.

### 사용법
누군가의 레포지토리로 들어가면 우측 상단에 **Star**라는 버튼이 있다. 클릭 한 후 자신의 github 프로필로 가서 좌측 상단의 **Stars**를 클릭하면 북마크해둔 레포지토리를 확인할 수 있다.

## Issue
레포지토리에서 작업 계획이나 토론, 수정 사항같이 남들에게 **메세지**를 남겨 놓는 것이다.

**공지사항**과 조금 비슷하다고 볼 수 있다.

## Branch
**Branch**는 나뭇가지라는 뜻이다. 

github에서는 큰 몸통으로 부터 뻗어나간, 분기된 부분이라는 뜻으로 쓰인다. 

다시 말해, **Branch**를 새로 생성한다는 것은, **main Branch**로부터 분기되어 생성되는 **별도의 작업 공간**을 만들겠다는 것이다.

**Fork**와의 차이점이라면 **Fork**는 레포지토리를 새로 만들지만, **Branch**는 현재 사용중인 레포지토리에 **Branch**라는 것이 생성된다.

### 사용법
일단 git과 연결된 터미널을 열어야 한다. 이후 터미널에 

    git branch "<Branch 이름>"
을 입력 해 **Branch**를 생성하고, 

    git checkout "<Branch 이름>"
를 입력하면 해당 **Branch**로 이동한다.

위 두 과정을 한 번에 하기 위해선

    git checkout -b "<새로 만들 Branch 이름>"
를 입력하면 생성과 동시에 해당 **Branch**로 이동한다.

**Branch**의 이름은 **“ ” type/ - <issue 번호> <간략한 설명>** 으로 하는 것이 좋다. type에는 커밋 메세지의 type에서 처럼 dox 등등이 들어갈 수 있다.

### 삭제법
터미널에 
        
    git branc -D "<Branch 이름>"
을 입력하면 해당 **Branch**가 삭제된다.

## Pull Request
분기된 **Branch**들을 병합하기 위한 과정. Merge를 통해 병합하기 전, 다른 **Branch**와 (main Branch 포함) 충돌하는 부분이 없는 지 확인하는 과정이다.

### 사용법
레포지토리로 들어간 후, 좌측 상단쪽에 있는 여러 개의 탭 중에서 **Pull requests**를 클릭한다. 이후 **Comparing changes**에서 **base Branch**와 **compare Branch**를 설정한 후, **Create pull request**버튼을 클릭하면 새로운 주소로 이동한다. 제목과 설명을 쓴 후 (이 때의 제목도 type을 적어두는 것이 좋다.), **Create pull request**를 클릭하면 충돌 여부를 **<span style="color:green">초록색** 테두리로 둘러쌓인 공간에 표시해준다.

## Merge
분기된 **Branch**들을 병합하는 마지막 부분이다.

**Pull Request(PR)** 결과, 충돌 부분이 없었다면 **Merge pull request** 버튼을 클릭한다. 3가지 옵션이 있는데,

### Create a merge commit
두 **Branch**를 공통 부모로 하는 새로운 **커밋**을 만들고 그 **커밋**에 앞선 PR에서 설정한 **compare Branch**에 있던 커밋 메세지들을 **base Branch**에 그대로 추가한 후, 두 **Branch**가 **base Branch**로 병합된다.

커밋 메세지들을 더 이상 남길 필요가 없다면 쓸 필요 없는 옵션이다.

### Squash and merge
**Compare Branch**의 커밋 메세지들을 남기지 않고 두 **Branch**가 **base Branch**로 병합된다.

### Rebase and merge
**Merge Commit**에서는 하나의 커밋에 **compare Branch**의 커밋 메세지들을 전부 옮겨넣는 것이라면, 이것은 커밋 메세지 개수만큼 새로운 커밋이 생기며, 그 커밋들에 메세지가 옮겨진다.

커밋 ID가 변경되며, 충돌 가능성이 높은 편이다.

느낀점
=======================
이번에는 레포지토리를 다루는 여러가지 방법을 배웠다. 본인의 작업은 물론 다른 사람의 작업물을 이용하는 것도 조금은 배웠기 때문에 앞으로 깃허브를 더 효과적으로 사용할 수 있을 것이 기대된다. 

근데 브랜치라는걸 쓰면서 은근히 불편한 점들이 있었다. main 브랜치로 이동하려는데 분명 커밋해놨던 README를 다시 커밋하라고 한다거나, 처음 실습했을 땐 README를 실수로 Week1 폴더에 생성했더니 이유를 잘 모르겠는 문제점들이 계속 생겨서 결국 전부 삭제하고 실습을 Issue 생성을 제외한 모든걸 다시 해야 했다. 브랜치를 쓸 땐 귀찮은 일들이 꽤 많이 생길 것 같다는 안 좋은 예감이 든다.