FROM ubuntu:xenial
MAINTAINER Deepak

ENV IFIN input
ENV IFOUT output1 output2 output3 output4 output5

RUN export DEBIAN_FRONTEND=noninteractive && apt-get update && apt-get install -y -q \
	net-tools \
	iproute \
	inetutils-ping \
	nginx \
 	python \
	python-yaml \
	python3 \
	python3-pip \
	curl

ADD start.sh start.sh
RUN chmod +x start.sh
ADD stop.sh stop.sh
RUN chmod +x stop.sh

ADD nginx.conf /etc/nginx/nginx.conf
ADD log_intf_statistics.py log_intf_statistics.py

WORKDIR /

RUN mkdir /tngbench_share

# normal entry point
CMD /bin/bash
