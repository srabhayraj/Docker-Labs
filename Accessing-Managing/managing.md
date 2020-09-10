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

