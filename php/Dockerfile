FROM php:8.1-fpm

RUN apt-get update && apt-get install -y zlib1g-dev g++ git libicu-dev zip libzip-dev zip libpq-dev
RUN docker-php-ext-install intl opcache pdo pdo_pgsql pgsql
RUN pecl install apcu
RUN docker-php-ext-enable apcu
RUN docker-php-ext-configure zip
RUN docker-php-ext-install zip

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN curl -sS https://get.symfony.com/cli/installer | bash
RUN mv /root/.symfony5/bin/symfony /usr/local/bin/symfony

WORKDIR /var/www/project
