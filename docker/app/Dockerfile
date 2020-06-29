FROM php:7-fpm

ARG UID=1000
ARG GID=1000
RUN useradd -m -u ${UID} docker

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

RUN apt-get update && apt-get install -y git zip unzip

RUN apt-get update \
    && docker-php-ext-install pdo_mysql

USER ${UID}:${GID}

WORKDIR /var/www/html
