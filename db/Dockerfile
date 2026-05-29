FROM mysql:8

ENV MYSQL_ROOT_PASSWORD=admin123
ENV MYSQL_DATABASE=tienda_perritos

COPY init.sql /docker-entrypoint-initdb.d/init.sql

EXPOSE 3306
