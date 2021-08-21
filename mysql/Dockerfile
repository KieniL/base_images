FROM mysql:8.0.26

LABEL maintainer="KieniL"
LABEL name="mysqlbaseimage"
LABEL version="1.0"
LABEL author="KieniL"
LABEL contact="https://github.com/KieniL/base_images/issues"
LABEL documentation="https://github.com/KieniL/base_images"

SHELL ["/bin/bash", "-o", "pipefail", "-c"]

RUN echo "1" > /tmp/mysqld.pid && chmod 777 /tmp/mysqld.pid \
&& usermod -u 20000 mysql && groupmod -g 20000 mysql \
&& find / -name '/proc' -prune -group 20000 -exec chgrp -h mysql {} \; \
&& find / -name '/proc' -prune -user 20000 -exec chown -h mysql {} \; \
&& chown mysql:mysql /var/run/mysqld && chown mysql:mysql /var/lib/mysql \
&& apt-get --simulate purge $(dpkg-query -Wf "${Package;-40}${Priority}\n" \
| awk '$2 ~ /optional|extra/ { print $1 }') \
&& apt-get autoremove -y \
&& rm -R /var/cache/apt/