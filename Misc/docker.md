# Docker

# Commands

1. `docker --version`: 查看版本  
```
Docker version 18.03.0-ce, build 0520e24302
```
2. `docker search ubuntu`: 查找線上的Image
```
NAME                                                   DESCRIPTION                                     STARS               OFFICIAL            AUTOMATED
ubuntu                                                 Ubuntu is a Debian-based Linux operating sys…   9041                [OK]
dorowu/ubuntu-desktop-lxde-vnc                         Ubuntu with openssh-server and NoVNC            260                                     [OK]
rastasheep/ubuntu-sshd                                 Dockerized SSH service, built on top of offi…   195                                     [OK]
consol/ubuntu-xfce-vnc                                 Ubuntu container with "headless" VNC session…   147                                     [OK]
ansible/ubuntu14.04-ansible                            Ubuntu 14.04 LTS with ansible                   95                                      [OK]
ubuntu-upstart                                         Upstart is an event-based replacement for th…   93                  [OK]
neurodebian                                            NeuroDebian provides neuroscience research s…   55                  [OK]
1and1internet/ubuntu-16-nginx-php-phpmyadmin-mysql-5   ubuntu-16-nginx-php-phpmyadmin-mysql-5          48                                      [OK]
ubuntu-debootstrap                                     debootstrap --variant=minbase --components=m…   40                  [OK]
nuagebec/ubuntu                                        Simple always updated Ubuntu docker images w…   23                                      [OK]
tutum/ubuntu                                           Simple Ubuntu docker images with SSH access     18
i386/ubuntu                                            Ubuntu is a Debian-based Linux operating sys…   16
1and1internet/ubuntu-16-apache-php-7.0                 ubuntu-16-apache-php-7.0                        13                                      [OK]
ppc64le/ubuntu                                         Ubuntu is a Debian-based Linux operating sys…   12
1and1internet/ubuntu-16-nginx-php-5.6-wordpress-4      ubuntu-16-nginx-php-5.6-wordpress-4             7                                       [OK]
eclipse/ubuntu_jdk8                                    Ubuntu, JDK8, Maven 3, git, curl, nmap, mc, …   7                                       [OK]
codenvy/ubuntu_jdk8                                    Ubuntu, JDK8, Maven 3, git, curl, nmap, mc, …   5                                       [OK]
darksheer/ubuntu                                       Base Ubuntu Image -- Updated hourly             5                                       [OK]
pivotaldata/ubuntu                                     A quick freshening-up of the base Ubuntu doc…   2
1and1internet/ubuntu-16-sshd                           ubuntu-16-sshd                                  1                                       [OK]
smartentry/ubuntu                                      ubuntu with smartentry                          1                                       [OK]
ossobv/ubuntu                                          Custom ubuntu image from scratch (based on o…   0
1and1internet/ubuntu-16-healthcheck                    ubuntu-16-healthcheck                           0                                       [OK]
pivotaldata/ubuntu-gpdb-dev                            Ubuntu images for GPDB development              0
paasmule/bosh-tools-ubuntu                             Ubuntu based bosh-cli                           0                                       [OK]
```

3. `docker pull ubuntu`: 下載image
```
Using default tag: latest
latest: Pulling from library/ubuntu
84ed7d2f608f: Pull complete
be2bf1c4a48d: Pull complete
a5bdc6303093: Pull complete
e9055237d68d: Pull complete
Digest: sha256:868fd30a0e47b8d8ac485df174795b5e2fe8a6c8f056cc707b232d65b8a1ab68
Status: Downloaded newer image for ubuntu:latest
```

4. `sudo docker images`: 查看目前local docker的所有image
```
REPOSITORY          TAG                 IMAGE ID            CREATED             SIZE
ubuntu              latest              1d9c17228a9e        8 days ago          86.7MB
```

5. `sudo docker run -i -t ubuntu /bin/bash`: 分配一個terminal進入交互操作模式
```
root@59954db08b43:/# uname -a
Linux 59954db08b43 4.14.79-boot2docker #1 SMP Thu Nov 8 01:56:42 UTC 2018 x86_64 x86_64 x86_64 GNU/Linux
```
結束離開: `exit` or `Ctrl-D`  
Detach: `Ctrl-P + Ctrl-Q`  
Attach: `sudo docker attach 59954db08b43`

6. `sudo docker ps -a`: 查看所有的container
```
CONTAINER ID        IMAGE               COMMAND             CREATED             STATUS                           PORTS               NAMES
59954db08b43        ubuntu              "/bin/bash"         About an hour ago   Up About an hour                                     xenodochial_morse
df2e13c45fa6        ubuntu              "/bin/bash"         About an hour ago   Exited (0) About an hour ago                         confident_feynman
eb51172d9f86        ubuntu              "/bin/bash"         About an hour ago   Exited (127) About an hour ago                       tender_shirley
```

7. `docker cp /path/to/file1 59954db08b43:/path/to/file2`: copy file from host to docker container  

8. `docker cp 59954db08b43:/path/to/file1 /path/to/file2`: copy file from docker container to host  

9. `docker rm 59954db08b43`: remove container  

# Reference
[docker get started](https://docs.docker.com/get-started/#test-docker-installation)  
[Windows install docker](https://hk.saowen.com/a/5b14e34f7266b297f0641b4561a6250f7c703fe27c6d1970055aa6436495fd49)  
[Docker 常用指令與容器操作教學](https://blog.gtwang.org/linux/docker-commands-and-container-management-tutorial/)