# Docker TEST

Reference Video :: Youtube 얄팍한 코딩사전 : Korean Youtuber
https://youtu.be/hWPv9LMlme8?si=obdrCWXT5iMRlhzd

## Test Environment

- Docker playground : https://labs.play-with-docker.com/

## Source : git

- https://gitlab.com/yalco/practice-docker.git

## Docker CLI Command

- Origin Reference : https://www.yalco.kr/36_docker/

### Check Docker Version

docker -v

### download only docker image

docker pull {nameOfImage}:{Tag for image}
(The tag Is Optional)

### Make Container with Image

docker create {option} {nameOfImage}:{Tag}

옵션 설명
-d 데몬으로 실행(뒤에서 - 안 보이는 곳(백그라운드)에서 알아서 돌라고 하기)
-it 컨테이너로 들어갔을 때 bash로 CLI 입출력을 사용할 수 있도록 해 줍니다.
--name {이름} 컨테이너 이름 지정
-p {호스트의 포트 번호}:{컨테이너의 포트 번호} 호스트와 컨테이너의 포트를 연결합니다.
--rm 컨테이너가 종료되면{내부에서 돌아가는 작업이 끝나면} 컨테이너를 제거합니다.
-v {호스트의 디렉토리}:{컨테이너의 디렉토리} 호스트와 컨테이너의 디렉토리를 연결합니다.

### Start container

docker start {container id or name}

### Enter container(inside using CLI)

docker attach {container id or name}

### Image Download and enter container

docker run {nameOfImage}:{Tag}
e.g. docker -it run python:3

### Restart container which is running

docker restart {container id or name}

### exit and stop container

exit or Ctrl+D

### not stop but exit container

Ctrl + P, Q

### show list of container running

docker ps

### show list of all container

docker ps -a

### delete container

docker rm {container id or name}

### delete all container

docker rm `docker ps -a -q`

### delete image

docker rmi {option} {image id}
force to delete with option -f

### stop and delete all images and container

- 모든 컨테이너 중지
  docker stop $(docker ps -aq)

### delete unused containers, images, networks, volumes.

docker system prune -a

# easy command to stop and delete combination

docker stop $(docker ps -aq)
docker system prune -a

### build docker image with Dockerfile file Script

# Dockerfile 파일이 있는 디렉토리 기준. 마지막의 . 이 상대주소

docker build -t {nameOfImage} .( <= relative path)

### build docker image & container with docker-compose file Script

# docker background running

option : -d (demon)
