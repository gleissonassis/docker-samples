FROM alpine

RUN apk update && \
    apk add mariadb mariadb-client && \
    mysql_install_db --user=mysql && \
    /usr/share/mysql/mysql.server start && \
    mysql -u root mysql -e "GRANT ALL PRIVILEGES ON *.* TO dbuser@'%' IDENTIFIED BY 'dbpassword'"

VOLUME /var/lib/mysql
EXPOSE 3306
CMD ["mysqld_safe","--user=mysql"]