# Docker reference
This is an stydy of basic concepts of docker to use and create constainers for many applications.

## What is a container?
Simply put, a container is simply another process on your machine that has been isolated from all other processes on the host machine.

## Dockerfile

Use dockerfile to construct your own images, if you want to create your own image or customize an image you must to use dockerfile.

Important: An image is immutable

    FROM: ImageName (It's image name)

    RUN: Comands ex: apt-get install (You can use RUN to customize your images)

    EXPOSE: 8000

### Two ways to create images in docker

1. You can white a docker file 
2. Or you can commit your changes in a running container

## Hello world docker

Download hello-world image

```
docker run hello-world
```
List all containers
```
docker ps -a 
```
Remove a container
```
docker rm {containerId or containerName}
```
List all images
```
docker images
```
Remove images
```
docker rmi {imageId or imageName}
```

## Export ports
Run nginx with alpine 

| Parameter |                                |
|-----------|--------------------------------|
| -d        | Run a container in background  |
| --name    | Give a name for your container |
| -p        | Map a port                     |

```
docker run -d --name my_nginx nginx:alpine
```
Run container in port 8080
```
docker run -d --name docker_porta -p 8080:80 nginx:alpine
```

## Execute commands in container

| Parameter |                                |
|-----------|--------------------------------|
|  -i, --interactive | Keep STDIN open even if not attached  |
|  -t, --tty  | Allocate a pseudo-TTY |

Access bash
```
docker exec -i -t my_nginx bash 
//or
docker exec -it my_nginx bash 
```

## Volume bind
When you create a file in your local folder it will be have a copy in container folder.

docker run -d --name docker_porta -v {yourLocalFolder}:{containerFolder} -p 8080:80 nginx:alpine

## Volume

Show all volumes
```
docker volume ls 
```
Create a new volume
```
docker volume create {volumeName}
```
Show volume details 
```
docker volume inspect {volumeName}
```
```
docker volume create --driver local --opt type=none --opt device=%cd% --opt o=bind
```
## Working with networks

List networks
```
docker network ls
```
Create a network
```
docker network create -d bridge {networkName}
```
Use created network
```
docker run -d --name nginx2 --net={networkName} nginx
```

## Commit images

Commit your image 
```
docker commit {containerId} {myImageName}
```
Commit versions (You can create version of the same image)
```
docker commit {containerId} {myImageName}:v2
```

## Push images

Login in docker hub
```
docker login
```

```
docker push {myImageName}
```

## Tips

List all containers hash
```
docker ps -a -q
```
Remove all containers by hash
```
docker rm $(docker ps -a -q) -f
```

## Install docker

* [Clique here](https://docs.docker.com/engine/install/)

## References

* [Docker.com](https://docs.docker.com/get-started/)