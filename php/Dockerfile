FROM php:5-fpm-alpine

RUN apk add --no-cache autoconf gcc g++ make
RUN yes | pecl install xdebug

COPY ./php.ini    /usr/local/etc/php/conf.d/php.ini
COPY ./xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini
