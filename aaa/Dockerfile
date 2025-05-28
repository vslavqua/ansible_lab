FROM debian:11

RUN apt-get update && apt-get install -y \
    openssh-server sudo iproute2 iputils-ping systemd vim curl \
    && mkdir /var/run/sshd \
    && useradd -m -s /bin/bash ansible \
    && echo "ansible:ansible" | chpasswd \
    && echo "ansible ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers \
    && sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config \
    && echo "root:root" | chpasswd

EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]
