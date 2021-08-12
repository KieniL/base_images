FROM adoptopenjdk/openjdk13:x86_64-alpine-jre13u-nightly

ENV TZ=Europe/Berlin

WORKDIR /app

# run container as non root
RUN apk update && apk upgrade -U -a \
&& addgroup -S springgroup && adduser -S springuser -G springgroup

#create tmpdir for java.io.tmpdir
RUN mkdir /app/tmp

USER springuser
