FROM php:8.5.13-fpm

RUN apt-get update

RUN apt-get install -y --no-install-recommends git unzip libpq-dev libzip-dev libicu-dev

RUN docker-php-ext-install -j"$(nproc)" pdo_pgsql pgsql bcmath intl pcntl zip

RUN apt-get clean && rm -rf /var/lib/apt/lists/*

COPY --from=composer:2 /usr/bin/composer /usr/bin/composer

WORKDIR /var/www/html
