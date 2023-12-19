# Git 실습
## GitHub에 Remote Repository 생성하고 Clone하기
## 혼자서 Basic Git commands 실습
Desktop과 notebook 등 2개 이상의 컴퓨터에서 프로젝트를 수행할 때 각각 cloning해서 작업할 수 있다. 

이를 흉내내기 위해 컴퓨터 내에 다른 folder 안에 LR를 clone해서 실습해보가로 하자.

미리 cloning한 repository위치에서 vscode를 실행하여 folder를 연다. 

### *git bash*에서
*git bash*를 실행해서 새로운 folder 밑에 LR를 생성하자.

    git clone <remote repository>

RR의 연결 상태를 확인해 보자

    git remote -v

README.md 파일을 수정하자. 그리고 간단한 Python code 파일 simple.py를 만든다.

현재의 git 상태를 알아보자

    git status

새로운 파일을 add 하자. (이제부터 simple.py 파일은 *tracked* 된다)

    git add simple.py

그전 commit가 working directory와의 변경사항이 어떠한지 알아보자.

    git diff

Commit한다.

    git commit -a -m "add simple.py"

다시 status를 확인해 보자. 그리고 commit history를 보자.

    git log

RR에 추가된 commit들을 push하자.

    git push origin main

### vscode에서
Pull: RR에서 새로운 commit들을 가져온다.

simple.py의 code를 변경해서 commit한다.

### git bash에서
simple.py code를 다른 방식으로 변경해서 commit하고 push하자.

### vscode에서
변경된 commit을 push한다면 merge conflict가 발생하여 fail(거절)될 것이다. RR에 있는 새로운 commit을 먼저 가져와야 한다. *fetch* 하고 history, 즉 commit graph를 보자.

working tree에서 새로운 commit을 반영해서 변경하는 작업이 필요하다. *git merge* 명령으로 실행할 수 있지만, 
vscode에서는 그냥 *pull* 하는 편이 쉽다. (이미 fetch한 commit을 다시 fectch하지 않기 때문)

### Merge conflict
일반적으로, 하나의 RR를 가지고 여러개의 LR를 cloning해서 분산 작업하게 되면, repository 마다 다른 변경사항(commit)이 발생할 수 있다. 
- merge: 이 변경 사항들은 결국 RR에 주의깊게 반영되어야 하며 변경사항들은 **merge** 되어야 한다.
- merge conflict: 만일 같은 파일 속에서 서로 다른 변경이 이루어졌다면 merge할 때 **conflict**가 발생되어 merge가 fail된다. 
- conflict의 해결: 두개의 변경사항을 분석하여 어떤 것을 반영할지는 user 책임이다. Conflict를 해결하면 비로서 merge할 수 있다.

## 여러명이 협동작업하기
### GitHub에 collaborator 추가
### branch 사용하기