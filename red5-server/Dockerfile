#
# Dockerfile for red5-server
#

FROM java:8-alpine
MAINTAINER kev <noreply@easypi.info>

ENV RED5_VERSION 1.0.7

WORKDIR /opt/red5-server

RUN set -xe \
    && apk add -U bash curl tar \
    && curl -sSL https://github.com/Red5/red5-server/releases/download/v${RED5_VERSION}-RELEASE/red5-server-${RED5_VERSION}-RELEASE.tar.gz | tar xz --strip 1 \
    && apk del curl tar \
    && rm -rf /var/cache/apk/*

EXPOSE 843 1935 5080 5443 8088 8443 9999

ENTRYPOINT ["./red5.sh"]
