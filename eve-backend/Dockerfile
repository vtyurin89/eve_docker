FROM php:8.3-fpm

WORKDIR /var/www

RUN apt-get update && apt-get install -y \
        apt-utils \
        libpng-dev \
        libzip-dev \
        zip unzip \
        git && \
        docker-php-ext-install pdo_mysql && \
        docker-php-ext-install bcmath && \
        docker-php-ext-install gd && \
        docker-php-ext-install zip && \
        apt-get clean && \
        rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

COPY ../../eve-backend/ ./

ENV COMPOSER_ALLOW_SUPERUSER=1
RUN curl -sS https://getcomposer.org/installer | php -- \
    --filename=composer \
    --install-dir=/usr/local/bin

