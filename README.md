# Aternos Thanos. Now on Docker
Not affiliated with aternos.org in any way

### PHP library to automatically detect and remove unused chunks from Minecraft worlds. Now on Docker.

[Official Repo](https://github.com/aternosorg/)

[Docker Hub Link](https://hub.docker.com/repository/docker/cristianeduardmihai/thanos)

## Make sure the world you want to optimize is in the `watch` folder before starting. This container is not meant to run continuously.

## Run:
- Docker CLI
```
docker run \
  --name=Thanos \
  -e TZ=Europe/London \  #Optional, doesn't really matter
  -v /path/to/world:/watch \ #path to your unoptimized world folder
  -v /path/to/output:/output \ #path to the folder you want your optimized world to be exported. Must be empty
  cristianeduardmihai/thanos
```
- Docker Compose
```
---
version: "2.1"
services:
  thanos:
    image: cristianeduardmihai/thanos
    container_name: Thanos
    environment:
      - TZ=Europe/London
    volumes:
      - /path/to/world:/watch
      - /path/to/output:/output
```