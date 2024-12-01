FROM ubuntu:24.04

RUN apt-get update && \
    apt-get install -y \
    openssh-server \
    sudo \
    htop \
    ncdu \
    git \
    nano && \
    apt-get clean

RUN mkdir /var/run/sshd

RUN useradd -m ansibleuser && echo "ansibleuser:password" | chpasswd && adduser ansibleuser sudo

EXPOSE 22

WORKDIR /workspace

CMD ["/usr/sbin/sshd", "-D"]
