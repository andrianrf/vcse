FROM jitsi/base:stable-8615

LABEL org.opencontainers.image.title="VCS Web"
LABEL org.opencontainers.image.description="VCS Web."
LABEL org.opencontainers.image.url="https://hub.docker.com/repository/docker/andrianrf/vcs-web/general"
LABEL org.opencontainers.image.source="https://github.com/andrianrf/vcse/tree/master/web"
LABEL org.opencontainers.image.documentation="https://github.com/andrianrf/vcse"

ADD https://raw.githubusercontent.com/acmesh-official/acme.sh/2.8.8/acme.sh /opt
COPY rootfs/ /

RUN apt-dpkg-wrap apt-get update && \
    apt-dpkg-wrap apt-get install -y cron nginx-extras jitsi-meet-web socat curl jq && \
    mv /usr/share/jitsi-meet/interface_config.js /defaults && \
    rm -f /etc/nginx/conf.d/default.conf && \
    apt-cleanup

EXPOSE 80 443

VOLUME ["/config", "/usr/share/jitsi-meet/transcripts"]
