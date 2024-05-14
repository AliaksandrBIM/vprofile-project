#1Stage --------------------------------------------------------------
FROM openjdk:11 AS BUILD_IMAGE
RUN apt update && apt install maven -y
RUN git clone https://github.com/AliaksandrBIM/vprofile-project.git
#переходим в папку проекта и запускаем билд для создания артефакта
RUN cd vprofile-project && git checkout docker && mvn install

#2Stage --------------------------------------------------------------
FROM tomcat:9-jrell
RUN rm -rf /usr/local/tomcat/webapps/*
COPY --from=BUILD_IMAGE vprofile-project/target/vprofile-v2.war /usr/local/tomcat/webapps/ROOT.war

EXPOSE 8080
CMD ["catalina.sh", "run"]
