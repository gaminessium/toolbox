# apache-airflow 1.10.10

FROM python:3.7-slim-buster

ARG airflow_version=1.10.10
ARG airflow_home=/airflow
ARG airflow_cfg=./airflow.cfg

ENV TZ Asia/Tokyo
ENV AIRFLOW_VERSION=${airflow_version}
ENV AIRFLOW_HOME=${airflow_home}
ENV AIRFLOW_CFG=${airflow_cfg}

# apt リポジトリの更新
RUN set -x && \
echo 'deb http://ftp.jp.debian.org/debian/ buster main contrib non-free' > sources.list && \
apt-get update

RUN mkdir ${AIRFLOW_HOME}
WORKDIR ${AIRFLOW_HOME}

COPY ${AIRFLOW_CFG} ./airflow.cfg

RUN set -x && \
apt-get install -y --no-install-recommends build-essential python3-distutils

RUN set -x && \
pip install apache-airflow==${airflow_version}

RUN apt-get clean

RUN airflow initdb

ENTRYPOINT [ "airflow" ]

CMD ["webserver"]

# docker build --build-arg airflow_cfg=./airflow.cfg -t airflow ./
# docker run --rm -ti -p 8080:8080 -v $(pwd)/dags:/usr/local/airflow/dags -v $(pwd)/plugins:/usr/local/airflow/plugins airflow
