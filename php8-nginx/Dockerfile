FROM alpine:3.22.2

EXPOSE 80
EXPOSE 443
STOPSIGNAL SIGTERM

RUN apk update && apk upgrade
RUN apk add bash
RUN apk add vim
RUN apk add nginx
RUN apk add freetype-dev libjpeg-turbo-dev libwebp-dev libpng-dev
RUN apk add imagemagick
RUN apk add htop

## PHP extension modules
RUN apk add php84 
RUN apk add php84-fpm 
RUN apk add php84-opcache
RUN apk add php84-gd 
RUN apk add php84-zlib 
RUN apk add php84-curl
RUN apk add php84-mysqli
RUN apk add php84-pdo_pgsql
RUN apk add php84-phar
RUN apk add php84-simplexml
RUN apk add php84-dom
RUN apk add php84-xml
RUN apk add php84-xmlwriter
RUN apk add php84-xmlreader
RUN apk add php84-zip
RUN apk add php84-xsl
RUN apk add php84-exif
RUN apk add php84-fileinfo
RUN apk add php84-intl
RUN apk add php84-pecl-imagick
RUN apk add php84-ctype
RUN apk add php84-pecl-redis

# Required by wp-cli
RUN apk add php84-iconv
RUN apk add mysql-client 

## Add wordpress cli
RUN wget -O /usr/local/bin/wp https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar
RUN chmod +x /usr/local/bin/wp

WORKDIR /var/www
COPY etc/nginx /etc/nginx
COPY etc/php /etc/php84
RUN mkdir /var/run/php

COPY start-nginx.sh /usr/local/bin/start-nginx
CMD ["start-nginx"]