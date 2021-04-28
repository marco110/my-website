FROM nginx:1.17.3-alpine

LABEL MAINTAINER="marco"

RUN pwd

COPY /devops/nginx.conf /etc/nginx/nginx.conf

RUN rm -rf /usr/share/nginx/html
COPY /devops/dist/ /usr/share/nginx/html
