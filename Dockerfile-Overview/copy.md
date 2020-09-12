# Create an image with COPY Instruction
    * The COPY instruction copies files or directories from source and adds them to the filesystem of the container at destinatio.
    * Two form of COPY instruction:
    ```
    COPY [--chown=<user>:<group>] <src>... <dest>
    COPY [--chown=<user>:<group>] ["<src>",... "<dest>"] (this form is required for paths containing whitespace)
    ```

### Creating a Dockerfile
```
FROM nginx:alpine 
LABEL maintainer="Abhay Raj Singh Rathore"

COPY index.html /usr/share/nginx/html/
ENTRYPOINT ["nginx", "-g", "daemon off;"]
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/1.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/2.PNG)

### Creating the index.html file
```
$ echo "Welcome to Docker-Labs ! " > index.html
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/3.PNG)

### Building Docker Image
```
$ docker image build -t cpy:v1 .
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/4.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/5.PNG)

### Starting the Container
```
$ docker container run -d --rm --name myapp1 -p 80:80 cpy:v1
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/6.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/7.PNG)

### Checking Index File
```
$ curl localhost
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/8.PNG)

## COPY Instruction in Multi-Stage Builds

### Creating Dockerfile
```
FROM alpine AS stage1
LABEL maintainer="Abhay Raj Singh Rathore"
RUN echo "Welcome to Docker-Labs !" > /opt/index.html

FROM nginx:alpine
LABEL maintainer="Abhay Raj Singh Rathore"
COPY --from=stage1 /opt/index.html /usr/share/nginx/html/
ENTRYPOINT ["nginx", "-g", "daemon off;"]
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/9.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/10.PNG)

### Building Docker Image
```
$ docker image build -t cpy:v2 .
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/11.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/12.PNG)

### Starting the container
```
$ docker container run -d --rm --name myapp2 -p 8080:80 cpy:v2
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/13.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/14.PNG)

### Checking index.html file
```
$ curl localhost:8080
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/copy/15.PNG)


## NOTE
We can name our stages, by adding an AS to the FROM instruction.By default, the stages are not named, and we can refer to them by their integer number, starting with 0 for the first FROM instruction.We are not limited to copying from stages we created earlier in our Dockerfile, we can use the COPY --from instruction to copy from a separate image, either using the local image name, a tag available locally or on a Docker registry.
```
COPY --from=nginx:latest /etc/nginx/nginx.conf /nginx.conf
```
