FROM socketwench/drupal-base:8
MAINTAINER tess@deninet.com

ADD http://xdebug.org/files/xdebug-2.4.0.tgz /tmp/xdebug-2.4.0.tgz

RUN cd /tmp && \
    tar -xzf xdebug-2.4.0.tgz && \
    cd xdebug-2.4.0 && \
    phpize && \
    ./configure && \
    make && \
    cp modules/xdebug.so /usr/local/lib/php/extensions/no-debug-non-zts-20151012

COPY php.ini /usr/local/etc/php/
