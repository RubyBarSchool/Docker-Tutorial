# <img src="https://img.icons8.com/color/2x/docker.png" alt="Docker icon" width="100" height="80"> Docker Tutorial
#### Docker Tutorial for Beginner

## [Website docker](https://docs.docker.com/)
## Docker architecture (C) Docker Inc.
<img src="./image/docker-architecture.png" alt="Docker architecture" >

## Docker component interaction ( (C) Luis Herrera Benítez )

<img src="./image/docker-component-interaction.png" alt="Docker component interaction" >

## Docker CLI
#### Docker pull
``` powershell
 docker pull [OPTIONS] NAME[:TAG|@DIGEST]
 # example redis
 docker pull redis
 docker pull redis:latest
 docker pull redis:4.0
```
#### Architecture Docker pull
```powershell
TERMINAL =====> DOCKER CLI =====> DOCKER HOST ( DOCKER DAEMON ) === CHECK CACHE NO ===>  DOCKER HUB ( Registry ) === 
                                                               ||                                                 ||
                                                               ||                                                 ||
                                                         CHECK CACHE YES                                          ||
                                                               ||                                                 ||
                                                               ||==========================================  DOCKER IMAGE ( DISK )
                                                                                                                  ||
                                                                                                                  ||
                                                                                                            BUILD CONTAINER ( DOCKER DAEMON check cache )
                                                                                                                  ||
                                                                                                                  ||
                                                                                                            DOCKER CONTAINER
```

#### Docker run
``` powershell
 docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
 # example redis
 docker run --name my-redis -d redis:latest
```
