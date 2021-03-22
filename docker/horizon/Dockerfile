FROM dps3_app:local
USER root
RUN mkdir -p /var/lib/apt/lists/ \
    && apt-get -yqq update \
    && apt-get install -yqq --no-install-recommends \
       wget curl supervisor \
    && rm -rf /var/lib/apt/lists/*

ADD ./docker/horizon/supervisord.conf /etc/supervisor/supervisord.conf

RUN chown laravel:laravel /var/log -R \
    && chmod g+rwx /var/log

WORKDIR /etc/supervisor/conf.d/

USER laravel

ENTRYPOINT ["/usr/bin/supervisord", "-n", "-c",  "/etc/supervisor/supervisord.conf"]
