# Managing the Container Shell

* First of all, clear the environment of Docker.
* So that the commands can be clearly interpreted.

* To check the IDs of all running containers
```
$ docker ps -a -q
```
  * -q is for query <br />
  
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/1.PNG)

### To clear the environment of docker, delete all the containers which have created till now.
```
$ docker rm -f $(docker ps -a -q)
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/2.PNG)

* To check the containers
```
$ docker ps -a
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/3.PNG)


### Launch the two containers from dockerhub
```
$ docker run -d -p 5000:5000 --name app1 selaworkshops/python-app:1.0

$ docker run -d -p 5001:5001 -e "port=5001" --name app2 selaworkshops/python-app:2.0
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/5.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/6.PNG)

* -d --> Used to detach the container
* -p --> Used for port number
* -e --> Used to set environment variable
* An environment variable is a dynamic-named value that can affect the way running processes will behave on a computer. 
Environment variables are useful to store system-wide values, for examples, PATH : the most frequently-used environment variable, which stores a list of directories to search for executable programs.

### Ensure the Containers are running
```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/7.PNG)

### Stop the first container
```
$ docker stop app1
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/8.PNG)

### Kill the second container
```
$ docker kill app2
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/9.PNG)

### Displaying running containers
```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/10.PNG)

### Show all the containers(including non-running containers)
```
$ docker ps -a
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/11.PNG)

### Start both containers again
```
$ docker start app1 app2
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/12.PNG)

### Displaying running containers
```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/13.PNG)

### Restart the second container
```
$ docker restart app2
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/14.PNG)

### Displaying the docker host information
```
$ docker info
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/16.PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/16(2).PNG)

### Showing the running processes in the first container
```
$ docker top app1
```
 * "docker top" command display the running processes of a container.<br />
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/17.PNG)

### Retrieve the history of the second container
```
$ docker history selaworkshops/python-app:2.0
```
 * "docker history" command shows the history of an image.<br />
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/18.PNG)

### Inspect the second container image
```
$ docker inspect selaworkshops/python-app:2.0
```
 * "docker inspect" command provides detailed information on constructs controlled by Docker or on Docker objects. By default, docker inspect will render results in a JSON array.<br />
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/19(1).PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/19(2).PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/19(3).PNG)

### Inspect the first container and looks for the internal ip
```
$ docker inspect app1
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/20(1).PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/20(2).PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/20(3).PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/20(4).PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/20(5).PNG)
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/20(6).PNG)

### Show the logs of the second container using flag follow
```
$ docker logs --follow app2
```
  * "docker logs" command fetch the logs of a container.<br />
  * --follow,-f  --> 	Follow log output<br />
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/managing/21.PNG)

### Stop to tracking logs
```
$ Ctrl + C
```

### Browse to the application and see the containers logs from the terminal
```
http://localhost:5001
```
















