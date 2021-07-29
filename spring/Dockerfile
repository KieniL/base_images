FROM adoptopenjdk/openjdk13:x86_64-alpine-jre13u-nightly

ENV TZ=Europe/Berlin

WORKDIR /APP

# run container as non root
RUN apk update && apk upgrade -U -a && addgroup -S familygroup && adduser -S familyuser -G familygroup

USER familyuser
