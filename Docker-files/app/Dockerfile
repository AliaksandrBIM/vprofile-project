# 1-й этап: сборка артефакта
FROM openjdk:11 AS build_image
RUN apt-get update && apt-get install -y maven git
# Клонируем репозиторий
RUN git clone https://github.com/AliaksandrBIM/vprofile-project.git
# Переходим в папку проекта, переключаемся на нужную ветку и запускаем билд
WORKDIR vprofile-project
RUN git checkout docker && mvn clean install

# 2-й этап: сборка конечного образа
FROM tomcat:9.0-jdk11-openjdk
LABEL "Project"="microservices"
LABEL "Author"="DevOps"
# Удаляем стандартные приложения Tomcat
RUN rm -rf /usr/local/tomcat/webapps/*
# Копируем артефакт из первого этапа
COPY --from=build_image /vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war
# Открываем порт 8080
EXPOSE 8080
# Запускаем Tomcat
CMD ["catalina.sh", "run"]

