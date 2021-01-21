FROM ubuntu:latest

RUN apt update \
 && apt upgrade -y \
 && DEBIAN_FRONTEND=noninteractive apt install -y software-properties-common \
 && DEBIAN_FRONTEND=noninteractive add-apt-repository ppa:deadsnakes/ppa \
 && apt update -y

RUN apt install -y \
    python3.9 \
    python3-pip \
    net-tools \
    inetutils-ping \
    wget

COPY requirements.txt ./
RUN pip3 install --no-cache-dir -r requirements.txt
RUN rm requirements.txt

COPY install.sh ./
RUN chmod +x install.sh
RUN bash install.sh
RUN echo 'eval "$(starship init bash)"' >> ~/.bashrc
RUN rm install.sh

RUN mkdir -p ~/.config
COPY .starship ~/.config/

RUN rm -rf /var/lib/apt/lists/*
