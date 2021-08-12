FROM nginx:1.21.0-alpine

WORKDIR /app


RUN apk update --no-cache && apk add --upgrade libxml2-dbg=2.9.12-r0 curl-doc=7.78.0-r0 curl=7.78.0-r0 libxml2=2.9.12-r0 gettext=0.20.2-r2 --no-cache

#Create temp files to that they are not created on runtime
RUN mkdir /var/cache/nginx/client_temp /var/cache/nginx/proxy_temp \
  /var/cache/nginx/fastcgi_temp /var/cache/nginx/uwsgi_temp \
  /var/cache/nginx/scgi_temp && echo "1" > /tmp/nginx.pid && echo "1" >  /var/run/nginx.pid 

RUN cp -R /etc/nginx /app

# set file permissions for nginx user
RUN chown -R nginx:nginx /var/cache/nginx /etc/nginx/ /tmp/nginx.pid

# switch to non-root user
USER nginx