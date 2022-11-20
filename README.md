# Description

This repository contains Dockerfiles and devcontainer features for developing and building various cross-platform apps, notably GUI Java apps that rely on Swing or JavaFX.
The Microsoft OpenJDK was selected as the Java distribution because it's not headless so using AWT libraries is possible.
Alpine-GUI-Java is a x64 image only, as there is no Microsoft OpenJDK release for Alpine on ARM. Other images should be hardware-agnostic.
The features included in this repository are meant for Visual Studio Code container development. alpine-utils installs a Code Server and basic development tools, while wslg-config sets up the container to display apps using WSLg on Windows. 
wslg-config is currently incomplete due to issue passing environment variables from the host into the container through features.