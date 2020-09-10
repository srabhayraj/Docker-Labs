# Saving Images and Containers as tar files for sharing

### Four major commands for doing this thing:
  * docker export : Export a container’s filesystem as a tar archive
  * docker import : Import the contents from a tarball to create a filesystem image
  * docker save : Save one or more images to a tar archive
  * docker load : Load an image from a tar archive

### Create Nginx Container

  * [NGINX] is a web server that also acts as an email proxy, reverse proxy, and load balancer. The software's structure is asynchronous and event-driven; which enables the processing of many requests at the same time. NGINX is highly scalable as well, meaning that its service grows along with its clients' traffic.
```
$ docker run -d -p 80:80 nginx
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/create.PNG)

### Displaying Created Container
```
$ docker ps -a
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/ps-a.PNG)

### Export the Created Container
```
$ docker export a8c > nginx.tar
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/export.PNG)

### Importing the Container

 * We could commit this container as a new image locally, but we could also use the Docker import command.
```
$ docker import - mynginx < nginx.tar
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/import.PNG)

### Displaying Images
 
  * Now we see that a new image named mynginx is displayed.
```
$ docker images
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/images.PNG)

 * To share this image upload the tar file on a web server and let other people also used this.
 * If we would rather deal with images that we have already commited, then we can also use load and save commands.
```
$ docker save -o mynginx1.tar nginx
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/save.PNG)

```
$ ls -l
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/ls-l.PNG)

 * Now, delete all images and containers running and try to run the below command to load docker image into ypur system.
```
$ docker rmi mynginx
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/rmi.PNG)

```
$ docker images
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/images2.PNG)

```
$ docker load < mynginx1.tar
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/load.PNG)

```
$ docker images
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/images3.PNG)














