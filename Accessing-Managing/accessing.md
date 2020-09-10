# Accessing the Container Shell

### Create Ubuntu Container
```
$ docker run -dit ubuntu
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/run.PNG)

### Displaying Created Container
```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/dockerps.PNG)

### Accessing the Container Shell
```
$ docker exec -t <container-id> bash
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/exec.PNG)

### Another Method to Access the Container Shell
```
$ docker attach <container-id>
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/attach.PNG)

  * After accessing the container, when we exit it and then try to re-acccess it we can't able to access it.
  * The reason is that the docker service daemon is stopped and before restarting it won't work.
  * Daemon : Daemon is a process that runs in the background and performs a specified operation at predefined times or in response to certain events.
  * Below is the demonstration of above mentioned statements.

```
$ docker attach <container-id>
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/attach2.PNG)

```
$ docker exec -t <container-id> bash
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/exec2.PNG)

  * Docker Container is running then also it is not accessing the shell.
```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/ps2.PNG)

  * Now, for solving this we have to start the container then it can access the shell.
```
$ docker start <container-id>
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/start.PNG)

  * Now, we can access the shell.
```
$ docker attach <container-id>
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/attach3.PNG)

  * Now, when we try to access from another method, it fails
  * The reason is that when we exit the container the docker daemon stopped. So we have to start it only then we can access.
```
$ docker exec -t <container-id> bash
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/exec3.PNG)

```
$ docker start <container-id>
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/start2.PNG)

```
$ docker exec -t <container-id> bash
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/exec4.PNG)

### Displaying Running Containers
```
$ docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/ps3.PNG)

### TO stop the all running Containers together
```
$ docker stop $(docker ps)
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/stop.PNG)
  
  * Here,  we use '$' sign as a variable and 'docker ps' container the value of variable by which all container can access together.

### Displaying Running Containers
```
docker ps
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/accessing/ps4.PNG)











