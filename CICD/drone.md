# Drone

# 前言
因為git server選用go語言開發的gitea，而drone也是用go語言開發的，就選用他了。  

# Setup
採用docker-compose的方式建立。  
```yml
version: '2'

services:
  drone-server:
    image: drone/drone:0.8

    ports:
      - 8080:8000
      - 9000
    volumes:
      - ./.drone:/var/lib/drone/
    restart: always
    environment:
      - DRONE_OPEN=false
      - DRONE_HOST=https://localhost
      - DRONE_SECRET=123456
      - DRONE_GITEA=true
      - DRONE_GITEA_URL=http://localhost:10080

  drone-agent:
    image: drone/agent:0.8

    command: agent
    restart: always
    depends_on:
      - drone-server
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    environment:
      - DRONE_SERVER=drone-server:9000
      - DRONE_SECRET=123456
```  
啟動: `sudo docker-compose up`  
網址: https://localhost:8080  
連上後，會看到:  
<img src="picture/drone/login.PNG" width="480">  
輸入你的gitea上的帳密，就會看到:  
<img src="picture/drone/drone_repo.PNG" width="480">  
就可以開始玩看看摟~


# Reference
[drone doc](http://docs.drone.io/)  
[drone github](https://github.com/drone/drone)  
[setting up continuous delivery with drone](https://drailing.net/2018/02/setting-up-continuous-delivery-with-drone/)  