# Docker-Tutorial

```install Docker from docker site ```

# Docker Container 

Docker container is running environment for IMAGES

### IMAGES
->redis
->mongodB

## Example

```docker pull redis``` Redis is image and pulled from docker hub
```docker run redis ``` Redis will run in a container now
```docker images```

REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
redis        latest    f16c30136ff3   2 weeks ago   107MB

```docker  run -d redis``` Run redis in dittached mode

```docker ps``` to see running container

CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS      NAMES
9b6ab153633f   redis     "docker-entrypoint.s…"   26 seconds ago   Up 25 seconds   6379/tcp   modest_wright

## To stop Container
```docker stop 9b6ab153633f``` 

## Docker run Specific port of the HOST (PC/LAP)

```docker run -p8000:6379 redis```



CONTAINER ID   IMAGE     COMMAND                  CREATED          STATUS          PORTS                                       NAMES
d2b1bdb93b51   redis     "docker-entrypoint.s…"   17 seconds ago   Up 17 seconds   0.0.0.0:8000->6379/tcp, :::8000->6379/tcp   gracious_mirzakhani

## Running Image With custom Name

```docker  run --name myredis -d redis```


# MongoDB  & Express Using Docker

```docker pull mongo```
```docker pull mongo-express```

## Docker Network

```docker network ls ``` (Auto genarated network)

Using Docker network we can connect express and mongo using name

#### Creating Custom Network
```docker network create mongo-network```

#### Running Mongo in network 
```docker run -p 27017:27017 -d -e MONGO_INITDB_ROOT_USERNAME=admin -e MONGO_INITDB_ROOT_PASSWORD=password --name mongodb --net mongo-network mongo```

#### Running Mongo Express in same Network 

```
docker run -d \
    --network mongo-network \
    --name mongo-express\
    -p 8081:8081 \
    -e ME_CONFIG_OPTIONS_EDITORTHEME=ambiance \
    -e ME_CONFIG_MONGODB_SERVER=mongodb\
    -e ME_CONFIG_MONGODB_ADMINUSERNAME=admin \
    -e ME_CONFIG_MONGODB_ADMINPASSWORD=admin \
    -e ME_CONFIG_BASICAUTH_USERNAME=admin\
    -e ME_CONFIG_BASICAUTH_PASSWORD=admin \
    mongo-express

```
Now Mongo Express is Available in host on localhost:8081



