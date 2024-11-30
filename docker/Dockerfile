FROM ubuntu:24.04

RUN apt-get update && apt-get install -y \
    openssh-server \
    python3 \
    python3-pip \
    sudo && \
    mkdir /var/run/sshd && \
    echo 'root:password' | chpasswd && \
    sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config && \
    service ssh start

RUN pip3 install ansible

CMD ["/usr/sbin/sshd", "-D"]
