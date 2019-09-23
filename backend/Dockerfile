FROM ubuntu:16.04
 
RUN apt-get update \
 && DEBIAN_FRONTEND=noninteractive apt-get install -y mysql-server \
 && sed -i "s/127.0.0.1/0.0.0.0/g" /etc/mysql/mysql.conf.d/mysqld.cnf \
 && mkdir /var/run/mysqld \
 && chown -R mysql:mysql /var/run/mysqld


ENV MYSQL_ROOT_PASSWORD root
ENV MYSQL_USER chandra
ENV MYSQL_PASSWORD chandra
 
#VOLUME ["/var/lib/mysql"]
 
EXPOSE 3306
ADD script/createdb.sql /docker-entrypoint-initdb.d
#CMD ["mysqld_safe"]