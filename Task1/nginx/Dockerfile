FROM nginx:latest

RUN apt-get update
#RUN apt-get install nginx-extras -y
##RUN apt-get install libnginx-mod-http-headers-more-filter -y
#
RUN ln -sf /dev/stdout /var/log/nginx/access.log
RUN ln -sf /dev/stderr /var/log/nginx/error.log
#
RUN rm -rf /etc/nginx/conf.d/default.conf
RUN rm -rf /etc/nginx/nginx.conf
COPY ./nginx.conf /etc/nginx/nginx.conf
COPY ./app.conf /etc/nginx/conf.d/app.conf
RUN mkdir /etc/nginx/ssl
COPY ./ssl/* /etc/nginx/ssl/
VOLUME ["/var/cache/nginx"]
#
EXPOSE 80 443
#
CMD ["nginx", "-g", "daemon off;"]
