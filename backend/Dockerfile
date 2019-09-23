FROM ubuntu:18.04
MAINTAINER ursbrchandra@gmail.com
RUN apt-get -y update 
RUN apt-get -y install mysql-server  sudo
CMD ["mkdir","/var/lib/mysql"]
RUN chgrp -R 0 /var/lib/mysql/   
RUN chmod -R g+rw /var/lib/mysql/  
RUN find /var/lib/mysql/ -type d -exec chmod g+x {} +
VOLUME /var/lib/mysql
EXPOSE 3306
COPY script/createdb.sh ./
RUN chmod 755 ./createdb.sh
ENTRYPOINT ["./createdb.sh"]
