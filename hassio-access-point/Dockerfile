ARG BUILD_FROM="ghcr.io/home-assistant/base:latest"
FROM $BUILD_FROM

LABEL maintainer="ex-ml <ex_ml@sent.com>"

RUN apk update && \
apk add --no-cache bash iw hostapd networkmanager networkmanager-cli net-tools sudo dnsmasq iptables && \
rm -rf /var/cache/apk/*

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

ENV LANG=C.UTF-8

COPY hostapd.conf /hostapd.conf
COPY dnsmasq.conf /dnsmasq.conf

COPY run.sh /run.sh
RUN chmod a+x /run.sh

CMD [ "/run.sh" ]
