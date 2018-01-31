# youtube-dl

Run youtube-dl inside docker.

[youtube-dl](http://rg3.github.io/youtube-dl/) is a command-line program to download videos from YouTube.com and a few [more sites](http://rg3.github.io/youtube-dl/supportedsites.html).

## Docker setup

Install docker: https://docs.docker.com/engine/installation/

Install docker compose: https://docs.docker.com/compose/install/

Docker documentation: https://docs.docker.com/

## Usage

### Build-in docker image

- build docker image `docker build -t youtube-dl .`

- list youtube-dl options: `docker run youtube-dl --help`

- download a video: `docker run --rm -v $(pwd):/media youtube-dl https://www.youtube.com/watch?v=JYwUUDdYi9I`

### Docker Hub image

- pull docker image from docker hub: `docker pull kijart/youtube-dl`

- download a video using docker image: `docker run --rm -v $(pwd):/media kijart/youtube-dl https://www.youtube.com/watch\?v\=JYwUUDdYi9I`

- create a docker container

```
docker create \
  --name=youtube-dl \
  -v <path to data>:/media \
  kijart/youtube-dl
```

### Docker compose

- create a container using docker-compose: `docker-compose up --no-start`

- download a video using docker compose: `docker-compose run youtube-dl https://www.youtube.com/watch\?v\=JYwUUDdYi9I`

## More info

- youtube-dl command-line [options documentation](https://github.com/rg3/youtube-dl#options)
