FROM php:5-apache
MAINTAINER tess@deninet.com

RUN apt-get update && apt-get install -y \
    libfreetype6-dev \
    libjpeg62-turbo-dev \
    libmcrypt-dev \
    libpng12-dev \
    libicu-dev

RUN docker-php-ext-install gd json intl pdo pdo_mysql mbstring

# Add custom PHP configuration changes from php.ini
COPY php.ini /usr/local/etc/php/

# Copy and enable our own site configuration -- needed for .htaccess enable.
COPY web.conf /etc/apache2/sites-available/web.conf
RUN a2dissite 000-default && \
    a2ensite web

# Enable mod_rewrite, otherwise Drupal form submission doesn't work.
RUN a2enmod rewrite
