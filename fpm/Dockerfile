FROM php:7.0-fpm

RUN apt-get update && apt-get install -y \
    libxml2-dev \
    zlib1g-dev \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng-dev \
    && docker-php-ext-install -j$(nproc) iconv mcrypt pdo pdo_mysql mysqli mbstring xml zip \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-install -j$(nproc) gd

#FROM php:7.1-fpm
#
#RUN apt-get update && apt-get install -y   apk upgrade && \
#    apk add --update --no-cache \
#    libcurl \
#    curl-dev \
#    libpng-dev \
#    libjpeg \
#    libjpeg-turbo-dev \
#    freetype-dev \
#    jpeg-dev \
#    libmcrypt-dev \
#    sqlite-dev \
#    libxml2-dev \
#    libintl \
#    icu-dev \
#    zlib-dev \
#    supervisor
#
## Install extra modules here
#RUN /usr/local/bin/docker-php-ext-install gd pdo pdo_mysql curl mcrypt mysqli mbstring pdo_sqlite xml intl zip \
#    && /usr/local/bin/docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/

