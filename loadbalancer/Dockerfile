FROM openresty/openresty:1.15.8.3-2-alpine

# add nginx' host configuration
RUN rm /etc/nginx/conf.d/default.conf

ADD nginx.conf /etc/nginx/nginx.conf

# nginx consul template
ADD nginx_app.conf /etc/nginx/conf.d/nginx.conf

ADD start.sh /

ENTRYPOINT ["/start.sh"]
