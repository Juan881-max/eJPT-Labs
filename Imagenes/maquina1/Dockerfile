FROM debian:latest

RUN apt update && apt upgrade -y

RUN  useradd -m -s /bin/bash jack && echo "jack:123456" | chpasswd

RUN  useradd -m -s /bin/bash ana && echo "ana:qwert" | chpasswd

RUN  useradd -m -s /bin/bash nico && echo "nico:abcdef" | chpasswd

RUN apt install -y apache2 vsftpd sudo python3 openssh-server

RUN echo "eJPT{$(echo 'root' | md5sum | cut -d' ' -f1)}" > /root/flag.txt

RUN echo "jack ALL=(ana) NOPASSWD: /usr/bin/python3" >> /etc/sudoers

RUN echo "ana ALL=(nico) NOPASSWD: /usr/bin/env" >> /etc/sudoers

RUN echo "nico ALL=(root) NOPASSWD: /usr/bin/bash" >> /etc/sudoers

RUN mkdir -p /var/run/sshd 

RUN sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

COPY secret.html /var/www/html/secret.html 

RUN chmod 400 /root/flag.txt && chown root:root /root/flag.txt 

EXPOSE 80 22 21

CMD service apache2 start && service ssh start && service vsftpd start && tail -f /dev/null
