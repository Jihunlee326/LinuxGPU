#####
Week2. Linux 개발환경 세팅
#####


[GIT]
  1. VCS(Version Control System)의 일종  
  2. GIT != Github  
    - git은 버전컨트롤시스템  
    - github은 git 기반의 오픈소스 code 저장소  
  3. distibuted version control system(git) <=> centralized version control system  
  4. master branch(=main) > develop  
  5. 명령어  
    1) git remote -V : orgin = main 주소  
    2) push : 내가 만든걸 올린다.   
    3) git pull origin master : origin의 remote 저장소에서 master 브랜치를 가져와 합친다.  
    4) git clone 한 경로가 origin이 되고 제일 중요한 branch는 master. 
    5) git status : 상태 보기  
    6) git add <파일> : 수정한걸 추가, 아직 commit 전  
    7) git commit -am "<메세지>" : 실제로 추가시킴, 메세지로 메모할 수 있음  
    8) git log : commit log를 본다  
    9) git push origin master : origin으로 master branch를 업데이트 시킴  
                              : local에서 변경한 후에 push를 해야 저장소가 업데이트 됌  
   10) git checkout <경로> : <경로> 밑을 모두 commit으로 맞춤, 마지막 수정 전 내용으로 돌아갈 수 있음  
   11) git diff : 변경내역을 출력해줌  
   
     
[VIM]
  1. 터미널에 쓸수 있는 텍스트 에디터  
  2. 커스타마이징에 굉장히 좋음  
  3. 세팅 파일 : ~/.vimrc  
  4. 4가지 모드가 존재함  
    1) Normal 모드(훌는 모드), esc로 활성화  
    2) Visual 모드(텍스트 선태 모드) : 드래그르 하여 수정학 싶으 부분을 선택하는 모드  
       노말모드 v, shift-v, ctrl-v 로 활성화  
    3) insert 모드 : i, o, a, s, 등으로 활성화  
       다시 평소모드로 가려면 esc  
    4) Ex 모드 : 커맨드 모드  
       >> 노말 모드에서 , / ? 로 활성화  
       >> :w 저장. 
       >> :q vim 종료. 
       >> :wq 저장하고 vim 종료. 
       >> :q! 저장안하고 강제 종료. 
       >> :23 23번째 줄로 이동. 
       >> /jihun jihun이라는 단어를 찾는다, n으로 다음, N으로 이전.  
  5. h, j, k ,l : 좌/하/상/우 방향키  
  
    
    
    
