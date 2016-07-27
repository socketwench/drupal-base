FROM composer/composer:php5
MAINTAINER tess@deninet.com

# Add common extensions
RUN apt-get update && \
    apt-get install -yq \
            mysql-client \
            supervisor

RUN docker-php-ext-install pdo_mysql

RUN composer global require drush/drush

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

WORKDIR /var/www/html

CMD ["-n"]

ENTRYPOINT ["/usr/bin/supervisord"]
