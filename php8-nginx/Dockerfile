FROM alpine:3.17.0

EXPOSE 80
EXPOSE 443
STOPSIGNAL SIGTERM

RUN apk update && apk upgrade
RUN apk add bash
RUN apk add vim
RUN apk add nginx
RUN apk add freetype-dev libjpeg-turbo-dev libwebp-dev libpng-dev

## PHP extension modules
RUN apk add php81 
RUN apk add php81-fpm php81-opcache
RUN apk add php81-gd php81-zlib php81-curl
RUN apk add php81-mysqli
RUN apk add php81-mysqli
RUN apk add php81-phar

## Add wordpress cli
RUN wget -O /usr/local/bin/wp https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN chmod +x /usr/local/bin/wp

WORKDIR /var/www
COPY etc/nginx /etc/nginx
COPY etc/php /etc/php81
RUN mkdir /var/run/php

COPY start-nginx.sh /usr/local/bin/start-nginx
CMD ["start-nginx"]