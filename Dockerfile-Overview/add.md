# Create an image with ADD Instruction
    * COPY and ADD are both Dockerfile instructions that serve similar purposes. They let you copy files from a specific location into a Docker image.
    * COPY takes in a src and destination. It only lets you copy in a local file or directory from your host (the machine building the Docker image) into the Docker image itself.
    * ADD lets you do that too, but it also supports 2 other sources. First, you can use a URL instead of a local file / directory. Secondly, you can extract a tar file from the source directly into the destination.

### Creating Dockerfile
```
FROM alpine:3.5
RUN apk update
ADD http://www.vlsitechnology.org/pharosc_8.4.tar.gz .
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/1.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/2.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/3.PNG)

### Build Docker Image
```
$ docker build -t abhayrajsr/alpine-add . -f <Name-of-Dockerfile{AddDockerfile}>
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/4.PNG)

### Tagging Image as Labs-add
```
$ docker tag abhayrajsr/alpine-add abhayrajsr/labs-add:v1.0 
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/5.PNG)

### Verify the Images
```
$ docker images
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/6.PNG)

### Create a Container
```
$ docker run -dit abhayrajsr/labs-add:v1.0 /bin/sh
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/7.PNG)

### Displaying the running Container
```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/8.PNG)

### Enter into Container Shell
```
$ docker attach <container-id>
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/9.PNG)

### Verify that if the link has been extracted onto the container
```
/ # ls -ltr
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/10.PNG)

