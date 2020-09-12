# Create an image with ADD Instruction

### Creating Dockerfile
```
FROM alpine:3.5
RUN apk update
ADD http://www.vlsitechnology.org/pharosc_8.4.tar.gz .
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/1.PNG)

### Build Docker Image
```
$ docker build -t abhayrajsr/alpine-add . -f <Name-of-Dockerfile{AddDockerfile}>
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/2.PNG)

### Tagging Image as Labs-add
```
$ docker tag abhayrajsr/alpine-add abhayrajsr/labs-add:v1.0 
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/3.PNG)

### Verify the Images
```
$ docker images
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/4.PNG)

### Create a Container
```
$ docker run -dit abhayrajsr/labs-add:v1.0 /bin/sh
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/5.PNG)

### Displaying the running Container
```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/6.PNG)

### Enter into Container Shell
```
$ docker attach <container-id>
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/7.PNG)

### Verify that if the link has been extracted onto the container
```
/ # ls -ltr
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/add/8.PNG)

