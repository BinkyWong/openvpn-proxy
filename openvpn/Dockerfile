FROM alpine:3.15.0

RUN set -xe \
    && apk add --update --no-cache openvpn

ENTRYPOINT ["openvpn"]
VOLUME ["/vpn"]