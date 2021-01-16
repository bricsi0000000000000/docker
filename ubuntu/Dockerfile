FROM ubuntu:latest

RUN apt update \
 && apt upgrade -y \
 && apt install -y \
    bash \
    wget \
    git \
    nano

COPY install.sh ./
RUN chmod +x install.sh
RUN bash install.sh
RUN echo 'eval "$(starship init bash)"' >> ~/.bashrc
RUN rm install.sh

RUN mkdir -p ~/.config
COPY .starship.toml ~/.config/

RUN rm -rf /var/lib/apt/lists/*