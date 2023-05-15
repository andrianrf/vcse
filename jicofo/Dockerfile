FROM jitsi/base-java:stable-8615

LABEL org.opencontainers.image.title="Video Conference Focus (vicofo)"
LABEL org.opencontainers.image.description="Server-side focus component that manages media sessions and acts as load balancer."
LABEL org.opencontainers.image.url="https://hub.docker.com/repository/docker/andrianrf/vcs-vicofo/general"
LABEL org.opencontainers.image.source="https://github.com/andrianrf/vcse/tree/master/jicofo"
LABEL org.opencontainers.image.documentation="https://github.com/andrianrf/vcse"

RUN apt-dpkg-wrap apt-get update && \
    apt-dpkg-wrap apt-get install -y jicofo && \
    apt-cleanup

COPY rootfs/ /

VOLUME /config
