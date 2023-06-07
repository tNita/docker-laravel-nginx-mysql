FROM php:8.1-fpm
COPY php.ini /usr/local/etc/php/

RUN apt update
RUN apt install -y wget git unzip libpq-dev

# Install PHP Extensions
RUN apt install -y zlib1g-dev mariadb-client libzip-dev libonig-dev \
    && docker-php-ext-install zip pdo_mysql

COPY --from=composer /usr/bin/composer /usr/bin/composer

RUN composer global require "laravel/installer"