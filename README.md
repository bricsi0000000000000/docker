# Docker

## Commands

### Build

`docker build -t doxygen .`

### Push

Before you could push, you have to add a tag.

`docker tag doxygen:latest bricsi/doxygen`

`docker push bricsi/doxygen`

### Run

`docker run -it --rm google_test`

`-it`: Run in foreground.
`--rm`: Delete after exit.

Run with attached folder: `docker run -it --rm -v E:\programming\c++\mosze\console-RPG1\tests:/tests google_test`

### See images

`docker images`

### See running containers

`docker ps -a`

### Delete image

`docker rmi google_test`

## Examples

```Dockerfile
FROM ubuntu:20.04

RUN apt update \
 && DEBIAN_FRONTEND=noninteractive apt install -y \
  make \
  cmake \
  cppcheck \
  g++ \
  doxygen \
  graphviz \
  git \
&& rm -rf /var/lib/apt/lists/*
```

Define the operating system:

```Dockerfile
FROM ubuntu:20.04
```

Update everything to later be able to install apps:

```Dockerfile
RUN apt update
```

Install app without asking and automatically say yes:

```Dockerfile
DEBIAN_FRONTEND=noninteractive apt install -y
```

Remove cache:

```Dockerfile
rm -rf /var/lib/apt/lists/*
```

To type a new line, you need to put this character at the end of the line: `\`
