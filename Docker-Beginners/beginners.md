# Docker-Labs for Beginners

### * Run Hello-world Example
```
$ docker run hello-world
```
![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/hello-world.PNG)

### * Docker Images
      - Listing Docker Images
      
      ```
      $ docker images
      ```
      
      ![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/dockerimagesPNG)
      
      
      - Showing All Images (included hidden images too)
      
      ```
      $ docker images -a
      ```
      
      ![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/dockerimages-a.PNG)
      
      
      - Listing images by name and tag
      
      First pull the images of same OS and different versions
      
      ```
      $ docker pull alpine:3.6
      $ docker pull alpine:3.7
      $ docker pull alpine:3.8
      $ docker pull alpine:3.9
      ```
      
      
      ```
      
      $ docker images alpine:3.7
      
      
      $ docker images alpine
      
      ```
      ![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/dockerpull.PNG)
      ![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/tag.PNG)
      
      
      - Listing the full length image IDs
      
      ```
      $ docker images --no-trunc
      ```
      
      ![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/notrunc.PNG)
      
      
      - Listing out images with filter
      
      ```
      
      $ docker images --filter=reference='alpine'
      
      ```
      
      ![alt Text](https://github.com/srabhayraj/Docker-Labs/blob/master/metadata/filter.PNG)
      
      

      


