FROM php:8.0.23-fpm-alpine3.16

ENV PECL_EXTENSIONS="pcov psr redis exdebug"
ENV  PHP_EXTENSIONs="bz2 exif gd gettext intl pcntl pdo_mysql zip"

RUN apk add --no-cache --virtual .build-deps \
$PHPIZE_DEPS libtool \
&& apk add --no-cache bzip2-dev gettext-dev git icu icu-dev libintl libpng-dev libzip-dev mysql-client \
#  install and enable PECL extensions
&& docker-php-source extract \
&& pecl install $PECL_EXTENSIONS \
&& cd /usr/src/php/ext/ \
&& docker-php-ext-enable $PHP_EXTENSIONS \
&& docker-php-ext-configure opcache --enable-opcache \
# install and enable PHP EXTENSIONS
&& docker-php-ext-install -j "$(nproc)" $PHP_EXTENSIONS \
# clean up
&& apk del -f .build-deps \ 
&& cd /usr/local/etc/php/conf.d/ \
&& pecl clear-cache \
&& docker-php-source delete \
&& rm -rf /var/cache/apk/* /tmp/* /usr/share/doc/* /usr/share/man/*

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html
USER www-data