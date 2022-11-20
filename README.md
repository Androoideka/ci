# Description

This repository contains Dockerfiles and devcontainer features that leverage Alpine Linux for developing and building various cross-platform apps, notably GUI Java apps that rely on Swing or JavaFX.

## Images

Alpine-GUI is a quick-start Alpine image with additional libraries installed to allow rendering graphical applications. This includes common fonts through deja-vu.

Alpine-GUI-Java and Alpine-GUI-JavaFX are Alpine images that come with a x64 JDK for developing Java apps with GUI support. The Microsoft OpenJDK was selected for these images because it's not headless so using AWT libraries is possible. There is currently no Microsoft OpenJDK release for Alpine on ARM so this will only work on x64 systems.

Alpine-Java-WinPack is an Alpine image with wine installed and a Windows JDK for packaging Java apps into Windows programs using jpackage --type app-image. I've avoided including WiX toolkit because I prefer using the new WiX 4.0 that relies solely on .NET Core.

Alpine-Java is an Alpine image with the Eclipse Temurin JDK installed. Use this for building headless applications such as Spring Boot applications.

All Java images aside from WinPack come with maven.

## Features

The features included in this repository are meant for Visual Studio Code container development. 

alpine-utils is a modification of the common-utils feature in devcontainers/features to be more lightweight and to work with Alpine Linux. This feature installs a Code Server, sets up a non-root user and installs bash and basic development tools.

wslg-config sets up the container to display apps using WSLg on Windows. This feature is currently incomplete because features don't support passing environment variables from the host into the container. A workaround for this is to add the following along with the feature into your devcontainer.json:
```
"containerEnv": {
	"DISPLAY": ":0",
	"WAYLAND_DISPLAY": "${localEnv:WAYLAND_DISPLAY}",
	"XDG_RUNTIME_DIR": "${localEnv:XDG_RUNTIME_DIR}",
	"PULSE_SERVER": "${localEnv:PULSE_SERVER}"
},
```