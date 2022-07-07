FROM php:7.3-fpm

# cài đặt và kích hoạt opcache, mysqli, pdo_mysql, memcached

RUN apt-get update -y \
    && apt-get install libzip-dev zip libmemcached-dev  -y \
    && apt-get install vim -y \
    && apt-get install htop \
    && docker-php-ext-install zip opcache mysqli pdo_mysql \
    && docker-php-ext-enable mysqli \
    && docker-php-ext-enable opcache \
    && docker-php-ext-enable pdo_mysql \
    && pecl install memcached \
    && rm -rf /var/lib/apt/lists/*


ADD ./php.ini /usr/local/etc/php/php.ini

EXPOSE 9000

# CMD [ "httpd-foreground"]