# Docker Version 1.6.2

FROM pritunl/archlinux

# variables
ENV APP="[app name]" 

# create a non-root user to run the app
RUN useradd -mrU http 

# install git, nginx, and node.js
RUN pacman -S git nginx node npm --noconfirm

# install source
RUN chown http:http /srv/http
RUN git clone git://10.200.4.201/"${APP}".git /home/"${USER}"/"${APP}"
RUN cd /home/"$USER"/"${APP}" && sudo -u "${USER}" npm install


