FROM solita/ubuntu-systemd

# Instalacja SSH
RUN apt-get update && apt-get install -y openssh-server iproute2 inetutils-ping
RUN mkdir /var/run/sshd

# Dodanie użytkownika
RUN useradd -m -s /bin/bash user-server && \
    echo "user-server:test1234" | chpasswd

# Ustawienie SSH do akceptowania połączeń i restart SSH
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
EXPOSE 22

CMD ["/usr/sbin/sshd", "-D"]
