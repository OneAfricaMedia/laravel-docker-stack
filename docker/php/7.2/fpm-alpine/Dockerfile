# PHP Application
FROM php:7.2-fpm-alpine

LABEL maintainer="Norby Baruani <norbyb@roam.africa>"

ENV YARN_VERSION=latest

# Install any custom system requirements here
RUN apk update \
    && apk add --no-cache --virtual .build_deps \
        $PHPIZE_DEPS \
        curl-dev \
        imagemagick-dev \
        libtool \
        libxml2-dev \
        make \
        gcc \
    && apk add --no-cache \
        curl \
        imagemagick \
        mysql-client \
        libintl \
        icu-dev \
        icu \
        vim \
        unzip \
        composer \
        nodejs \
        bash \
    && docker-php-ext-install \
        curl \
        iconv \
        mbstring \
        pdo \
        pdo_mysql \
        mysqli \
        pcntl \
        tokenizer \
        xml \
        zip \
        intl \
        ctype \
        bcmath \
        json \
    && pecl install imagick \
    && docker-php-ext-enable \
        imagick \
        mysqli \
    && curl -sfSL -O https://yarnpkg.com/${YARN_VERSION}.tar.gz -O https://yarnpkg.com/${YARN_VERSION}.tar.gz.asc \
    && mkdir /usr/local/share/yarn \
    && tar -xf ${YARN_VERSION}.tar.gz -C /usr/local/share/yarn --strip 1 \
    && ln -s /usr/local/share/yarn/bin/yarn /usr/local/bin/ \
    && ln -s /usr/local/share/yarn/bin/yarnpkg /usr/local/bin/ \
    && rm ${YARN_VERSION}.tar.gz* \
    && apk del --no-cache -f .build_deps \
    && rm -f /var/cache/apk/*

# DIR
WORKDIR /var/www/app

CMD ["php-fpm"]