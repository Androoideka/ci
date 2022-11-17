FROM androoideka/alpine-gui:latest

ARG TARGET_JAVA_VERSION=17
ARG JDK_URL="https://aka.ms/download-jdk/microsoft-jdk-${TARGET_JAVA_VERSION}-alpine-x64.tar.gz"
ENV JAVA_HOME /usr/lib/jvm/msopenjdk-${TARGET_JAVA_VERSION}
ENV PATH "${JAVA_HOME}/bin:${PATH}"
# Default to UTF-8 file.encoding
ENV LANG en_US.UTF-8

# Install Microsoft OpenJDK
RUN apk add --no-cache unzip zip \
    && wget -O msopenjdk.tar.gz "${JDK_URL}" \
    && wget -O sha256sum.txt "${JDK_URL}.sha256sum.txt" \
    \
    && sha256sumText=$(cat sha256sum.txt) \
    && sha256=$(expr substr "${sha256sumText}" 1 64) \
    && echo "${sha256}  msopenjdk.tar.gz" | sha256sum - \
    && rm sha256sum.txt* \
    \
    && mkdir -p "$JAVA_HOME" \
    && tar --extract \
    --file msopenjdk.tar.gz \
    --directory "$JAVA_HOME" \
    --strip-components 1 \
    --no-same-owner \
    && rm msopenjdk.tar.gz* \
    \
    && ln -s ${JAVA_HOME} /docker-java-home \
    && ln -s ${JAVA_HOME} /usr/local/openjdk-${TARGET_JAVA_VERSION}