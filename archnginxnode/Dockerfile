# Docker Version 1.6.2

FROM pritunl/archlinux

# variables
ENV APP="[app name]" REPO="[repo url]"

# install git, nginx, and node.js
RUN pacman -S sudo git nginx nodejs npm --noconfirm

# install source
RUN git clone git://"${REPO}"/"${APP}".git /srv/http/"${APP}"
RUN cd /srv/http/"${APP}" && npm install
RUN chown -R http:http /srv/http

# copy over nginx.conf
RUN rm /etc/nginx/nginx.conf
ADD nginx.conf /etc/nginx/nginx.conf

# create container with default command npm start
CMD /usr/bin/nginx && cd /srv/http/"${APP}" && sudo -u http npm start
