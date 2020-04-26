# diagrams   0.8.2
FROM python:3.7-slim-stretch

ARG diagram_dir=/var/python/diagrams
ENV DIAGRAM_DIR=${diagram_dir}

WORKDIR ${DIAGRAM_DIR}

# 日本語フォントのダウンロード
ADD https://ipafont.ipa.go.jp/IPAexfont/ipaexg00401.zip /root/.fonts/ipafont.zip

RUN set -x && \
echo 'deb http://ftp.jp.debian.org/debian buster-updates main contrib' > sources.list && \
apt update && \
apt install -y unzip graphviz && \
pip install diagrams

# 日本語フォントの展開とインストール
RUN set -x && \
unzip /root/.fonts/ipafont.zip -d /root/.fonts && \
fc-cache -fv

CMD ["pip", "show", "diagrams"]

# docker build -t diagrams .
# docker run --rm -v $(pwd):/var/python/diagrams diagrams python diagram.py
