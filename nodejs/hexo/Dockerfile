# hexo-cli@3.1.0

FROM node:latest

ARG project_dir=/var/project/hexo

ENV PROJECT_DIR=${project_dir}

RUN set -x && \
   npm install -g hexo-cli && \
   mkdir -p ${project_dir}

WORKDIR ${project_dir}

CMD [ "bash" ]

# docker build -t hexo:writer .
# docker run --rm -u $(id -u) -ti -v $(pwd):/var/project/hexo hexo:writer hexo init myblog
# docker run --rm -u $(id -u) -ti -v $(pwd):/var/project/hexo -w /var/project/hexo/myblog -p 4000:4000 hexo:writer hexo server
