FROM ubuntu:22.04

ENV DEBIAN_FRONTEND=noninteractive

RUN apt-get update && apt-get install -y \
    nginx \
    wget \
    unzip \
    && apt-get clean

WORKDIR /app

RUN wget http://v04.adtec.ovh/server/VCMP04_server_v39_linux64.zip \
    && unzip VCMP04_server_v39_linux64.zip \
    && rm VCMP04_server_v39_linux64.zip

RUN chmod 777 mpsvrrel64

EXPOSE 80

CMD ["/bin/bash", "-c", "nginx && ./mpsvrrel64 -allow-server-runas-root"]
