FROM debian:12

RUN apt-get update && apt-get install -y \
    mariadb-server \
    mariadb-client

RUN mkdir -p /run/mysqld && chown -R mysql:mysql /run/mysqld

COPY conf/configeration-mariadb.cnf /etc/mysql/mariadb.conf.d/

COPY tools/init.sh /init.sh
RUN chmod +x /init.sh

EXPOSE 3306
ENTRYPOINT ["/init.sh"]