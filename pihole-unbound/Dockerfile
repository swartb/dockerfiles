FROM pihole/pihole:latest

LABEL maintainer="swartb@me.com"
LABEL url="https://github.com/swartb/dockerfiles/main/dockerfile.pi-hole-unbound"

RUN apt-get update && \
    apt-get install unbound -y
  
RUN curl -o /etc/unbound/unbound.conf.d/pi-hole.conf https://github.com/swartb/dockerfiles/blob/main/pihole-unbound/unbound-ph-hole.conf
RUN curl -o /etc/pihole/setupVars.conf https://github.com/swartb/dockerfiles/blob/main/pihole-unbound/setupVars.conf

RUN /etc/init.d/unbound start
