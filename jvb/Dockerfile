FROM jitsi/base-java:stable-8615

LABEL org.opencontainers.image.title="Video Bridge"
LABEL org.opencontainers.image.description="WebRTC compatible server designed to route video streams amongst participants in a conference."
LABEL org.opencontainers.image.url="https://hub.docker.com/repository/docker/andrianrf/vcs-videobridge/general"
LABEL org.opencontainers.image.source="https://github.com/andrianrf/vcse/tree/master/jvb"
LABEL org.opencontainers.image.documentation="https://github.com/andrianrf/vcse"

RUN apt-dpkg-wrap apt-get update && \
    apt-dpkg-wrap apt-get install -y jitsi-videobridge2 jq curl iproute2 dnsutils && \
    apt-cleanup

COPY rootfs/ /

VOLUME /config
