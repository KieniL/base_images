FROM mysql:8.0.26


ENV TZ=Europe/Berlin

RUN groupadd dbgroup && useradd dbuser -G dbgroup

RUN chgrp dbgroup -R /var/lib/mysql && \
 chown dbuser -R /var/lib/mysql && \
 chgrp dbgroup -R /var/run/mysqld && \
 chown dbuser -R /var/run/mysqld

USER dbuser