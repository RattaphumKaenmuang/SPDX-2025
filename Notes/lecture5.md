# Docker
Platform allowing users to run applications in a "container-ised" form, allowing each service to be able to have its own environment catered to itself, making compatibility way easier than hard-installing to the host itself.

A blueprint of these environments are called "images", which will be used to create instances of containers. You can create an image yourself from a base image + other services you need (then upload to) or pull from a registry.

## Relevant Commands
### docker login
```
docker login [OPTIONS] [SERVER]
docker login
docker login -u <user_name>
docker login -u <user_name> -p <password>
```
### docker logout
```
docker logout [SERVER]
docker logout
```

### docker image
List all images downloaded.
```
docker images
docker image ls
```

### docker pull
Download an image from a registry.
```
docker image pull [OPTIONS] NAME[:TAG|@DIGEST]
docker pull <image name>
```

### docker create
```
docker create <options> <image name> --name -v -p
docker create --name ubuntu14 -v /user/sommaik:/home ubuntu:14.04
```

### docker run
This command will create a NEW container which needs to be deleted unless a flag was specified. You can also optionally add a command to be run as soon as the container is initialised. Will pull a new image if the specified one is not locally available.

* Note: **-it** flag is needed for interacting with a terminal inside a container

```
docker container run [OPTIONS] IMAGE [COMMAND] [ARG...]

// Example
docker run --name my-nginx -p 9081:80 -d -v <your project path>:/usr/share/nginx/html nginx
```

### docker exec
Execute a command into an EXISTING container.

* Note: -it flag is needed for interacting with a terminal inside a container

```
docker container exec [OPTIONS] CONTAINER COMMAND [ARG...]

// Example
docker exec -it <container_id> bash
```

### docker start
```
docker start <container_id> or <container_name>
```

### docker stop
```
docker stop <container_id> or <container_name>

// Stop all containers
docker stop $(docker ps -a -q)
```

### docker tag
```
docker tag SOURCE_IMAGE[:TAG] TARGET_IMAGE[:TAG]
```

### docker build
```
docker build [dir]

docker build -t registry.gitlab.com/66010704/spdx-2025-66010704 .
```

### docker push
```
docker push [OPTIONS] NAME[:TAG]

docker push registry.gitlab.com/66010704/spdx-2025-66010704
```