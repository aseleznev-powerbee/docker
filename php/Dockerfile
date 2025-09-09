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
RUN pecl install xdebug \
	&& docker-php-ext-install xdebug

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer