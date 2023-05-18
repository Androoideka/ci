FROM androoideka/alpine-gui:latest
ARG JAVA_VERSION=17
ENV JAVA_HOME=/usr/lib/jdk
# Set Java version, add JAVA_HOME to path and default to UTF-8 file.encoding
ENV JAVA_VERSION=${JAVA_VERSION} PATH=${PATH}:${JAVA_HOME}/bin LANG='en_US.UTF-8' LANGUAGE='en_US:en' LC_ALL='en_US.UTF-8'
# Download and extract JDK and add tools for building Java projects like objcopy and maven
RUN wget -nv -O jdk.tar.gz "https://aka.ms/download-jdk/microsoft-jdk-${JAVA_VERSION}-alpine-x64.tar.gz" \
    && mkdir $JAVA_HOME \
    && tar xf jdk.tar.gz -C $JAVA_HOME --strip-components 1 --no-same-owner \
    && rm jdk.tar.gz \
    && apk add --no-cache binutils maven