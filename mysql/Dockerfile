FROM mysql:8.0.26

RUN echo "1" > /tmp/mysqld.pid && chmod 777 /tmp/mysqld.pid

RUN usermod -u 10000 mysql && groupmod -g 10000 mysql

RUN find / -name '/proc' -prune -group 10000 -exec chgrp -h mysql {} \;

RUN find / -name '/proc' -prune -user 10000 -exec chown -h mysql {} \;

RUN chown mysql:mysql /var/run/mysqld