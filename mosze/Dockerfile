FROM ubuntu:20.04

RUN apt update \
 && DEBIAN_FRONTEND=noninteractive apt install -y \
  make \
  cmake \
  cppcheck \
  g++ \
  git \
  valgrind \
&& rm -rf /var/lib/apt/lists/*