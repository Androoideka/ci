FROM alpine:latest
RUN apk update \
    && apk add --no-cache libxext libxrender libxtst libxi fontconfig ttf-dejavu \
    && rm -rf /var/cache/apk/*