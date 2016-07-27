FROM composer/composer:php5
MAINTAINER tess@deninet.com

RUN composer global require drush/drush

RUN apt-get update && \
    apt-get -yq install supervisor

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

WORKDIR /var/www/html

CMD ["-n"]

ENTRYPOINT ["/usr/bin/supervisord"]
