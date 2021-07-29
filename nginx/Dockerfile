FROM nginx:1.21.0-alpine

WORKDIR /app


RUN apk update --no-cache && apk add --upgrade libxml2-dbg=2.9.12-r0 curl-doc=7.78.0-r0 curl=7.78.0-r0 libxml2=2.9.12-r0 gettext=0.20.2-r2 --no-cache


# set file permissions for nginx user
RUN chown -R nginx:nginx /var/cache/nginx /etc/nginx/

# switch to non-root user
USER nginx