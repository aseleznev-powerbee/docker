FROM namoshek/php-mssql:8.2-fpm
WORKDIR /var/www/html

RUN apt-get update && apt-get install -y \
                git \
                libzip-dev \
                libpng-dev \
                libxml2-dev \
                zip \
                unzip \
	&& docker-php-ext-install xml mysqli zip gd
COPY xdebug/xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini
RUN pecl install xdebug \
    && echo "zend_extension=$(find /usr/local/lib/php/extensions/ -name xdebug.so)" >> /usr/local/etc/php/conf.d/xdebug.ini

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer