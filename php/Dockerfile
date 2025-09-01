FROM php:8.2-fpm
#WORKDIR /var/www/html
#COPY . /var/www/html

# Install any necessary PHP extensions (e.g., mysqli, pdo_mysql)

RUN apt-get update && apt-get install -y \
                git \
                libzip-dev \
                libpng-dev \
                unixodbc-dev \
                libxml2-dev \
                zip \
                unzip \
	&& docker-php-ext-install xml mysqli zip gd \
        && pecl install sqlsrv \
        && pecl install pdo_sqlsrv \
        && echo extension=pdo_sqlsrv.so >> `php --ini | grep "Scan for additional .ini files" | sed -e "s|.*:\s*||"`/10_pdo_sqlsrv.ini \
        && echo extension=sqlsrv.so >> `php --ini | grep "Scan for additional .ini files" | sed -e "s|.*:\s*||"`/00_sqlsrv.ini

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer