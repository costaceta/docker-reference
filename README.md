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

## Install docker

* [Clique here](https://docs.docker.com/engine/install/)

## References

* [Docker.com](https://docs.docker.com/get-started/)