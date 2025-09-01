FROM php:8.2-fpm
#WORKDIR /var/www/html
#COPY . /var/www/html

# Install any necessary PHP extensions (e.g., mysqli, pdo_mysql)

RUN apt-get update && apt-get install -y \
        git \
        libzip-dev \
        libpng-dev \
        unixodbc-dev \
        zip \
        unzip && \
	docker-php-ext-install mysqli zip gd

COPY --from=composer:latest /usr/bin/composer /usr/local/bin/composer