FROM ubuntu:latest

RUN apt update \
 && apt upgrade -y \
 && apt install -y software-properties-common \
 && add-apt-repository ppa:deadsnakes/ppa \
 && apt update -y

RUN apt install -y \
    python3.6 \
    python3-pip \
    bash \
    wget \
    git \
    nano

COPY requirements.txt ./
RUN python3.6 -m pip install --no-cache-dir -r requirements.txt
RUN rm requirements.txt

RUN python3.6 -m pip install --user --upgrade tensorflow==1.12.0

RUN apt install -y libopencv-dev python3-opencv

#COPY ai ./

RUN rm -rf /var/lib/apt/lists/*

#RUN export PYTHONPATH=models-r1.12.0:models-r1.12.0/research/:models-r1.12.0/research/slim/