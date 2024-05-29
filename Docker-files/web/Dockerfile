# Используем официальный образ Nginx
FROM nginx:latest
# Добавляем метки для идентификации проекта и автора
LABEL "Project"="microservices"
LABEL "Author"="DevOps"
# Удаляем стандартный файл конфигурации Nginx
RUN rm -rf /etc/nginx/conf.d/default.conf
# Копируем файл конфигурации в директорию конфигураций Nginx
COPY nginvproapp.conf /etc/nginx/conf.d/nginvproapp.conf

