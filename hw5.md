# **CLI(command Line Interface)2_lecture note**

## ***standard output***
- **>** 새로운 파일 만들기
- **cat** 텍스트 파일에 있는 내용을 그대로 출력해줌
- **>>**  예전내용에 새로운 내용 덧붙이고 싶을때/or 새로운 파일 만들기

## ***standard input (키보드)*** 
 **<** 뒤에 있는 내용의 명령을 읽어옴  
$ sort < word.txt > sorted_words.txt -안에 있는 내용들을 sorting을 해서 sorted_worded.txt 새파일로 저장을 해라   

*띄어쓰기 주의하기!!*   
$ output=cat sorted_worded.txt   

![](https://t2.daumcdn.net/thumb/R720x0/?fname=http://t1.daumcdn.net/brunch/service/user/zIH/image/cYQGsh5PqnlHm-2-EHITjeFHaWE.png)

## ***Make pipeline*** 
- 파이프라인은 이전 명령의 출력을 다음 명령의 입력으로 공급한다.
- ls -lh| less  양이 너무 많으니까 조금만 출력하도록 하고 스크롤로 나머지 내용 확인할수 있도록 함
- ls -lh| wc-l 현재 디렉토리에 있는 파일의 개수 확인
q를 누르면 스크린에서 벗어남!
  
## ***Expansion 확장*** 
- shell commmand에 들어가기 전에 특정한 의미로 확장되는 것을 의미함
echo 뒤에 오는 텍스트 출력

- echo * => ls의 기능 //*가 현재 디렉토리에 있는 파일을 정보를 담는 기능
- ehco ~ =>현재 유저의 home directory
- backslash=>이어주기
ex) ls -l\--reverse\--human--readable>> backslash(\)가 이어주는 역할을 함

## ***Permission*** 
*very important>
>리눅스는 멀티 유저 시스템

> $ -rwxr-xr-x 1 User 197121 1963639 Apr 20 14:52 /bin/bash*

-rwx rwx rwx  

1)파일이냐 디렉토리냐 -면 파일 d면 디렉토리  
2)3자리씩 끊어읽기 owner/group/others  
		            	root  root  11351  
3)read write execute(실행가능한 파일일떄 실행가능한 권한을 주는 것)  

## ***changing permissions(chmod)***

-설정된 권한을 바꾸고 싶을때  
chmod 600(권한을 나타내는 숫자) 파일이름이나 디렉토리  
|숫자|rwxrwxrwx|
| --:  | :--: |
| 777  | rwxr-xr-x |
| 755   | rwx------ |
| 700  | rw-rw-rw- |
| 666 | rw-r--r-- |
| 600 | rw------- |  

777(모두에게 권한)/755/711/666/644/600(소유자만 읽고 적을 수 있음)

```sh
$ cp module.py backup_module.py -같은 디렉일때
$ cp -r../neral . > 현재 디렉에 상위 디렉에 있는 neral디렉 (-r 모든 것)을 복사하겠다
-r 안쓰면 바로 위의 디렉만 가져오게 됨
```

## ***Superuser***
- 모든 권한을 가짐>password를 물어봄
-기본적으로 cli명령어 앞에 sudo라는 글자를 붙임
- sudo -i>계정이름이 root로 바뀜->개인으로 바꾸려면 exit
```sh
$ sudo some_command
$ sudo -i
```
---------------------------------------------
## ***shell script***

- 뭔가 미리 작성을 해놓고 자동으로 실행되는 프로그램
- ex) nano >
#!/bin/bash- 이 스크립트가 bash스크립트인지 알려주기 위해!



## ***Various TIPs*** 
1) history> 과거의 명령들을 모아서 보내줌!!  ex> history > history_command.txt
2) -하나면 약식,  --두개면 풀네임



