FROM php:7.4.12-fpm-buster

RUN apt-get update && apt-get install -y --no-install-recommends \
        git \
        zlib1g-dev \
        libxml2-dev \
        libzip-dev \
        libicu-dev \
        libpng-dev \
        libpq-dev \
    && pecl install xdebug \
    && docker-php-ext-enable xdebug \
    && docker-php-ext-install \
        zip \
        intl \
        exif \
        gd \
        pgsql pdo pdo_pgsql pdo_mysql \
    && rm -rf /var/lib/apt/lists/*

ADD ./php.ini /usr/local/etc/php/php.ini

COPY conf.d/ /usr/local/etc/php/conf.d

RUN curl -sS https://getcomposer.org/installer | php && mv composer.phar /usr/local/bin/composer

ARG user_name

RUN useradd --create-home --shell /bin/bash $user_name

WORKDIR /srv
