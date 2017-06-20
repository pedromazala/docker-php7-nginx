FROM php:7.1-fpm

RUN apt-get update && apt-get install -y \
         libfreetype6-dev \
         libjpeg62-turbo-dev \
         libmcrypt-dev \
         libpng12-dev \
     && docker-php-ext-install -j$(nproc) iconv mcrypt \
     && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
     && docker-php-ext-install -j$(nproc) gd \
     && apt-get install -y zlib1g-dev \
     && rm -rf /var/lib/apt/lists/* \
     && docker-php-ext-install zip \
     && docker-php-ext-install pdo pdo_mysql
