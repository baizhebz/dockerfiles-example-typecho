FROM php:7-fpm

ADD sources.list /etc/apt/sources.list
ADD php-fpm.conf /usr/local/etc/php-fpm.conf

RUN apt-get update && apt-get install -y \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libmcrypt-dev \
        libpng12-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd \
    && docker-php-ext-install pdo_mysql

WORKDIR /data/wwwroot/

RUN usermod -u 1000 www-data

EXPOSE 9000
VOLUME ["/data"]
