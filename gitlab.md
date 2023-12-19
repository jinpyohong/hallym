# Git 실습
## GitHub에 Remote Repository 생성하고 Clone하기
## 혼자서 Basic Git commands 실습
내 LR가 어떤 RR과 연결되었는지 알아보자.

    git remote -v

README.md 파일을 수정하자. 그리고 간단한 Python code 파일 simple.py를 만든다. 현재의 git 상태를 알아보자

    git status


- diff
- status/log
- remote
- Add/Commit/Push/Pull
## 
Desktop과 notebook 등 2개 이상의 컴퓨터에서 프로젝트를 수행할 때 각각 cloning해서 작업할 수 있다. 

일반적으로, 하나의 RR를 가지고 여러개의 LR를 cloning해서 분산 작업하게 되면, repository 마다 다른 변경사항(commit)이 발생할 수 있다. 
- merge: 이 변경 사항들은 결국 RR에 주의깊게 반영되어야 하며 변경사항들은 **merge** 되어야 한다.
- merge conflict: 만일 같은 파일 속에서 서로 다른 변경이 이루어졌다면 merge할 때 **conflict**가 발생되어 merge가 fail된다. 
- conflict의 해결: 두개의 변경사항을 분석하여 어떤 것을 반영할지는 user 책임이다. Conflict를 해결하면 비로서 merge할 수 있다.