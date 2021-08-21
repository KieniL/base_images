FROM markhobson/maven-chrome:jdk-11

LABEL maintainer="KieniL"
LABEL name="mavenchromebaseimage"
LABEL version="1.0.0"
LABEL author="KieniL"
LABEL contact="https://github.com/KieniL/base_images/issues"
LABEL documentation="https://github.com/KieniL/base_images"

ENV TZ EUROPE/BERLIN

WORKDIR /app

SHELL ["/bin/bash", "-o", "pipefail", "-c"]
RUN apt-get --simulate purge $(dpkg-query -Wf '${Package;-40}${Priority}\n' \
| awk '$2 ~ /optional|extra/ { print $1 }') \
&& apt-get autoremove -y \
&& rm -R /var/cache/apt/