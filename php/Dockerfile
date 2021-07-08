FROM php:7.4-fpm

RUN apt-get update 
RUN apt-get install -y zlib1g-dev libpq-dev git libicu-dev libxml2-dev libzip-dev zip unzip 
RUN apt-get install -y vim
RUN docker-php-ext-configure intl 
RUN docker-php-ext-install intl 
RUN docker-php-ext-configure pgsql -with-pgsql=/usr/local/pgsql 
RUN docker-php-ext-install pdo pdo_pgsql pgsql 
RUN docker-php-ext-install zip xml

WORKDIR /var/www/

RUN curl -sS https://getcomposer.org/installer | php -- --install-dir=/usr/local/bin --filename=composer

# RUN curl -sS https://get.symfony.com/cli/installer | bash
# RUN mv /root/.symfony/bin/symfony /usr/local/bin/symfony
COPY ./html /var/www/
# RUN pecl install xdebug
# RUN docker-php-ext-enable xdebug
# RUN composer install
# RUN composer update
# RUN apt-get install nodejs
# RUN npm install --save && y