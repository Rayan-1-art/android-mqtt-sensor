FROM ubuntu:22.04
ENV DEBIAN_FRONTEND=noninteractive
RUN apt-get update && apt-get install -y wget unzip curl git build-essential openjdk-11-jdk ca-certificates unzip zip gradle && rm -rf /var/lib/apt/lists/*
RUN mkdir -p /usr/local/android-sdk/cmdline-tools && cd /usr/local/android-sdk && wget -q https://dl.google.com/android/repository/commandlinetools-linux-9477386_latest.zip -O /tmp/cmdline-tools.zip && unzip /tmp/cmdline-tools.zip -d cmdline-tools && mkdir -p cmdline-tools/latest && mv cmdline-tools/* cmdline-tools/latest/ && rm /tmp/cmdline-tools.zip
ENV ANDROID_SDK_ROOT=/usr/local/android-sdk
ENV PATH=${ANDROID_SDK_ROOT}/cmdline-tools/latest/bin:${ANDROID_SDK_ROOT}/platform-tools:${PATH}
RUN yes | sdkmanager --licenses || true
RUN sdkmanager --sdk_root=${ANDROID_SDK_ROOT} "platform-tools" "platforms;android-33" "build-tools;33.0.2"
WORKDIR /workspace
USER root
