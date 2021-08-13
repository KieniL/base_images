FROM mysql:8.0.26

RUN usermod -u 10000 mysql && groupmod -g 10000 mysql \
  && chmod 777 -R /var/run/mysqld/

RUN find / -name '/proc' -prune -group 10000 -exec chgrp -h mysql {} \;

RUN find / -name '/proc' -prune -user 10000 -exec chown -h mysql {} \;
