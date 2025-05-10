ARG BUILD_FROM=ghcr.io/home-assistant/amd64-base:3.19
FROM ${BUILD_FROM}

# Install required packages
RUN \
    apk add --no-cache \
        alsa-lib \
        avahi \
        avahi-compat-libdns_sd \
        dbus \
        pulseaudio-alsa \
        snapcast \
        librespot=0.4.3-r0

# Copy root filesystem
COPY rootfs /

# Labels
LABEL \
    io.hass.name="Snapcast Server" \
    io.hass.description="Snapcast server with Spotify connect support" \
    io.hass.type="addon" \
    io.hass.version="0.3.0"

# Set correct environment variables
ENV LANG C.UTF-8

ENTRYPOINT ["/init"]
