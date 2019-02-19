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
  * 모든명령어 --help : 해당 명령어의 사용법을 알 수 있음  
  $ find : 파일 탐색  
    $ find [대상위치] [옵션]  
    $ ex) find . -name 파일이름  
  $ clear : 화면 청소  
  
[Linux Directory]
  > / : 루트, 최상위 디렉토리, 리눅스의 모든 디렉토리들의 시작점
  > /bin : 기본적인 명령어가 저장된 디렉토리, 실행가능한 프로그램들(binary), 터미널로 사용할 수 있는 애들, 명령어들, 함부로 건들지 말 것.
  > /dev : 시스템 디바이스 파일을 저장하고 있는 디렉토리, 즉 모든 장치들
  > /home : 사용자의 홈 디렉토리
  > /root : 시스템 최고관리자인 root사용자의 개인 홈 디렉토리, 일반 사용자는 접근 불가
  > /sbin : 시스템 관리자들이 사용하는 명령어를 저장
  > /tmp : 공용, 임시 디렉토리
  > /usr : 시스템이 아닌 일반사용자들이 줄 사용하는 디렉토리
  > /usr/bin/ : 일바 사용자들이 사용가능한 명령어 파일들이 존재하는 디렉토리, 여기에 왠만한 프로그램들이 깔림

