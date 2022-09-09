FROM php:8.0.23-fpm-alpine3.16

RUN docker-php-ext-install pdo_mysql
COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www
USER www-data