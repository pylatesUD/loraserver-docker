FROM centos:7

MAINTAINER Mainflux

WORKDIR /opt/lora/loraserver

ENV LORASERVER_VERSION=0.19.0
ENV DOCKERIZE_VERSION v0.3.0

ADD https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz dockerize.tar.gz
RUN tar -C /usr/local/bin -xzf dockerize.tar.gz && rm -f dockerize.tar.gz

ADD https://github.com/brocaar/loraserver/releases/download/${LORASERVER_VERSION}/loraserver_${LORASERVER_VERSION}_linux_amd64.tar.gz loraserver.tar.gz
RUN tar -xzf loraserver.tar.gz && rm -f loraserver.tar.gz

EXPOSE 8000

CMD ./loraserver
