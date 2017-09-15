# Dockerfile-ubuntu
Simple Dockerfile with necessary linux commands based on ubuntu 16.04.

## Included commands
1. Package curl: `curl`
2. Package dnsutils: `dig, nslookup`
3. Package iputils-ping: `ping`
4. Package net-tools: `ifconfig, netstat, arp, root`
5. Package openssh-server: `ssh, sshd`
6. Package traceroute: `traceroute`
7. Package vim: `vim`

## Others I had done
1. Modify the file *sources.list* to improve download speed. 
2. Copy this Dockerfile-ubuntu to image, and a simple script *start.sh* to start service ssh in each container.
3. Change password of root to 123 for ssh use in other applications.
4. Modify the file */etc/ssh/sshd_config* to permit the root login.
5. Expose port 22, 23 and 80.

## What I provide
1. *[Dockerfile-ubuntu](https://github.com/xxdoor/Dockerfile-ubuntu/blob/master/Dockerfile-ubuntu)*
2. *[sources.list](https://github.com/xxdoor/Dockerfile-ubuntu/blob/master/sources.list)*, I use the repository URL of SJTU.
3. *[start.sh](https://github.com/xxdoor/Dockerfile-ubuntu/blob/master/start.sh)*, 2-line script.
4. *[docker-compose.yml](https://github.com/xxdoor/Dockerfile-ubuntu/blob/master/docker-compose.yml)*, a yml file to start 2 containers from this image built by *Dockerfile-ubuntu*.

## Instruction
1. `$ docker build -t ubuntu:custom -f Dockerfile-ubuntu .`
   
   Build docker image from *Dockerfile-ubuntu*, and set current directory as the context path.
2. `$ docker-compose up -d`
   
   Start 2 containers. 
   Till now, there are 2 containers up, and all done.You can use `$ docker exec -it ubuntu1 bash` to enter the container:ubuntu1.
