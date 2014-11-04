FROM ubuntu
MAINTAINER Gregory Man <man.gregory@gmail.com>
RUN apt-get update && apt-get install -y tor && apt-get clean
ADD torrc /etc/tor/torrc
EXPOSE 9051
VOLUME ["/opt/tor/hidden_services"]
CMD tor --HashedControlPassword $TOR_CONTROL_PASSWD
