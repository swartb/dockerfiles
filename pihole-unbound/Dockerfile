FROM pihole/pihole:latest

LABEL maintainer="swartb@me.com"
LABEL url="https://github.com/swartb/dockerfiles/tree/main/pihole-unbound"


# install unbound
RUN apt-get update && \
    apt-get install unbound -y

# copy unbound config file and start unbound
RUN curl -o /etc/unbound/unbound.conf.d/pi-hole.conf https://raw.githubusercontent.com/swartb/dockerfiles/main/pihole-unbound/unbound-pi-hole.conf
RUN curl -o /root/start-unbound.sh https://raw.githubusercontent.com/swartb/dockerfiles/main/pihole-unbound/start-unbound.sh
RUN chmod +x /root/start-unbound.sh

# configuration
ENV TZ Europe/Amsterdam
ENV DNS1 127.0.0.1#5335

ENTRYPOINT /root/start-unbound.sh
