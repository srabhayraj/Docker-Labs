# hellowhale

This is built for a quick demonstration.

Pre-requisite

- Install Docker


## Clone the Repository

```
git clone https://github.com/srabhayraj/Docker-Labs/hellowhale
```

## Building the Image

```
docker build -t hellowhale .
```

## Running the Docker Container

```
docker run -d -p 80:80 --name hellowhale hellowhale
```

## Tagging the Image

```
docker tag hellowhale srabhayraj/Docker-Labs/hellowhale
```

## Pushing it to Dockerhub

```
docker login
```

```
docker push srabhayraj/Docker-Labs/hellowhale
```
