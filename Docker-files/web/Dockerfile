FROM nginx:latest
LABEL "Project"="microservices"
LABEL "Author"="DevOps"

RUN rm -rf /etc/nginx/conf.d/default.conf
COPY nginvproapp.conf /etc/nginx/conf.d/nginvproapp.conf
