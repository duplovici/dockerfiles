# Docker Version 1.6.2

FROM pritunl/archlinux

# variables
ENV APP="[app name]"

# install git, nginx, and node.js
RUN pacman -S git nginx node npm --noconfirm

# install source
RUN git clone git://10.200.4.201/"${APP}".git /srv/http/"${APP}"
RUN cd /srv/http/"${APP}" && npm install
RUN chown -R http:http /srv/http

# copy over nginx.conf
RUN rm /etc/nginx/nginx.conf
ADD nginx.conf /etc/nginx/nginx.conf

# enable/start nginx
RUN systemctl enable nginx
RUN systemctl start nginx

# create container with default command npm start
CMD cd /srv/http/"${APP}" && sudo -u http npm start
