# FROM ubuntu/bind9
FROM ubuntu:bionic

ENV TZ=America/Sao_Paulo

EXPOSE 53 53/udp


RUN apt-get update \
  && apt-get install -y \
  dnsutils \
  iputils-ping \
  dnsmasq

# Enable IPv4
# RUN sed -i 's/OPTIONS=.*/OPTIONS="-4 -u bind"/' /etc/default/bind9

# Copy configuration files
# COPY named.conf.options /etc/bind/
# COPY named.conf.local /etc/bind/
# COPY zones/ /etc/bind/zones/

COPY dnsmasq.conf  /etc/dnsmasq.conf

# Run eternal loop
CMD [ "/usr/sbin/dnsmasq", "--no-daemon" ]