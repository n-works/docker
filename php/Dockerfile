FROM php:7.2-apache

RUN apt-get update \
  && apt-get install -y \
    unzip \
    zlib1g-dev \
  && docker-php-ext-install \
    zip \
  && rm -rf /var/lib/apt/lists/* \
  && apt-get clean

RUN a2enmod rewrite

COPY --from=composer /usr/bin/composer /usr/bin/composer
