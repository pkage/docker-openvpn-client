FROM alpine:3.17

RUN apk add --no-cache \
    bash \
    bind-tools \
    iptables \
    curl \
    ip6tables \
    openvpn

COPY . /usr/local/bin

HEALTHCHECK --start-period 1m --start-interval=5s --interval=5m --timeout=3s \
  CMD curl -f http://ifconfig.me/ || exit 1

ENV KILL_SWITCH=on

ENTRYPOINT [ "entry.sh" ]
