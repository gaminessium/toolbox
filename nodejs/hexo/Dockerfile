# hexo-cli@3.1.0

FROM node:latest

ARG project_dir=/var/project/hexo

ENV PROJECT_DIR=${project_dir}

RUN set -x && \
   npm install -g hexo-cli && \
   mkdir -p ${project_dir} && \
   hexo version

WORKDIR ${project_dir}

ENTRYPOINT [ "hexo" ]
CMD [ "help" ]
