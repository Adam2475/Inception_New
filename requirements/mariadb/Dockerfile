FROM debian:latest

RUN apt update && apt upgrade && apt install -y \
    mariadb-server

COPY 50-server.cnf /etc/mysql/mariadb.conf.d/.
COPY init.sql /etc/mysql/init.sql
COPY script.sh .

RUN mkdir /run/mysqld
RUN chmod +x script.sh

CMD ["./script.sh"]