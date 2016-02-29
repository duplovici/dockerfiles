# Docker Version 1.10.2

FROM pritunl/archlinux

# variables i.e. APP=docker-demo REPO=github.com/ndarwincorn
ENV APP="[app name]" REPO="[repo url]"

# install git and nginx
RUN pacman -S sudo git nginx --noconfirm

# install source
RUN git clone git://"${REPO}"/"${APP}".git /srv/http/"${APP}"
RUN chown -R http:http /srv/http

# copy over nginx.conf
RUN rm /etc/nginx/nginx.conf
ADD nginx.conf /etc/nginx/nginx.conf

# create container by running the nginx executable
CMD /usr/bin/nginx
