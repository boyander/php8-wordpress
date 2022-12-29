FROM alpine:3.17.0

EXPOSE 80
EXPOSE 443
STOPSIGNAL SIGTERM

RUN apk update && apk upgrade
RUN apk add bash
RUN apk add nginx
RUN apk add freetype-dev libjpeg-turbo-dev libwebp-dev libpng-dev
RUN apk add php81 
RUN apk add php81-fpm php81-opcache
RUN apk add php81-gd php81-zlib php81-curl
RUN apk add php81-mysqli

COPY etc/nginx /etc/nginx
COPY etc/php /etc/php81
RUN mkdir /var/run/php

COPY start-nginx.sh /usr/local/bin/start-nginx
CMD ["start-nginx"]