# PHP Application
FROM php:7.2-fpm

LABEL maintainer="Norby Baruani <norbyb@roam.africa>"

# Install any custom system requirements here
RUN apt-get update \
    && apt-get install -y \
        libpq-dev \
        libfreetype6-dev \
        libjpeg62-turbo-dev \
        libpng-dev \
        zlib1g-dev \
        libxml2-dev \
        libcurl3 \
        libcurl3-dev \
        gnupg \
        gnupg2 \
        nano \
        mysql-client \
        unzip \
        apt-transport-https \
    && docker-php-ext-install \
        -j$(nproc) \
        iconv \
        gd \
        zip \
        mbstring \
        pdo \
        pdo_mysql \
        mysqli \
        bcmath \
        opcache \
        json \
        intl \
        curl \
        tokenizer \
        ctype \
        pcntl \
    && docker-php-ext-configure gd --with-freetype-dir=/usr/include/ --with-jpeg-dir=/usr/include/ \
    && docker-php-ext-enable mysqli \
    && curl -sL https://deb.nodesource.com/setup_8.x | bash \
    && curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin/ --filename=composer \
    && curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | apt-key add - \
    && echo "deb https://dl.yarnpkg.com/debian/ stable main" | tee /etc/apt/sources.list.d/yarn.list \
    && apt-get update \
    && apt-get install -y \
        yarn \
        nodejs

RUN node -v
RUN npm -v

# DIR
WORKDIR /var/www/app

CMD ["php-fpm"]