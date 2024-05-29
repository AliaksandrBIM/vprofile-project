# Используем официальный образ MySQL версии 8.0.33
FROM mysql:8.0.33
# Добавляем метки для идентификации проекта и автора
LABEL "Project"="microservices"
LABEL "Author"="DevOps"
# Устанавливаем переменные окружения для конфигурации MySQL
ENV MYSQL_ROOT_PASSWORD="vprodbpass"
ENV MYSQL_DATABASE="microservices"
# Добавляем SQL файл для инициализации базы данных
ADD db_backup.sql /docker-entrypoint-initdb.d/db_backup.sql

