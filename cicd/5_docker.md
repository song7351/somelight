1. 도커를 왜 써야하나?

- 현업에서는 딱히 필요없을것 같다. 그러나 경험을 위해서 사용해봤다. (대량의 서버가 아니라 하나의 서버만 사용하기 때문에)

2. 도커설치 관련

- https://velog.io/@anrun/docker1

3. 도커 바인드
   도커 바인드 마운트(Bind Mount)를 사용하여 엔진엑스(Nginx)에서 도커 컨테이너로 완성한 dist를 root로 설정할 수 있습니다.

도커 바인드 마운트를 사용하면 호스트 머신의 파일이나 디렉토리를 컨테이너 내부의 디렉토리에 마운트할 수 있습니다. 이를 이용하여 엔진엑스가 사용할 디렉토리를 호스트 머신의 디렉토리와 연결하여 사용할 수 있습니다.

예를 들어, 호스트 머신의 /path/to/dist 디렉토리에 엔진엑스에서 사용할 dist 파일이 있다고 가정하겠습니다. 이를 도커 컨테이너 내부의 /usr/share/nginx/html 디렉토리와 바인드 마운트하려면 다음과 같은 명령어를 사용할 수 있습니다.

docker run -d -p 80:80 -v /path/to/dist:/usr/share/nginx/html nginx

위 명령어에서 -v 옵션은 호스트 머신의 /path/to/dist 디렉토리와 컨테이너 내부의 /usr/share/nginx/html 디렉토리를 바인드 마운트한다는 것을 나타냅니다. 이를 통해 엔진엑스는 컨테이너 내부의 /usr/share/nginx/html 디렉토리를 root로 설정하여 dist 파일을 사용할 수 있습니다.

또한, -d 옵션은 컨테이너를 백그라운드 모드로 실행하고, -p 옵션은 호스트 머신의 80번 포트와 컨테이너 내부의 80번 포트를 매핑하여 엔진엑스에 접근할 수 있도록 합니다.

이와 같은 방법으로 도커 바인드 마운트와 옵션을 활용하여 엔진엑스에서 도커 컨테이너로 완성한 dist를 root로 설정할 수 있습니다.
