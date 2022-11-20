FROM alpine:latest
# Add libraries for rendering and fonts
RUN apk update \
    && apk add --no-cache libxext libxrender libxtst libxi fontconfig ttf-dejavu \
    && rm -rf /var/cache/apk/*