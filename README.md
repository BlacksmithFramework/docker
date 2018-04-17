# Blacksmith

## Command line tool

Building
Running the local (development) environment
```
./dock build (container-name)
```

View STDOUT of container
```
./dock watch (container-name)
```

Running the local (development) environment
```
./dock dev (container-name)
```

Running the production environment detached
```
./dock start (container-name)
```

Switching to shell
```
./dock shell [container-name]
```

## Raw commands

### List Running Docker Containers
`docker ps`

### Connect to a Docker Container
`docker exec -it <CONTAINER ID>`

### Terminate a Docker Container
`docker kill <CONTAINER ID>`

### Build the Docker Compose Containers
This task is specific to Docker Compose (docker-compose.yml)

`docker-compose build`

### Build A Docker Compose Container By Name
`docker-compose build <CONTAINER NAME>`

### Deploy Docker Compose Stack
`docker-compose up -d`


#### Example commands
Open a shell to a named container called "nginx'

`docker exec -it nginx bash`

Running a command within a named the container

`docker exec -t nginx <command here>`

Checking the response from a named container

`docker exec -it nginx curl -ik https://localhost`

Rebuilding a named container

```
sudo su webapp
cd /home/webapp/
git pull origin develop
docker-compose build nginx
docker-compose stop nginx
docker-compose rm -f nginx
docker-compose up -d nginx
docker ps
```
OR

```
docker-compose build nginx && docker-compose stop nginx && docker-compose rm -f nginx && docker-compose up -d nginx && docker ps
```


Rebuild without cache

`docker-compose build --no-cache nginx`


Full rebuild

`docker-compose build && docker-compose stop && docker-compose rm -f && docker-compose up -d && docker ps`

Tail STDOUT and STDERR

`docker logs nginx --follow`

Prune
`docker system prune`
