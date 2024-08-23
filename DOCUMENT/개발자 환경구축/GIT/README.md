<h1>GIT</h1>			

<h3>기본 명령어 </h3>

```
cmd - git init : .git 폴더 만들어짐.				
		
git status - git 상태 확인		
		
git add (t.txt) : stage area에 파일 등록		
		
git log --oneline : 로그를 한줄로 볼 수 있다.		
		
git reset --soft : commit : 취소 , working directory(add) : 있음 , stage area : 있음
   	  --mixed : commit : 취소, working directory(add) : 있음 , stage area : 없음
	  --hard : commit : 취소, working directory(add) : 없음 , stage area : 없음

git reflog
      
git merge - 충돌이 일어나면 git merge --continue(충돌 해결 후) , git abort(충돌 무시) 

git branch (확인) , git branch [newBranch], git switch/checkout [branch명]
```

<hr/>

<h3>깃허브 사이트랑 연동</h3>

```
주의 : 		
깃허브에서 readme파일을 생성하는순간 branch가 하나 만들어지게돼버림.		
로컬에서 repository를 넣을때 문제가 생김		

1. 깃 푸시 할 파일에서 git init (깃생성) 
2. 2. git add *(모든 파일 넣기)
3. git branch -M main(main을 메인 브랜치로 설정)
4. 4. git commit -m "V0.0" (버전 명 commit)
5. git remote add origin https://github.com/Maze-o/GIT-TEST.git (깃허브 사이트랑 연결)
6. git remote -v (사이트랑 연결 되었는지 확인)
7. git push origin (푸시 처음 하면 깃 푸시 셋을 하라고 나옴)
8. git push --set-upstream origin main (푸시 설정)
9. git push origin (깃허브 사이트로 푸시) 
```

<hr/>

<h3>이미 만들어져있는 깃허브 깃이랑 연동</h3>

```
1. 파일에서 git init
2. git clone https://github.com/Maze-o/GIT_TEST3.git
git push origin , git pull origin, git fetch origin
```
<hr/>

<h3>이클립스 깃허브 연동</h3>

```
올리기
1. 상단 window -> show view -> 
2. 프로젝트 우클릭 -> team -> share project
3. use or create repostiory in parent folder of project 체크 (git init)
4. Git Repositories 선택 (이클립스) -> remotes 우클릭 create remote -> Configure push 선택 create
5. URI -> 깃허브에 있는 repostiory 주소 복사붙여넣기
6. User id에는 github 닉네임 or 아이디 입력
7. passwd에는 github -> profile setting -> Developer settings -> Personal access tokens -> Tokens(classic) -> Generate new token (classic) -> Note 닉네임 설정 후 repo 선택후 Generate token 붙여넣기 Finish
 
받기

이클립스 file -> Import -> froject from git -> Clone uri

이클립스에서 브랜치 생성 후 깃허브에 커밋

프로젝트 우클릭 -> team -> switch -> new branch -> branch name에 branch 이름 입력
파일 수정 후 commit 하면 github에 새로운 branch 보임. -> 하지만 이클립스에서는 merge 불가능. 깃허브에서 merge해야함
```
