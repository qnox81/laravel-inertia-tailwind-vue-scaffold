FROM php:7.2-fpm-alpine

ADD ./docker/app/www.conf /usr/local/etc/php-fpm.d/www.conf

RUN addgroup -g 1000 laravel && adduser -G laravel -g laravel -s /bin/sh -D laravel

RUN mkdir -p /var/www

RUN chown laravel:laravel /var/www

WORKDIR /var/www

RUN apk add --update --no-cache net-snmp mariadb-client librrd libzip docker bash $PHPIZE_DEPS \
  && apk add --update --virtual .build-deps autoconf g++ make zlib-dev curl-dev rrdtool-dev net-snmp-dev libxml2-dev libzip-dev \
  && pecl channel-update pecl.php.net \
  && pecl install -o -f redis rrd xdebug-3.0.2 \
  && docker-php-ext-enable redis xdebug \
  && docker-php-ext-install pdo pdo_mysql mbstring opcache tokenizer xml pcntl sockets zip \
  && apk del .build-deps \
  && rm -rf /tmp/* \
  && addgroup laravel docker

