FROM golang:alpine

WORKDIR /opt/lora/lora-gateway-bridge

ENV LORA_GATEWAY_BRIDGE 2.1.4
ENV DOCKERIZE_VERSION v0.3.0

RUN apk update && apk add git && apk add wget && rm -rf /var/cache/apk/*

RUN wget https://github.com/jwilder/dockerize/releases/download/$DOCKERIZE_VERSION/dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && tar -C /usr/local/bin -xzvf dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz \
    && rm dockerize-linux-amd64-$DOCKERIZE_VERSION.tar.gz

ADD https://github.com/brocaar/lora-gateway-bridge/releases/download/${LORA_GATEWAY_BRIDGE}/lora_gateway_bridge_${LORA_GATEWAY_BRIDGE}_linux_amd64.tar.gz lora-gateway-bridge.tar.gz

RUN tar -xzf lora-gateway-bridge.tar.gz && rm -f lora-gateway-bridge.tar.gz

EXPOSE 1700

CMD ./lora-gateway-bridge
