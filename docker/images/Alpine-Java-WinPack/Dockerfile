FROM alpine:latest
ARG JAVA_VERSION=17
# Set Java version and add path for Windows JDK
ENV JAVA_VERSION=${JAVA_VERSION} JAVA_WIN=/usr/lib/winjdk
# Download and extract JDK
RUN apk add --no-cache wine \
    && wget -nv -O jdk.zip "https://aka.ms/download-jdk/microsoft-jdk-${JAVA_VERSION}-windows-x64.zip" \
    && mkdir $JAVA_WIN \
    && unzip jdk.zip \
    && rm jdk.zip \
    && mv -f `find . -type d -maxdepth 1 -name "jdk*"`/* $JAVA_WIN \
    && rm -rf `find . -type d -maxdepth 1 -name "jdk*"`