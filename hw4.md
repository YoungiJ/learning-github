# **CLI(command Line Interface)_lecture note**

## ***about LINUX***
- 리눅스 커널은 무료 오픈 소스 운영체제로 커스터마이즈된 OS를 만들 수 있음
- 리눅스 커널은 사용자를 위한 운영 체제 역할을 하는 다양한 배포판을 지원하는데 이러한 배포판 중 유명한 것으로 우분투,Devian,Fedora 가 있음
- 개인용 보다는 서버, 안드로이드에서 활용함
- 보안성 굿/안정성 좋음

## ***OS role***
 **shell**(kernal 과 소통하는 interface)->**kernel**(hardware resource와 소통하는 중심 os)->**hardware resource**(cpu,디스크 드라이브,메모리)

## ***CLI vs GUI*** 

CLI 장단점>명령어 암기,빠르다  
GUI 장단점>직관적,마우스,느리다 [CLI vs GUI more](https://ko.gadget-info.com/difference-between-cli)

LINUX/MACOS(리눅스 기반)>Terminal 프로그램 실행  
WINDOWS>Git Bash사용

![](https://velog.velcdn.com/images%2Flink717%2Fpost%2F950e6128-ca74-471d-b7f9-945f6f3e1c5a%2Fimage.png)

## ***경로 탐색*** 
- pwd-현재 경로 출력
- cd-change directory
- ls-list files and directory 정보 가져옴
- / root 가장 근본 디렉토리
- . 현재 디렉토리
- .. 한단계 상위 디렉토리 ex)cd ../neral
- ~ 현재 유저의 home
- /[이름] >절대경로, 나머지는 상대경로
  
## ***소유 정보 출력*** 
-l     long format->소유정보 생성날짜 소유자를 출력해줌  
-lh    >-l랑 다 똑같은데 kilobyte 로 변환
둘다 total 몇k인지 나옴

## ***조작방법(복사 이동 삭제)*** 

*주의사항>cli는 명령어 입력할 때 주의 실제상황!!->반드시 이중 삼중으로 백업하기!*

## cp :파일,디렉 복사하기

```sh
$ cp module.py backup_module.py -같은 디렉일때
$ cp -r../neral . > 현재 디렉에 상위 디렉에 있는 neral디렉 (-r 모든 것)을 복사하겠다
-r 안쓰면 바로 위의 디렉만 가져오게 됨
```


## mv: 이동 또는 이름 바꿀때
```sh
$ mv module.py new_module.py> 이름 바꾸기
```
## rm :**굉장히 위험 영구적으로 삭제 휴지통에서도 복원못함!!!!!!!!**

```sh
$ rm -i file1 file2
각각의 파일이 삭제되기 전에 프롬프트 창에 뜸
```
## mkdir :make directory 현재 디렉안에 디렉 만들기
```sh
$ mkdir new_directory
$ ls
```
---------------------------------------------
## 여러개의 파일 이동,삭제->wildcards
| Pattern  | Matches |
| --:  | :--: |
| *   | 모든 파일 이름 |
| g*  | g로 시작하는 모든 파일 이름 |
| b*.txt | g로 시작하고 txt파일인 파일 이름 |
| Data??? | Data뒤에 모르는 세글자가 이름인 파일 |


## **Various TIPs** 
1) tab치면 자동완성  
2) 위에 있는 명령어 또 입력하고 싶을때 위 화살표 >계속 위 화살표 누르면 그 위 명령어   
3) clear> 다 삭제  
4) rm 으로 지우기 전에 ls>미리 확인해보라구~  
5) man cp>설명 문서나와서 참고 가능함  
6) 끝맞칠때 exit누르면 log out  


