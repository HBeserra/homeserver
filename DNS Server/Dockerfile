FROM ubuntu:bionic

ENV TZ=America/Sao_Paulo

EXPOSE 53 53/udp

RUN apt-get update \
  && apt-get install -y \
  dnsmasq 

COPY dnsmasq.conf  /etc/dnsmasq.conf

# Inicia o servidor DNS
CMD [ "/usr/sbin/dnsmasq", "--no-daemon" ]