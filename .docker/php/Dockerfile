FROM php:7.4-fpm
ARG user=app
WORKDIR /www/html
RUN apt-get update && apt install -y unzip
RUN apt-get install -y libzip-dev && docker-php-ext-install zip mysqli pdo_mysql

RUN useradd -ms /bin/bash $user
RUN chown -R $user:$user /www/html
RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer
USER $user
EXPOSE 9000