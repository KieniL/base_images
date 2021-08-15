FROM mysql:8.0.26

RUN echo "1" > /tmp/mysqld.pid && chmod 777 /tmp/mysqld.pid

RUN usermod -u 20000 mysql && groupmod -g 20000 mysql

RUN find / -name '/proc' -prune -group 20000 -exec chgrp -h mysql {} \;

RUN find / -name '/proc' -prune -user 20000 -exec chown -h mysql {} \;

RUN chown mysql:mysql /var/run/mysqld

RUN chown mysql:mysql /var/lib/mysql