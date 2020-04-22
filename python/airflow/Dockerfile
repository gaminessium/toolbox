#   ____________       _____________
#  ____    |__( )_________  __/__  /________      __
# ____  /| |_  /__  ___/_  /_ __  /_  __ \_ | /| / /
# ___  ___ |  / _  /   _  __/ _  / / /_/ /_ |/ |/ /
#  _/_/  |_/_/  /_/    /_/    /_/  \____/____/|__/  v1.10.9

FROM python:3.7

ARG airflow_home=/usr/local/airflow
ARG airflow_cfg=/usr/local/airflow/airflow.cfg

ENV TZ Asia/Tokyo
ENV AIRFLOW_HOME=${airflow_home}
ENV AIRFLOW_CFG=${airflow_cfg}

RUN mkdir ${airflow_home}
WORKDIR ${airflow_home}

COPY ${AIRFLOW_CFG} ./airflow.cfg

RUN set -x && \
sed -i -e 's%http://.*.ubuntu.com%http://ftp.jaist.ac.jp/pub/Linux%g' /etc/apt/sources.list && \
apt update && \
apt install -y --no-install-recommends libssl-dev libkrb5-dev libsasl2-dev && \
apt install -y --no-install-recommends default-mysql-client default-libmysqlclient-dev python3-mysqldb && \
apt -y clean && \
pip install mysql-connector-python "apache-airflow[mysql]"

RUN airflow initdb

CMD ["bash", "-c", "(airflow webserver & airflow scheduler)"]

# docker build --build-arg airflow_cfg=./airflow.cfg -t airflow .
# docker run --rm -it -p 8080:8080 -v $(pwd)/dags:/usr/local/airflow/dags -v $(pwd)/plugins:/usr/local/airflow/plugins airflow
