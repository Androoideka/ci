FROM androoideka/alpine-gui-java:latest
RUN apk add --no-cache maven \
    && wget -nv -O javafx.zip https://download2.gluonhq.com/openjfx/19/openjfx-19_linux-x64_bin-jmods.zip \
    && unzip javafx.zip \
    && rm javafx.zip \
    && mv -f `find javafx-jmods-19/ -type f -maxdepth 1 -name "*.jmod"`/* $JAVA_HOME/jmods \
    && rm -rf javafx-jmods-19
