FROM nginx:1.21.0-alpine

LABEL maintainer="KieniL"
LABEL name="nginxbaseimage"
LABEL version="1.0"
LABEL author="KieniL"
LABEL contact="https://github.com/KieniL/base_images/issues"
LABEL documentation="https://github.com/KieniL/base_images"

WORKDIR /app

# Create packages
# create temp files
# copy the config of nginx to workdir for later usage
# set file permissions for nginx user
RUN apk update --no-cache \
&& apk add --upgrade libxml2-dbg=2.9.12-r0 curl-doc=7.78.0-r0 curl=7.78.0-r0 libxml2=2.9.12-r0 gettext=0.20.2-r2 --no-cache \
&& mkdir /var/cache/nginx/client_temp /var/cache/nginx/proxy_temp \
  /var/cache/nginx/fastcgi_temp /var/cache/nginx/uwsgi_temp \
  /var/cache/nginx/scgi_temp && echo "1" > /tmp/nginx.pid && echo "1" >  /var/run/nginx.pid \
&& cp -R /etc/nginx/* /app \
&& chown -R nginx:nginx /var/cache/nginx /etc/nginx/ /tmp/nginx.pid /app \
&& rm -R /var/cache/apk/

# switch to non-root user
USER nginx