FROM alpine

MAINTAINER Greg Nilchee <gnilchee@gmail.com>

RUN apk update && apk add wget ca-certificates && \
    mkdir /opt && cd /opt && \
    wget https://github.com/prometheus/prometheus/releases/download/v1.2.1/prometheus-1.2.1.linux-amd64.tar.gz && \
    tar -xzf prometheus-1.2.1.linux-amd64.tar.gz && \
    rm -rf /opt/*tar.gz && \
    mv /opt/prometheus-* /opt/prometheus

COPY prometheus.yml /opt/prometheus/prometheus.yml
CMD /opt/prometheus/prometheus -config.file=/opt/prometheus/prometheus.yml
