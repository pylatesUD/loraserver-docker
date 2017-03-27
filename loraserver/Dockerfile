FROM golang:alpine

WORKDIR /opt/lora/loraserver

ENV LORASERVER_VERSION=0.15.1
ENV DOCKERIZE_VERSION v0.3.0

RUN apk update && apk add git && apk add wget && rm -rf /var/cache/apk/*

RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

ADD https://github.com/brocaar/loraserver/releases/download/${LORASERVER_VERSION}/loraserver_${LORASERVER_VERSION}_linux_amd64.tar.gz loraserver.tar.gz

RUN tar -xzf loraserver.tar.gz && rm -f loraserver.tar.gz

EXPOSE 8000

CMD ./loraserver
