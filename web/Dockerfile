# Official PHP docker image with Apache pre-installed.
FROM php:8.0-apache

# Install dependencies and PHP extensions Laravel depends on.
RUN apt update \
    && apt install -y \
        g++ \
        libicu-dev \
        libpq-dev \
        libzip-dev \
        libpng-dev \
        zip \
        zlib1g-dev \
    && docker-php-ext-install \
        intl \
        opcache \
        pdo \
        pdo_mysql \
        bcmath \
        pcntl \
        zip \
        sockets \
        gd \
    && mkdir /var/www/laravel_app \
    && chown www-data:www-data /var/www/laravel_app \
    && chmod g+s /var/www/laravel_app

# Set working directory to the container's 'project' space.
WORKDIR /var/www/laravel_app

# Install Composer.
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
