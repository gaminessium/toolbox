# apache-airflow 1.10.10

FROM python:3.7-slim-buster

ARG airflow_version=1.10.10
ARG airflow_home=/airflow
ARG airflow_cfg=./airflow.cfg

ENV TZ Asia/Tokyo
ENV AIRFLOW_VERSION=${airflow_version}
ENV AIRFLOW_HOME=${airflow_home}
ENV AIRFLOW_CFG=${airflow_cfg}

RUN mkdir ${AIRFLOW_HOME}
WORKDIR ${AIRFLOW_HOME}

COPY ${AIRFLOW_CFG} ./airflow.cfg

# apt リポジトリの更新
RUN set -x && \
echo 'deb http://ftp.jp.debian.org/debian buster-updates main contrib' > sources.list && \
apt update

RUN set -x && \
apt install -y --no-install-recommends build-essential libssl-dev libkrb5-dev libsasl2-dev && \
apt install -y --no-install-recommends python3-dev python3-distutils-extra && \
apt install -y --no-install-recommends default-mysql-client default-libmysqlclient-dev python3-mysqldb

RUN set -x && \
pip install PyMySQL mysqlclient mysql-connector-python && \
pip install sqlalchemy apache-airflow[mysql,celery,crypto]

RUN airflow initdb

CMD ["bash", "-c", "(airflow webserver & airflow scheduler)"]

# docker build --build-arg airflow_cfg=./airflow.cfg -t airflow ./
# docker run --rm -ti -p 8080:8080 -v $(pwd)/dags:/usr/local/airflow/dags -v $(pwd)/plugins:/usr/local/airflow/plugins airflow
