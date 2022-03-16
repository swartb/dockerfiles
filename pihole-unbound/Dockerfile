FROM pihole/pihole:latest

LABEL maintainer="swartb@me.com"
LABEL url="https://github.com/swartb/dockerfiles/main/dockerfile.pi-hole-unbound"

RUN apt-get update && \
    apt-get install unbound -y
  
RUN curl -o /etc/unbound/unbound.conf.d/pi-hole.conf https://raw.githubusercontent.com/swartb/dockerfiles/main/pihole-unbound/unbound-ph-hole.conf

RUN /etc/init.d/unbound start

ENV PIHOLE_DNS_1 127.0.0.1#5335
ENV REV_SERVER false
ENV DNSSEC false
ENV DNS_BOGUS_PRIV false
ENV DNS_FQDN_REQUIRED false
ENV DNSMASQ_LISTENING single
