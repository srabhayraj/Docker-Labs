Below is the mentioned link for a quick hands-on on docker. This is built for a quick demonstration by using the hellowhale image.

**[hellowhale](https://github.com/srabhayraj/Docker-Labs/tree/master/hellowhale)**

### Below is the quick points for explanation for "hellowhale" explanation

* Pre requisite
  * Install Docker
    - [For Linux](https://docs.docker.com/engine/install/ubuntu/)
    - [For Windows](https://docs.docker.com/docker-for-windows/install/)
* Clone the required Repository
* Building the Image
  * docker build -t hellowhale .
  * The docker build command builds Docker images from a Dockerfile, but the command has to be run in the same directory as the Dockerfile. 
  When an image is built, the commands specified in the Dockerfile are executed. The operating system is installed​ along with all the packages required in the Docker container.
  -t : Name and optionally a tag in the ‘name:tag’ format
  . : for current folder
* Running the Docker Container
  * docker run -d -p 80:80 --name hellowhale hellowhale
  * he docker run command creates a container from a given image and starts the container using a given command.
  -d :  Run container in background and print container ID
  -p : Publish a container’s port(s) to the host
  --name : for container name
* Tagging the Image
  * docker tag hellowhale abhayrajsr/hellowhale
  * Docker tags convey useful information about a specific image version/variant.
  * hellowhale : image name
  * abhayrajsr/hellowhale : image format for dockerhub account
* Pushing it to Dockerhub
  * docker login
  * docker push abhayrajsr/hellowhale

### Build first Alpine Docker image and push it to Dockerhub

```
$ docker run -dit alpine sh
```
If image is present locally in your system then it retrieve from the system, otherwise if it is not present in the system locally then it will retrieve from official library over dockerhub.

![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/run.PNG)


```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/docker-ps.PNG)


```
$ docker attach 62
/ #
/ #
/ # cat /etc/os-release
NAME="Alpine Linux"
ID=alpine
VERSION_ID=3.9.2
PRETTY_NAME="Alpine Linux v3.9"
HOME_URL="https://alpinelinux.org/"
BUG_REPORT_URL="https://bugs.alpinelinux.org/"
/ #
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/attach.PNG)


```
/ # apk update

/ # apk add git
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/update.PNG)


```
$ docker commit -m "Added GIT" 620 abhayrajsr/alpine-git
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/commit.PNG)


```
$ docker images
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/docker-images.PNG)


```
$ docker tag abhayrajsr/alpine-git:latest abhayrajsr/alpine-git:1.0
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/tag.PNG)


```
$ docker images
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/docker-images2.PNG)


```
$ docker login

$ docker push abhayrajsr/alpine-git:1.0
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/login-push.PNG)

