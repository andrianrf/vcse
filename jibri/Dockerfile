FROM jitsi/base-java:stable-8615

LABEL org.opencontainers.image.title="Video Broadcasting Infrastructure"
LABEL org.opencontainers.image.description="Components for recording and/or streaming a conference."
LABEL org.opencontainers.image.url="https://hub.docker.com/repository/docker/andrianrf/vcs-broadcast/general"
LABEL org.opencontainers.image.source="https://github.com/andrianrf/vcse/tree/master/jibri"
LABEL org.opencontainers.image.documentation="https://github.com/andrianrf/vcse"

ARG TARGETPLATFORM=linux/x86_64
ARG USE_CHROMIUM=0
#ARG CHROME_RELEASE=latest
#ARG CHROMEDRIVER_MAJOR_RELEASE=latest
ARG CHROME_RELEASE=112.0.5615.49
ARG CHROMEDRIVER_MAJOR_RELEASE=112

COPY rootfs/ /

RUN apt-dpkg-wrap apt-get update && \
    apt-dpkg-wrap apt-get install -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" jibri libgl1-mesa-dri procps jitsi-upload-integrations jq pulseaudio dbus dbus-x11 rtkit unzip && \
    /usr/bin/install-chrome.sh && \
    apt-cleanup && \
    adduser jibri rtkit

VOLUME /config
