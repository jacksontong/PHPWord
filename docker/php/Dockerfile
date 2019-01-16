FROM php:7.1-apache

COPY 000-default.conf /etc/apache2/sites-enabled/000-default.conf

RUN apt-get update \
  && apt-get install -y --no-install-recommends zlib1g-dev libicu-dev g++ \
      libfreetype6-dev \
      libjpeg62-turbo-dev \
      libssl-dev \
      libpng-dev \
      git vim unzip \
  && docker-php-ext-configure gd --enable-gd-native-ttf --with-jpeg-dir=/usr/lib/x86_64-linux-gnu --with-png-dir=/usr/lib/x86_64-linux-gnu --with-freetype-dir=/usr/lib/x86_64-linux-gnu \
  && docker-php-ext-install -j$(nproc) gd \
  && docker-php-ext-install zip \
  && rm -rf /var/lib/apt/lists/*