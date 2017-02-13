FROM nginx

ADD nginx.conf /etc/nginx/nginx.conf
ADD sites-enabled/* /etc/nginx/conf.d/

RUN mkdir /data && mkdir /data/wwwroot && mkdir /data/log && mkdir /data/log/nginx
RUN usermod -u 1000 www-data
RUN chown -R www-data: /data/

EXPOSE 80
VOLUME ["/data"]
