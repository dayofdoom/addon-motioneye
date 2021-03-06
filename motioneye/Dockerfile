ARG BUILD_FROM=hassioaddons/base:2.3.0
# hadolint ignore=DL3006
FROM ${BUILD_FROM}

# Set shell
SHELL ["/bin/bash", "-o", "pipefail", "-c"]

# Setup base
RUN \
    apk add --no-cache \
        cifs-utils=6.8-r0 \
        ffmpeg=3.4.4-r1 \
        motion@edge=4.1.1-r0 \
        nginx=1.14.0-r1 \
        py2-curl=7.43.0-r5 \
        py2-pillow=4.3.0-r0 \
        py2-pip=10.0.1-r0 \
        python2=2.7.15-r1 \
        v4l-utils=1.12.6-r1 \
    \
    && pip2 install \
        motioneye==0.39.3

# Copy root filesystem
COPY rootfs /

# Build arugments
ARG BUILD_ARCH
ARG BUILD_DATE
ARG BUILD_REF
ARG BUILD_VERSION

# Labels
LABEL \
    io.hass.name="motionEye" \
    io.hass.description="Simple, elegant and feature-rich CCTV/NVR for your cameras" \
    io.hass.arch="${BUILD_ARCH}" \
    io.hass.type="addon" \
    io.hass.version=${BUILD_VERSION} \
    maintainer="Franck Nijhof <frenck@addons.community>" \
    org.label-schema.description="Simple, elegant and feature-rich CCTV/NVR for your cameras" \
    org.label-schema.build-date=${BUILD_DATE} \
    org.label-schema.name="motionEye" \
    org.label-schema.schema-version="1.0" \
    org.label-schema.url="https://community.home-assistant.io/t/community-hass-io-add-on-motioneye/71826?u=frenck" \
    org.label-schema.usage="https://github.com/hassio-addons/addon-motioneye/tree/master/README.md" \
    org.label-schema.vcs-ref=${BUILD_REF} \
    org.label-schema.vcs-url="https://github.com/hassio-addons/addon-motioneye" \
    org.label-schema.vendor="Community Hass.io Add-ons"
