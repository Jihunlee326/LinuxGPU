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

[Python]
  1. Script 언어
  2. 대부분의 딥러닝 프레임워크에서 사용
  3. C 계열같이 컴파일 방식이 아닌 언어
  4. 기능상 차익 많지는 않지만 요즘 추세는 Python3
  5. print "hello" != print("hello")
  * 버전 xx.xx.xx = major.minor.patch
  * which : 사용하는 명령어(바이너리)의 위치를 알려줌
  * ubuntu에서 py3를 지우면 화면이 안뜸..  
  * python [tap][tap] : 가능한 python을 시작하는 명령어들  
  6. 3rd Party 라이브러리 설치하기  
    1) pip install [라이브버리] --> pip는 apt같은 파이썬 패키지 관리 프로그램
    2) 하지만 아무거나 마구 설치하면 라이브러리들끼리 꼬여버림  
    3) 파이썬 가상환경을 사용하자!
      - virtualenv  
      - virtualenv [name]  
      - soruce activate [name] ==> MAC에서는 "source [name]/bin/activate"  명령어로 가상환경 활성화  
      - soruce deactivate  ==> MAX에서는 "deactivate" 명령어로 가상환경 종료  
      - rm -rf pth  
      - conda 가상환경은 이미 많은것들이 설치되어 있는 상태  
  7. Local에서 개발하기  
    1) pycharm : python 개발을 위한 가장 강력한 IDE  
               : 편함, 자동완성, 입문이 쉬움  
               : 유료, 복잡한 파이썬 개발상황에선 어려울 수 있음  
    2) sublime Text / ATOM : 단순 code 편집기  
                           : 무료, 수많은 플러그인을 통해서 리팩토링 가능  
                           : 커스터마이너징이 많아서 세팅이 어려울 수 있음  
                           : ATOM은 생각보다 무거움  
  8. Server에서 개발하기
    1) CLI(Command Line Interface)가 강제되는 상황  
    2) CLI가 가장 좋은 방법이지만, 너무 힘들면 다른 옵션이 있음  
      - Jupyter Notebook  
      - X forwarding  
      - Pycharm, Atom, Sublime Text의 원격 편집  
    3) 순수 CLI를 이용하는 방법 : Tmux + VIM  
      - Terminal Multiplexer  
      - 서버에 켜놓고 꺼지지 않는 터미널  
      - 로컬에서 터미널 세션에 언제나 붙을 수 있음  
    4) TMUX
      - 손쉽게 터미널을 항상 서버에 켜놓을 수 있다.  
      $ sudo apt install tmux  # tmux 설치  
      $ tmux new -s [name]     # name 이라는 세션 생성  
      $ jupyter-notebook       # jupyter 켜놓기  
      $ wget <어떤 데이터셋.zip>  # 데이터셋 계속 받아놓기  
      $ python train.py        # 내 실험 계속 켜놓기  
      # <ctrl-b> d             # session에서 떠나기  
      $ tmux attach -t [name]  # name 라는 세션에 다시 붙기  
      # <ctrl - d > 연타        # 터미널 다 끄기하면, 세션 아예 삭제  
    
                           
  
  
    
    
    
