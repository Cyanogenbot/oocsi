ARG BUILD_FROM
FROM $BUILD_FROM
RUN apt-get update && \
apt-get install -y --no-install-recommends \
        openjdk-11-jre
COPY requirements.txt ./
RUN pip install --no-cache-dir -r requirements.txt
LABEL MAINTAINER="m.funk@tue.nl"
WORKDIR /opt/docker
COPY --chown=daemon:root 1/opt /opt
COPY --chown=daemon:root opt /opt
EXPOSE 9000 4444
USER daemon
ENTRYPOINT ["/opt/docker/bin/oocsi-web"]
CMD []

