FROM openjdk:8-jre

MAINTAINER Mike Schippers <info@mikeschippers.com>

RUN apt-get update && apt-get install nano &&\
	groupadd -r tibgrp -g 433 && \
	useradd -u 431 -r -m -g tibgrp -d /home/tibusr -s /bin/bash -c "TIBCO Docker image user" tibusr && \
	chown -R tibusr:tibgrp /home/tibusr && \
	mkdir /opt/tibco && \
	chown -R tibusr:tibgrp /opt/tibco && \
	mkdir /tmp/install && \
	chown -R tibusr:tibgrp /tmp/install

USER tibusr	