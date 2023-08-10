FROM php:8.1.0-fpm

RUN apt-get update && apt-get install -y \
    curl \
    wget \
    git \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libpng-dev \
    libonig-dev \
    libzip-dev \
    libmcrypt-dev \
    && pecl install mcrypt \
    && docker-php-ext-enable mcrypt \
    && docker-php-ext-install -j$(nproc) iconv mbstring mysqli pdo_mysql zip \
    && docker-php-ext-configure gd --with-freetype --with-jpeg \
    && docker-php-ext-install -j$(nproc) gd

ENV PHP_IDE_CONFIG="serverName=Docker"
RUN pecl install xdebug-3.1.2 && docker-php-ext-enable xdebug
COPY xdebug.ini /usr/local/etc/php/conf.d/docker-php-ext-xdebug.ini

WORKDIR /var/www

RUN curl https://raw.githubusercontent.com/composer/getcomposer.org/main/web/installer -o /usr/src/composer-setup \
   && php /usr/src/composer-setup --install-dir=/bin --filename=composer

RUN docker-php-ext-install pdo pdo_mysql

COPY init.sh /init.sh

ENTRYPOINT ["bash", "/init.sh"]