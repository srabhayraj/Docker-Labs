# Creating Docker image with GIT installed

## Creating Dockerfile
  * To create dockerfile, first create a text file named Dockerfile, and then write the script of it.
  
```
FROM alpine:3.5
RUN apk update  
RUN apk add git
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/git/1.PNG)

## Build Docker Image
```
