FROM nginx:1.17.3-alpine

LABEL MAINTAINER="marco"

RUN mkdir -p /nginx-dir
WORKDIR /nginx-dir

ADD ./nginx.conf /etc/nginx/nginx.conf

RUN rm -rf /usr/share/nginx/html
ADD ./dist/ /usr/share/nginx/html
CMD nginx -g 'daemon off;'
