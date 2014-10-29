FROM ruby
MAINTAINER  Gregory Man <man.gregory@gmail.com>

RUN gem install --no-ri --no-rdoc geminabox thin &&\
    mkdir -p /opt/geminabox/
ADD config.ru /opt/geminabox/config.ru
EXPOSE  9292
VOLUME  ["/opt/geminabox/data"]
WORKDIR /opt/geminabox
CMD ["rackup", "-o", "0.0.0.0"]
