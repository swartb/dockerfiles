FROM pihole/pihole:latest

LABEL maintainer="swartb@me.com"
LABEL url="https://github.com/swartb/dockerfiles/main/dockerfile.pi-hole-unbound"


# install unbound
RUN apt-get update && \
    apt-get install unbound -y

# copy unbound config file and start unbound
RUN curl -o /etc/unbound/unbound.conf.d/pi-hole.conf https://raw.githubusercontent.com/swartb/dockerfiles/main/pihole-unbound/unbound-ph-hole.conf
RUN /etc/init.d/unbound start

# configuration
ENV TZ Europe/Amsterdam
ENV DNS1 127.0.0.1#5335
