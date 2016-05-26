# Docker Version 1.10.2

FROM pritunl/archlinux

RUN pacman -S postfix
RUN echo "user@externalemail.com" > /root/.forward
RUN openssl dhparam -out /etc/ssl/dhparams.pem 2048
COPY conf/main.cf /etc/postfix/main.cf
