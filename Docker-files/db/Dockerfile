FROM mysql:8.0.33
LABEL "Project"="microservices"
LABEL "Author"="DevOps"

ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="microservices"

ADD db_backup.sql docker-entrypoint-initdb.d/db_backup.sql
