FROM php:7.1-fpm

MAINTAINER Damber Prasad Gautam <damber.gautam@gmail.com>

ENV WORKDIR "/var/www/app"

RUN apt-get update && apt-get install -y --no-install-recommends \
    curl \
    openssl \
    git \
    unzip \
    libmemcached-dev \
    libz-dev \
    libpq-dev \
    libjpeg-dev \
    libpng-dev \
    libfreetype6-dev \
    libssl-dev \
    libmcrypt-dev \
    libicu-dev \
    autoconf \
    file \
    g++ \
    gcc \
  && rm -rf /var/lib/apt/lists/*
#&& apt-get purge -y --auto-remove $BUILD_DEPS

# Install php modules
RUN docker-php-ext-install pdo_mysql \
    #&& docker-php-ext-install pdo_pgsql \
    #&& docker-php-ext-install zip \
    #&& docker-php-ext-install bcmath \
    && docker-php-ext-configure intl \
    && docker-php-ext-install intl \
    && docker-php-ext-configure gd \
        --enable-gd-native-ttf \
        --with-jpeg-dir=/usr/lib \
        --with-png-dir=/usr/lib/ \
        --with-freetype-dir=/usr/include/freetype2 \
    && docker-php-ext-install gd


# Install Xdebug and Redis
#RUN docker-php-source extract \
#    && pecl install xdebug-alpha redis \
#    && docker-php-ext-enable xdebug redis \
#    && docker-php-source delete


# Install composer
RUN curl -sS https://getcomposer.org/installer | \
    php -- --install-dir=/usr/local/bin --filename=composer

COPY ./conf/xdebug.ini /usr/local/etc/php/conf.d/xdebug.ini
COPY ./conf/php.ini /usr/local/etc/php/conf.d/php.ini

RUN mkdir -p ${WORKDIR}

WORKDIR ${WORKDIR}
