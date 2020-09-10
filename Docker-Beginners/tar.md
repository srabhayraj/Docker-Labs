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
![alt Text]()

