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

