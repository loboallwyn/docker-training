# Introduction to Docker

## What is docker ?
Docker is a set of platform as a service products that use OS-level virtualization to deliver software in packages called containers. Containers are isolated from one another and bundle their own software, libraries and configuration files; they can communicate with each other through well-defined channels.

### Containers Vs Virtual Machines
https://www.netapp.com/blog/containers-vs-vms/


## Why use docker ?
- Isolation
- Lightweight
- Easier Installation
- Faster Development
- Server specification under version control.

## Docker basics

### Installation

https://docs.docker.com/engine/install/

### Install Nginx

```
docker container run --name mynginx nginx:stable

# Port Forwarding
docker container run --name mynginx -p 8080:80 nginx:stable

docker run --rm --name mynginx -p 8080:80 nginx:stable

docker container rm mynginx
```

### Change the index.html file inside nginx

```
docker container run --rm -v /Users/allwyn/source/docker/tutorial/index.html:/usr/share/nginx/html/index.html  -p 8080:80 --name mynginx nginx:stable
```

###  Daemon Mode

```
docker run -d  --rm -v /Users/allwyn/source/docker/tutorial/index.html:/usr/share/nginx/html/index.html  -p 8080:80 --name mynginx nginx:stable 
```

### Check logs when in Daemon mode

```
docker container logs --follow mynginx
```

### Shell Access to the docker image

```
docker container exec -it mynginx /bin/bash
```

### View runing containers

```
docker container ps
```


### Stopping the container

```
docker container stop myginx
```
