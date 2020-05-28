# nginx/1.17.10
FROM nginx

ARG project_dir=/usr/share/nginx/html
ARG nginx_conf=/etc/nginx/nginx.conf

WORKDIR ${project_dir}

ENTRYPOINT [ "nginx" ]

CMD [ "-v" ]

# docker build -t nginx .

# docker run --rm -ti -v $(pwd)/nginx.conf:/etc/nginx/nginx.conf:ro -p 8080:80 nginx bash
# service nginx start
