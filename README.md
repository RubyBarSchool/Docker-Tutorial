# <img src="https://img.icons8.com/color/2x/docker.png" alt="Docker icon" width="100" height="80"> Docker Tutorial
#### Docker Tutorial for Beginner

## [Website docker](https://docs.docker.com/)
## Docker architecture (C) Docker Inc.
<img src="./image/docker-architecture.png" alt="Docker architecture" >

## Docker component interaction ( (C) Luis Herrera Benítez )

<img src="./image/docker-component-interaction.png" alt="Docker component interaction" >

## Docker CLI ( [url](https://docs.docker.com/engine/reference/run/) )

#### Docker managing image
``` powershell
 docker image ls
 docker images
 
 Usage:  docker image COMMAND
 Commands:
  build       Build an image from a Dockerfile
  history     Show the history of an image
  import      Import the contents from a tarball to create a filesystem image
  inspect     Display detailed information on one or more images
  load        Load an image from a tar archive or STDIN
  ls          List images
  prune       Remove unused images
  pull        Pull an image or a repository from a registry
  push        Push an image or a repository to a registry
  rm          Remove one or more images
  save        Save one or more images to a tar archive (streamed to STDOUT by default)
  tag         Create a tag TARGET_IMAGE that refers to SOURCE_IMAGE

Run 'docker image COMMAND --help' for more information on a command.
```

#### Docker managing container

``` powershell
 docker ps
 docker images
 
Usage:  docker container COMMAND

Manage containers

Commands:
  attach      Attach local standard input, output, and error streams to a running container
  commit      Create a new image from a container's changes
  cp          Copy files/folders between a container and the local filesystem
  create      Create a new container
  diff        Inspect changes to files or directories on a container's filesystem
  exec        Run a command in a running container
  export      Export a container's filesystem as a tar archive
  inspect     Display detailed information on one or more containers
  kill        Kill one or more running containers
  logs        Fetch the logs of a container
  ls          List containers
  pause       Pause all processes within one or more containers
  port        List port mappings or a specific mapping for the container
  prune       Remove all stopped containers
  rename      Rename a container
  restart     Restart one or more containers
  rm          Remove one or more containers
  run         Run a command in a new container
  start       Start one or more stopped containers
  stats       Display a live stream of container(s) resource usage statistics
  stop        Stop one or more running containers
  top         Display the running processes of a container
  unpause     Unpause all processes within one or more containers
  update      Update configuration of one or more containers
  wait        Block until one or more containers stop, then print their exit codes

Run 'docker container COMMAND --help' for more information on a command.
```

#### Docker pull
``` powershell
 docker pull [OPTIONS] NAME[:TAG|@DIGEST]
 
 Pull an image or a repository from a registry

Options:
  -a, --all-tags                Download all tagged images in the repository
      --disable-content-trust   Skip image verification (default true)
      --platform string         Set platform if server is multi-platform
                                capable
  -q, --quiet                   Suppress verbose output
  
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

#### Docker port
``` powershell
  docker run -p portlocal:portcontainer [container]
 # example nginx single port
 docker run -p 3000:80 nginx 
 # example nginx multiple ports
 docker run -p 3000:80 -p 3030:80 nginx
```
