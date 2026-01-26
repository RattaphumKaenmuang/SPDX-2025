# Docker Compose
* Orchestration tool for running multi-container programs
* Write a script via a .yaml file
* Each service (container) in the program can now talk to each other using the container name
* Builds/pulls the images (if missing) -> Run as containers with specified settings and configs (port forwarding, image, etc.) -> Set all containers to be in the same network

## Scripts and Commands

### Basic docker-compose.yaml Script

```
services:
  hello:
    image: nginx:alpine
    ports:
      - 9085:80
    
  mydb:
    image: mysql:latest
    environment:
      - MYSQL_ROOT_PASSWORD=12345678

  myadmin:
    image: phpmyadmin/phpmyadmin
    ports:
      - 9082:80
    environment:
      - PMA_HOST=mydb

  my-app:
    build:
    context: .
    dockerfile: Dockerfile
    ports:
    - 9083:80
```

* Define services (containers)
  
  * Service named "hello"
    * hello will use **nginx:alpine** as the image
    * hello has a port forwarding rule to connect **port 9085 (outside the container) to 80 (inside the container)**
    * For normal Docker commands, this is equivalent to
  
        ```
        docker run --name hello -p 9085:80 nginx:alpine
        ```

  * Service named "mydb"
    * mydb will use **mysql:latest** as the image
    * mydb has an environment variable called **"MYSQL_ROOT_PASSWORD"** which is set to **"12345678"**
    * For normal Docker commands, this is equivalent to
  
        ```
        docker run --name mydb -e MYSQL_ROOT_PASSWORD=12345678 -d --network my-net mysql:latest
        ```

  * Service named "myadmin"
    * myadmin will use **phpmyadmin/phpmyadmin** as the image
    * myadmin has a port forwarding rule to connect **port 9082 (outside the container) to 80 (inside the container)**
    * myadmin has an environemnt variable called **"PMA_HOST"** which is set to **"mydb"**
    * For normal Docker commands, this is equivalent to

        ```
        docker run --name myadmin -d --network my-net -e PMA_HOST=mydb -p 9082:80 phpmyadmin/phpmyadmin
        ```

  * Service named "my-app"
    * my-app does not have an image to pull from, but will try to find a dockerfile named **"Dockerfile"** in the **current directory (.)** to build it from
    * my-app has a port forwarding rule to connect **port 9083 (outside the container) to 80 (inside the container)**

### Commands
#### docker compose up
Pull or build all the needed images then up all the containers in the "detached mode" (Does not consume the shell)

```
docker compose up -d
```

##### Important Flags
```
-d                      Up the containers in "detached" mode which doesn't take over the shell to show the output
--build                 Build images before starting containers
--force-recreate        Force build/recreate containers even if the image exists and hasn't changed
```

#### docker compose ps
Show all running containers (Only those made by compose, not from normal Docker)
```
docker compose ps
```

##### Important Flags
```
-a                      Show all containers, including stopped ones
--services              Display services
```