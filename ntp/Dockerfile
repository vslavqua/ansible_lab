FROM --platform=linux/arm64 debian:bullseye

ARG DC_NAME

RUN apt-get update && \
    apt-get install -y chrony && \
    apt-get clean

COPY chrony-${DC_NAME}.conf /etc/chrony/chrony.conf

CMD ["chronyd", "-d"]