# Ubuntu with nvm + node + npm + git + download repository

## Description

This docker image is the default Ubuntu image with the Node Version Manager (nvm), node + the Node Package Manager and git support.

## Versions

| Tag                | Ubuntu | nvm    | node    | npm   |
| ------------------ | ------ | ------ | ------- | ----- |
| `0.0.1` (`latest`) | 18.04  | 0.35.0 | 12.12.0 | 6.4.1 |

## Use this image

Add to your Dockerfile

```
FROM boldt/base-ubuntu-nvm-node-npm
```

## Build

(For own documentation)

### Build

1. Donwload this repo
2. Run

```
docker build -t your_docker_id/your_docker_name_repository
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
