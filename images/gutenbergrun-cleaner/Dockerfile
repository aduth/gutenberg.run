FROM alpine

RUN apk add docker coreutils mariadb-client

COPY ./purge-containers.sh /purge-containers.sh
COPY ./entrypoint.sh /entrypoint.sh
RUN chmod +x /purge-containers.sh /entrypoint.sh

# Setup cronjob
COPY ./cronjobs /etc/crontabs/root
RUN touch /var/log/cron.log

ENTRYPOINT [ "/bin/sh", "-e", "/entrypoint.sh" ]
