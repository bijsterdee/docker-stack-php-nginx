FROM php:7.4-fpm

## Install composer
RUN COMPOSER_HOME=/usr/local/composer curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

RUN apt-get update && \
    apt-get -yq install --no-install-recommends \
        libmcrypt-dev subversion git curl zip unzip acl libxml2-dev && \
    apt-get -y clean && \
    rm -rf /var/lib/apt/lists/*

# Install php extensions
RUN docker-php-ext-install \
    mysqli \
    pdo \
    pdo_mysql \
    soap