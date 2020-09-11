# Creating Docker image with GIT installed

## Creating Dockerfile
  * To create dockerfile, first create a text file named Dockerfile, and then write the script of it.
  
```
FROM alpine:3.5
RUN apk update  
RUN apk add git
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/git/1.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/git/2.PNG)

## Build Docker Image
  * With the help of Dockerfile, we will build the Docker image.

```
$ docker build -t abhayrajsr/alpine-git .
```
 * Here, we used "." to represent that used the current folder to access dockerfile.
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/git/3.PNG)

## Tagging image as labs-git
```
$ docker tag abhayrajsr/alpine-git abhayrajsr/labs-git:v1.0
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/git/4.PNG)

## Verify the Images
```
$ docker images
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/git/5.PNG)

## Create a Container
```
$ docker run -dit abhayrajsr/labs-git:v1.0 /bin/sh

$ docker run -dit abhayrajsr/labs-git:v1.0
```

  * Above following both commands are same, but here we write it because when we need a specific type of terminal then we get get it by this method (like /bin/bash). By default, it provide the /bin/sh terminal.

![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/git/6.PNG)

## Displaying running Containers
```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/git/7.PNG)

## Enter into Container Shell and verifying git is installed or not
```
$ docker attach <container-id{first three letters}>
 
  / # git --version
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/git/8.PNG)

