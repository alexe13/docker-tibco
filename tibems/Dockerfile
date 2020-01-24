FROM tibbase:1.0.0

MAINTAINER Mike Schippers <info@mikeschippers.com>

ARG EMS_VERSION=8.5
ARG FOLDER_NAME=TIB_ems-ce_8.5.1
ADD TIB_ems*.zip /tmp/install/
COPY certs /tmp/install/certs/

RUN unzip /tmp/install/TIB_ems*.zip -d /tmp/install/tibems/ && \
cd /tmp/install/tibems/${FOLDER_NAME} && \
for f in tar/*; do tar -C / -xvf $f; done && \
cp -r /opt/tibco/ems/${EMS_VERSION}/samples/config /opt/tibco/ems/${EMS_VERSION}/config && \
mkdir /opt/tibco/ems/${EMS_VERSION}/bin/datastore && \
cp -r /tmp/install/certs/. /opt/tibco/ems/${EMS_VERSION}/bin/ 2>/dev/null || : && \
chmod -R 777 /opt/tibco && \
rm -rf /tmp/install/tibems /tmp/install/TIB_ems*.zip

EXPOSE 7222

WORKDIR /opt/tibco/ems/8.5/bin/

ENTRYPOINT ["./tibemsd", "-config", "../config/tibemsd.conf"]