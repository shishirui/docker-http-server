FROM php:8.1-fpm

COPY sources.list /etc/apt/sources.list

RUN apt-get update \
    && apt-get install -y libmagickwand-dev --no-install-recommends \
    && mkdir -p /usr/src/php/ext/imagick \
    && curl -fsSL https://github.com/Imagick/imagick/archive/06116aa24b76edaf6b1693198f79e6c295eda8a9.tar.gz | tar xvz -C "/usr/src/php/ext/imagick" --strip 1 \
    && docker-php-ext-install imagick \
    && docker-php-ext-install pdo_mysql \
    && docker-php-ext-install mysqli \
    && docker-php-ext-install gd
