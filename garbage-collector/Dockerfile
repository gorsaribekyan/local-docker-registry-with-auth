FROM ubuntu:22.04

RUN apt-get update -y
RUN apt-get install cron -y

COPY ./crontab /etc/cron.d/garbage-collector-cron

RUN crontab /etc/cron.d/garbage-collector-cron

RUN chmod 644 /etc/cron.d/garbage-collector-cron

RUN sed -i '/session    required     pam_loginuid.so/c\#session    required   pam_loginuid.so' /etc/pam.d/cron

CMD ["cron", "-f"]
