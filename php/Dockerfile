FROM php:7.4.4-fpm
RUN apt-get update && apt-get install -y
RUN docker-php-ext-configure pdo_mysql --with-pdo-mysql
RUN docker-php-ext-install pdo_mysql
RUN apt-get install -y supervisor
RUN apt-get install -y iputils-ping
RUN apt-get install -y mariadb-client


RUN apt-get install -y \
        zlib1g-dev \
        libzip-dev \
        zip \
        cron\
        && docker-php-ext-install zip

RUN apt-get install nano
  
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/bin --filename=composer

RUN apt-get update && \
    apt-get install -y libfreetype6-dev libjpeg62-turbo-dev libpng-dev && \
    docker-php-ext-configure gd --with-freetype --with-jpeg &&\
    docker-php-ext-install gd

WORKDIR /var/www