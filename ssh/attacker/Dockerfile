FROM jrei/systemd-ubuntu

# Instalacja SSH i dodatkowych narzędzi
RUN apt-get update && apt-get install -y openssh-server net-tools iproute2 inetutils-ping
RUN mkdir /var/run/sshd

# Dodanie użytkownika
RUN useradd -m -s /bin/bash user-server && \
    echo "user-server:test1234" | chpasswd

# Generowanie nowych kluczy hosta dla SSH
RUN rm /etc/ssh/ssh_host_*_key*
RUN dpkg-reconfigure openssh-server

# Ustawienie SSH do akceptowania połączeń
RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
EXPOSE 22

CMD ["/lib/systemd/systemd"]
