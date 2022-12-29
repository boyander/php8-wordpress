FROM php:8-apache
MAINTAINER marc@faable.com

RUN apt-get update && apt-get install --no-install-recommends -y \
    wget \
    nano \
    git \
    unzip \
    iputils-ping \
    libzip-dev \  
    libjpeg-dev \
    zlib1g-dev \
    libpng-dev \
    libwebp-dev \
    libfreetype-dev 


RUN a2enmod rewrite
RUN a2enmod headers
RUN docker-php-ext-install -j$(nproc) mysqli
RUN docker-php-ext-enable mysqli
RUN docker-php-ext-configure gd --with-freetype --with-webp --with-jpeg && \
    docker-php-ext-install gd -j$(nproc)
RUN chown -R www-data:www-data /var/www
ADD ./000-default.conf /etc/apache2/sites-available/000-default.conf

COPY start-apache.sh /usr/local/bin/start-apache
CMD ["start-apache"]
EXPOSE 80