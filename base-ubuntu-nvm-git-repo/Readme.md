# Ubuntu with nvm + node + npm + git + download repository

[![Gitlab](https://img.shields.io/static/v1.svg?label=Get%20the%20source%20code%20on&message=Github&color=555&style=flat&logo=github)](https://github.com/faifumo-dockerfiles/tree/master/base-ubuntu-nvm-git-repo/)
[![Docker Hub](https://img.shields.io/static/v1.svg?label=Get%20the%20container%20on&message=Docker%20Hub&color=555&style=flat&logo=docker)](https://hub.docker.com/r/quelicm/faifumo-base-ubuntu-nvm-git/)
[![Docker Pulls](https://img.shields.io/docker/pulls/quelicm/faifumo-base-ubuntu-nvm-git.svg)](https://hub.docker.com/r/quelicm/faifumo-base-ubuntu-nvm-git/)

## Description

This docker image is the default Ubuntu image with the Node Version Manager (nvm), node + the Node Package Manager and git support.

## Versions

| Tag                | Ubuntu | nvm    | node    | npm   |
| ------------------ | ------ | ------ | ------- | ----- |
| `0.0.1`            | 18.04  | 0.35.0 | 12.12.0 | 6.4.1 |
| `0.0.2` (`latest`) | 18.04  | 0.35.0 | 12.16.2 | 6.4.1 |

## Use this image

Add to your Dockerfile

```
FROM quelicm/faifumo-base-ubuntu-nvm-git
```

## Build

(For own documentation)

### Build

1. Donwload this repo and change into the directory `base-ubuntu-nvm-git-repo`

```
cd base-ubuntu-nvm-git-repo
```

2. Run

```
docker build -t your_docker_id/your_docker_name_repository .
```

3. Check your image is builded

```
docker images
```

### Options to build

You can customize the following versions:

- **node_version** Node version (12.12.0 by default)
- **nvm_version** NVM version (0.35.0 by default)
- **git_repository** Custom repository url (Currently only works with https urls)

You can pass the options with `--build-arg node_version=v12.11.1`

```
docker build --build-arg node_version=v12.11.1 -t your_docker_id/your_docker_name_repository
```

## Test the build

1. Download the image from docker hub

```
docker pull quelicm/faifumo-base-ubuntu-nvm-git:0.0.1
```

2. Run the image

```
docker run -p 4000:3000 quelicm/faifumo-base-ubuntu-nvm-git:0.0.1
```

3. Show the project in your browser in http://localhost:4000
