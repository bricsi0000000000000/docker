FROM ubuntu:20.04

RUN apt update \
 && DEBIAN_FRONTEND=noninteractive apt install -y \
    make \
    cmake \
    git \
    libgtest-dev \
    gcc g++ \
 && cd /usr/src/gtest \
 && cmake CMakeLists.txt \
 && make \
 && ln -st /usr/lib/ /usr/src/gtest/libgtest.a \
 && ln -st /usr/lib/ /usr/src/gtest/libgtest_main.a \
 && rm -rf /var/lib/apt/lists/*