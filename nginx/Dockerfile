ARG version=alpine
FROM nginx:${version}

MAINTAINER musicode <musicode@qq.com>

COPY nginx.conf /etc/nginx/
RUN /etc/nginx/conf.d/*.conf \
    && echo "upstream php-upstream { server: ${PHP_FPM_SERVICE_NAME}:${PHP_FPM_SERVICE_PORT}; }" > /etc/nginx/conf.d/upstream.conf

CMD ["nginx", "-g", "daemon off;"]

EXPOSE 80
