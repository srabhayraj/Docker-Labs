# Creating Docker image with GIT installed

## Creating Dockerfile
```
FROM alpine:3.5
RUN apk update  
RUN apk add git
```

## Build Docker Image
```
