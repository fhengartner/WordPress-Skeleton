FROM php:7.0.1-apache

# PHP extensions
RUN docker-php-ext-install mysqli && docker-php-ext-install mbstring

# Enable apache modules
RUN a2enmod rewrite && a2enmod headers && a2enmod expires 

# modify user-id of www-data so it has write access to mounted volume /var/www/html
# https://github.com/boot2docker/boot2docker/issues/581
RUN usermod -u 1000 www-data && usermod -G staff www-data && chown -Rf www-data.www-data /var/www/html

