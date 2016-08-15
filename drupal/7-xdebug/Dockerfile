FROM socketwench/drupal-base:7
MAINTAINER tess@deninet.com

# Download xdebug to the /tmp folder.
ADD http://xdebug.org/files/xdebug-2.4.0.tgz /tmp/xdebug-2.4.0.tgz

# Install and enable xdebug
RUN cd /tmp && \
    tar -xzf xdebug-2.4.0.tgz && \
    cd xdebug-2.4.0 && \
    phpize && \
    ./configure && \
    make && \
    cp modules/xdebug.so /usr/local/lib/php/extensions/no-debug-non-zts-20151012

# Add custom PHP configuration changes from php.ini
COPY php.ini /usr/local/etc/php/
