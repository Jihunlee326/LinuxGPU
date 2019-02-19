### Linux for Deep Learning 

## CONTENTS
1. Linux 배포판
2. Ubuntu 설치
3. CLI(Command Line Interface)
4. Sheel
5. Package Manager - apt

[Ubuntu]
  - Linux kernel을 포함한 배포되는 OS 중 하나
  - https://www.ubuntu.com/download/desktop
  - LTS는 2년마다 나오는 안정적인 버전
  - 딥러닝 플랫폼이 지원하는지 확인할 것
  - 영어로 설치 필수
  - 파티션 나누기 > something else
  - sda, sdb, sdc .. : 각각의 하드 단위
  - sda1, sda2, sda3 : sda 에서 나뉜 파티셔 단위
  - 파티셔 나눈 다음에 설치하는 것 추천
  - ext4 : ubuntu 기본, ntfs : 윈도우 기본
  - 우분투 설치해오기
  
[CLI]
  $ ls : 현재 디렉토리 정보  
    $ ls -al 또는 ll : 권한 탐색  
    $ ex) drwxr-xr-x 2 jihun.lee326  staff     64  2 19 20:39 ThisisDirectory  
    $ (drwx)-(rwx)-(rwx) : d는 디렉토리 r은 리드 w는 라이트 x는 execute권한  
    $ 숫자 : 바라보고 있는 디렉토리 갯수  
    $ 첫번째 : 주인꺼, 두번째 : 소유주의 그룹, 세번째 : 나머지의 권한  
    $ jihun.lee326 : 소유주  
    $ staff : 소유그룹  
  $ ssh 아이디@IP : 해당 아이피로 접속  
  $ pwd : print workning directory, 현재 내 위치 출력  
  $ cd : change directory  
    $ cd만 치면 자신의 기본 위치로 돌아옴  
  $ . : 현재위치  
  $ .. : 이전위치  
  $ tree : 트리형태로 디렉토리를 보여줌  
    $ tree -L 3 : Level을 제한해서 tree 형태로 디렉토리르 볼 수 있음  
  $ 모든명령어 --help : 해당 명령어의 사용법을 알 수 있음  
  $ find : 파일 탐색  
    $ find [대상위치] [옵션]  
    $ ex) find . -name 파일이름  
  $ clear : 화면 청소  
  $ mv [누구를] [어디로] : 파일 이동  
  $ cp [누구를] [무엇으로] : 파일 복사  
  $ mkdir [누구를] : 디렉토리 생성  
  $ rm [누구를] : 파일 삭제  
    $ rm -r : recursive 옵션임 안에 있는거 반복해서 다 지움  
  $ touch [누구를] : 빈 파일 생성(시간 갱신), 원래 있던 파일의 시간을 업데이트 할 수 있음 => linux에서는 시간 정보가 매우 중요  
  $ chown [누구:그룹] [대상] : 파일의 소유주/소유그룹 변경, change owner, (누구:그룹)한테 (대상 디렉토리)의 권한을 주는 것  
  $ chmod [어떻게] [대상] : 파일의 권한 변경  
    $ +, - 를 사용해서 권한 회수/부여  
    $ chmod -x 대상파일 : 대상파일의 x 권한을 뺏음  
    $ chmod u+r rock : rock파일의 u(user)권한에 x(execute)실행권한을 부여함  
  $ echo [무엇을] : 아무 내용인 출력  
    $ echo "HI!"  
  $ alias [이름]='[커맨드]' : 별칭 커맨드 생성  
    $ alias park='echo "I am a boy!"'  
  $ cat [누구를] : 파일 내용 출력  
  $ wget [주소] : web 주소에서 내용을 파일로 저장  
  $ grep [찾을 내용] [누구를] : 파일 내용 탐색, 찾을 내용은 텍스트임  
    $ grep -R GOLD rock1 : grep 에서는 대문자 R로 리커시브를 사용함  
  $ ps : 현재 실행중인 프로세스들을 탐색  
    $ ps -aux : 좀 더 자세하게 프로세스들을 보여줌  
  $ top : 실시간 모니터링, 윈도우즈 작업 관리자랑 비슷  
  $ kill [프로세스 id] : 프로세스 강제 종료  
  $ pipe(!!!) CLS의 꽃! : 커맨드간으 상호 작용
    $ | 커맨드를 사용해서 여러 명령어 입력  
    $ ps -aux | grep top : ps -aux의 결과 중에서 top 이라는 텍스트만 탐색  
  $ history : 사용한 명령어를 순서대로 출력  
  $ wc -l [누구를] : 파일이 몇 줄인지 출력, word count  
  
[Shell]
  - 커맨드를 실행시켜주고, 결과를 출력해주는 주체  
  - Bash : Bourne shell, 리눅스으 기본 쉘  
  - #!/bin/bash : xxx.sh 파일  
  - command 들을 나열하며 한번에 수행 가능  
  - .bashrc : login 할때마다, bash 셋팅  
    - .bashrc에 설정해서 편하게 사용할 수 있음, 즉 여기에 설정하면 한번만 설정하면 됌  
    - $PATH 도 설정할 수 있음, 환경변수 설정  
  - su & sudo (super user) : 관리자의 권한을 빌리는 것  
    - ubuntu는 root가 없음, 설치한 계정이 sudo 권한을 갖음  
    - su : 계정 전환(root 포함)  
    - sudo : root 계정 권한을 빌림  
    
[apt]
  - advanced package tool  
  - 패키지 매니저  
  - Debian이 리눅스 배포판 중 최고로 손꼽히는 이유?  
  - Fedora의 경우는 apt 대신 yum을 사용함  
  - commands  
    $ apt list : 패키지 리스트 출력  
      $ apt list --installed : 설치된 패키지 리스트 출력  
    $ apt search : 패키 찾기  
      $ apt search python2.7 | grep install : 예제  
    $ apt install  
    $ apt remove : 패키지 제거  
    $ apt update : apt 패키지 서버를 업데이트, 생각날때마다 해주기  
      $ /etc/apt/soruce.list 에 목록이 있음  
  
   
  
  
[Linux Directory]
  * / : 루트, 최상위 디렉토리, 리눅스의 모든 디렉토리들의 시작점  
  * /bin : 기본적인 명령어가 저장된 디렉토리, 실행가능한 프로그램들(binary), 터미널로 사용할 수 있는 애들, 명령어들, 함부로 건들지 말 것  
  * /dev : 시스템 디바이스 파일을 저장하고 있는 디렉토리, 즉 모든 장치들  
  * /home : 사용자의 홈 디렉토리  
  * /root : 시스템 최고관리자인 root사용자의 개인 홈 디렉토리, 일반 사용자는 접근 불가  
  * /sbin : 시스템 관리자들이 사용하는 명령어를 저장  
  * /tmp : 공용, 임시 디렉토리  
  * /usr : 시스템이 아닌 일반사용자들이 줄 사용하는 디렉토리  
  * /usr/bin/ : 일바 사용자들이 사용가능한 명령어 파일들이 존재하는 디렉토리, 여기에 왠만한 프로그램들이 깔림  

