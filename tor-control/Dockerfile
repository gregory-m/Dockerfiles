FROM ubuntu
MAINTAINER Gregory Man <man.gregory@gmail.com>
RUN apt-get update && apt-get install -y tor && apt-get clean
VOLUME ["/opt/tor/hidden_services"]
ADD torrc /opt/tor/hidden_services/torrc
EXPOSE 9051
CMD tor --HashedControlPassword $TOR_CONTROL_PASSWD -f /opt/tor/hidden_services/torrc
