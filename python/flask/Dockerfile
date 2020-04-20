# Flask   1.1.2
FROM python:3.7-slim-stretch

ARG project_dir=/var/python/flask
ENV PROJECT_DIR=${project_dir}

WORKDIR ${PROJECT_DIR}

RUN set -x && \
pip install flask

CMD ["pip", "show", "flask"]

# docker build -t flask .
# docker run --rm -ti -v $(pwd):/var/python/flask -p 5000:5000 flask python sample.py
