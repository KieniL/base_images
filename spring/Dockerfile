FROM adoptopenjdk/openjdk13:x86_64-alpine-jre13u-nightly

LABEL maintainer="KieniL"
LABEL name="springbaseimage"
LABEL version="1.0"
LABEL author="KieniL"
LABEL contact="https://github.com/KieniL/base_images/issues"
LABEL documentation="https://github.com/KieniL/base_images"

ENV TZ=Europe/Berlin

WORKDIR /app

# create user
# create tmpdir for java.io.tmpdir
# set permissions on /app/tmp to new user
RUN apk update --no-cache \
&& apk add git \
&& addgroup -S springgroup && adduser -S springuser -G springgroup \
&& mkdir /app/tmp \
&& chown -R springuser:springgroup /app \
&& rm -R /var/cache/apk/

USER springuser
