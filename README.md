# Beginers guide to containerization using Docker on Ubuntu

A basic Django project has been used here to containerize. 

## SO first of all, What is a container?
A container is a bundle of Application, Application libraries required to run your application and the minimum system dependencies.


## What is Docker?
dummy text

## Why Docker?
dummy text

## INSTALL DOCKER

Detailed instructions to install Docker are provided in this link:-
https://docs.docker.com/get-docker/

For Demo, 

run these following commands to install docker on your ubuntu machine.

```
sudo apt update
sudo apt install docker.io -y
```
### Start Docker daemon

Start the daemon using the below command

```
sudo systemctl start docker
```

Use the below command to verify if the docker daemon is actually started and Active

```
sudo systemctl status docker
```
![Alt text](image.png)
Here, docker is up and running

## Now let's get started

### Clone this repository and move to python-web-app 

```
git clone https://github.com/pias97/docker-practice.git
cd  python-web-app
```

### Login to Docker [Create an account with https://hub.docker.com/]

## Create a repository on dockerhub
![Alt text](image-1.png)

I have created one here.

Now back to terminal, login here using same credential.
```
docker login
```

```
Login with your Docker ID to push and pull images from Docker Hub. If you don't have a Docker ID, head over to https://hub.docker.com to create one.
Username: _ _
Password: _ _
```


```
"Login Succeeded" will appear if credentials are fine.
```

### Everything is set, Let's build our first Docker Image

You need to change the username accoringly in the below command

```
docker build -t pias97/first_python_image:v1 .
```

Output of the above command

```
    dummy output
```
### Verify Docker Image is created

```
docker images
```

Output 

```
REPOSITORY                  TAG               IMAGE ID       CREATED         SIZE
pias97/first_python_image   v1                0eb9acd4b1fc   7 hours ago     508MB
moby/buildkit               buildx-stable-1   ee33f441bff7   4 weeks ago     172MB
tonistiigi/binfmt           latest            354472a37893   15 months ago   60.2MB
```
Here is our first image. Let's push it to our docker repository. 

```
docker push pias97/first_python_image:v1
```
![Alt text](image-2.png)

Here it is pushed on the dockerhub repository.

Notice on thing, the size of the our image is comparatively large 