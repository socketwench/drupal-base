FROM drush/drush
MAINTAINER tess@deninet.com

RUN apt-get update && \
    apt-get -yq install supervisor

COPY supervisord.conf /etc/supervisor/conf.d/supervisord.conf

CMD ["-n"]

ENTRYPOINT ["/usr/bin/supervisord"]
