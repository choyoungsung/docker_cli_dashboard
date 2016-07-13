Here is an execution file	http://bit.ly/dcs_

* Download 및 설치
```
curl -sL bit.ly/dcs_ -o ./dcs
sudo chmod 755 ./dcs
sudo mv ./dcs /usr/bin/dcs
```

# docker_cli_dashboard
CLi mode dashboard for Docker(in redhat, ubuntu, OSX)

![](https://raw.githubusercontent.com/goody80/docker_cli_dashboard/master/sample01.png)

* It can be helps for type quickly :)
* You just shuld send a command "dcs" for start,stop,remove, pull run...
* That's all :)

2015/08/06 - update
* Docker Cli Dashboard를 통해서 자동으로 이미지 build 및 Verification 할 수 있는 command를 추가 하였습니다. :) 

1. "build" command 입력 시, Build에 사용 될 Dockerfile이 위치한 상위 디렉토리를 입력 받습니다.
2. docker_build_auto.sh command를 해당 경로에 download 받고 해당 명령을 실행 합니다.
3. 해당 경로에 속한 Dockerfile을 수정 후 build를 진행 합니다.
4. 빌드가 완료 후 image에 설정한 부분들이 정상으로 적용되었는지 verification 처리 합니다.
5. Verification 완료후 미리 지정한 tag(or user ID)가 할당되며, 지정된 registry로 해당 이미지의 upload를 진행합니다.
6. Upload가 완료된 후 작업을 위해 사용된 temp 이미지 멫 log file을 clean-up 합니다

 * Image verification을 위한 명령어를 CheckCommand= 변수에 지정 해 주시면 이미지가 생성 된 후 확인을 진행 합니다.

2016/01/13- update
* 명령어 입력 부분에 command를 자유롭게 입력 할 수 있습니다.
 * 복수개의 이미지를 삭제 하고자 할 경우 아래와 같이 입력 가능합니다.
  
2016/04/20- update
* OS별 Sudo 사용 유무에 따른 예외처리 적용하였습니다.
```
rm 123124 0981723 09871023 0983
```

2016/07/04- update
* 사용하지 않는 Docker Processors 정리 기능
```
purge
```

2016/07/13- update
 1. 사용하지 않는 Volume 삭제기능 추가
 2. In-line command 입력방식 지원

* dcs 내부에서 clean 또는, dcs clean 형태로 사용하지 않는 Volume 정리
```
clean
```
