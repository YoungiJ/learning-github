# **GIT1_lecture note**

## ***About GIT***
- **Git** 은 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 해당 파일들의 작업을 조율하기 위한 분산 버전 관리 시스템이다
- 분산 버전 관리 시스템으로서 빠른 수행 속도에 중점을 두고 있는 것이 특징이며 데이터 무결성, 분산, 비선형 워크플로를 지원한다.
- 깃은 많은 GUI를 지원하는 것이 특징이다. 현재 소스트리, GitHub Desktop 등의 여러 GUI를 사용할 수 있다.

## ***Changes vs Snapshot*** 
 **Changes >**  base버전에 수정본을 누적시키기 때문에 각각 file의 version이 다름  
 **Snapshot>** 각각의 버전에서 file의 전체를 캡쳐함
 
 ## ***용어*** 
- local-개인 컴퓨터  
- centrailzed-중앙서버에서 여러 버전 기록하다가 local이 요청해서 기록된 버젼을 받을 수 있다  
- distributed-각각의 로컬 컴퓨터가 서버의 중앙 시스템을 관리(데이터베이스를 통째로 관리=>필요할때 merge할수 있고 서버가 다운돼도 복사할 수 있음)  

- modified(수정된 상태)  
- staged area(준비상태)  
- commited(버전 기록)  
<img width="386" alt="git3" src="https://user-images.githubusercontent.com/104750081/194887624-76ea7416-7e38-4873-9e7a-ec093f929d3f.png">

 ## ***깃설치 및 기본 설정***
 1)system level : 모든 이용자,레포에 영향을 줌 관리권한이 있어야함  
```sh 
$ file:/gitconfig  
```
2)global level --global option 유저의 모든 레포에 영향  
```sh 
$ file:/.config/git/config  
```
3)local level --local option  

* system -> global-> local 순으로 덮어쓸 수 있음  
```sh 
$ git config --list > 셋팅된 config 리스트가 나옴  
$ git config --list--show-origin > 어떤 레벨에서 config이 되었는지까지 확인  
$  git config --global init.defaultBranch main > branch이름을 main으로 바꿈   
```
---------------------------------------------
## ***GIT 실전***  
```sh
$ git init -작업하는 디렉토리에 .git이 생성됨
$ ls -lha  -a> 숨겨진 파일이나 디렉토리 출력
$ git status -> commit 정보가 나옴
             -> untracted files>깃이 트래킹하지 않은 작업했던 파일들이 있음

```
* add를 안해주면 내용을 수정했지만 그 상태로 커밋(버전화) 
```sh
$ git add <file_name> - track되게 하기
$ git add. -모든 파일을 한꺼번에 stage area로 올려주자
$ git rm--cached <file_name> -파일시스템이 아니라 git 의 stage area에서 파일 삭제됨 >untracted 로 바뀌게 됨
```
* 디렉토리에서 삭제하는게 아니라 cached를 하면 stage에서만 제거됨
<img width="371" alt="git5" src="https://user-images.githubusercontent.com/104750081/194887598-378a6060-ed48-4fe4-87b5-847df139132c.png">


<img width="388" alt="git4" src="https://user-images.githubusercontent.com/104750081/194887704-63afbeaa-babc-44b7-9b6c-a86a67c99770.png">


```sh
$ nano .gitignore -명령어가 아니라 gitignore라는 파일을 만들어야함
- nano안에서 파일이름 입력하면 untracked에도 안뜨게 됨
$ git commit -m "commit message" -진짜 커밋하기(snapshot찍기)
$ git log -기록 보기
$//nothing to commit ,working tree clean  > 작업하는 공간과 다를게 없다
$git branch -브랜치 이름을 확인하고 싶으면 
$git branch -m master main - 브랜치 이름을 master에서 main 으로 바꾸고 싶을때 
```
<img width="371" alt="git5" src="https://user-images.githubusercontent.com/104750081/194887812-bd2fbaca-018a-4309-a21f-7974bc65bbf0.png">


<img width="353" alt="git2" src="https://user-images.githubusercontent.com/104750081/194887186-f64f3b49-ed35-496f-ba00-972a7cd10eca.png">



