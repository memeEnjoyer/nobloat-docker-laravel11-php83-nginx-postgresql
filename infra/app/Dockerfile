FROM php:8.3-fpm-alpine

RUN apk update \
    && apk add \
    git \
    libpng-dev \
    libxml2-dev \
    zip \
    unzip \
    libpq-dev \
    libzip-dev \
    bind-tools \
    postgresql-dev

RUN docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql \
    && docker-php-ext-install pdo pdo_pgsql pgsql zip bcmath gd

COPY --from=composer:latest /usr/bin/composer /usr/bin/composer

EXPOSE 9000
