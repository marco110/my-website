FROM nginx:1.17.3-alpine

LABEL MAINTAINER="marco"

RUN pwd

COPY ./nginx.conf /etc/nginx/nginx.conf

RUN rm -rf /usr/share/nginx/html
COPY dist/ /usr/share/nginx/html
