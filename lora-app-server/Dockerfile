FROM centos:7

WORKDIR /opt/lora/lora-app-server

ENV LORA_APP_SERVER 0.10.0
ENV DOCKERIZE_VERSION v0.3.0

ADD https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz dockerize.tar.gz
RUN tar -C /usr/local/bin -xzf dockerize.tar.gz && rm -f dockerize.tar.gz

ADD https://github.com/brocaar/lora-app-server/releases/download/${LORA_APP_SERVER}/lora_app_server_${LORA_APP_SERVER}_linux_amd64.tar.gz lora-app-server.tar.gz
ADD certs certs
RUN tar -xzf lora-app-server.tar.gz && rm -f lora-app-server.tar.gz

EXPOSE 8001

CMD ./lora-app-server
