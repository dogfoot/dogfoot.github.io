---
layout: post
title: 도커를 이용한 개발환경 셋팅 (for windows)
tags:
   - docker
---

## docker & centos7 설치
### 사전 작업
* https://www.docker.com 가입
* DockerDesktop 다운로드 후 설치
* PowerShell 실행

### centos7 이미지 다운로드
#### 이미지 탐색
```bash
PS #########> docker search centos
NAME                               DESCRIPTION                                     STARS               OFFICIAL            AUTOMATED
centos                             The official build of CentOS.                   5454                [OK]
ansible/centos7-ansible            Ansible on Centos7                              122                                     [OK]
jdeathe/centos-ssh                 CentOS-6 6.10 x86_64 / CentOS-7 7.6.1810 x86…   110                                     [OK]
consol/centos-xfce-vnc             Centos container with "headless" VNC session…   93                                      [OK]
centos/mysql-57-centos7            MySQL 5.7 SQL database server                   59
```

#### 이미지 다운로드
```bash
PS #########> docker pull centos:7
7: Pulling from library/centos
8ba884070f61: Pull complete
Digest: sha256:a799dd8a2ded4a83484bbae769d97655392b3f86533ceb7dd96bbac929809f3c
Status: Downloaded newer image for centos:7
```

#### 컨테이너 생성 및 이미지 실행
`docker run <옵션> <이미지 이름, ID> <명령> <매개 변수>`
```bash
PS #########> docker run -it --name test centos:7 /bin/bash
[root@ddb7bd6fd170 /]#
```
* -i : 표준 입력(stdin)을 활성화하며 컨테이너와 연결(attach)되어 있지 않더라도 표준 입력을 유지합니다.
* -t : TTY 모드(pseudo-TTY)를 사용합니다. Bash를 사용하려면 이 옵션을 설정해야 합니다. 이 옵션을 설정하지 않으면 명령을 입력할 수는 있지만 셸이 표시되지 않습니다.
* --name : 컨테이너의 이름을 설정합니다.