FROM ubuntu:xenial
MAINTAINER james.wilkins@fasthosts.co.uk
RUN \
  sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
  DEBIAN_FRONTEND=noninteractive apt-get -y update && \
  DEBIAN_FRONTEND=noninteractive apt-get -y upgrade && \
  DEBIAN_FRONTEND=noninteractive apt-get -y install supervisor && \
  mkdir -p /var/log/supervisor && \
  mkdir -p /tmp/sockets && \
  mkdir -p /init/ && \
  mkdir -p /hooks/ && \
  DEBIAN_FRONTEND=noninteractive apt-get -y clean && \
  rm -rf /var/lib/apt/lists/*
COPY supervisord.conf /etc/supervisor/supervisord.conf
COPY init/* /init/
COPY hooks/* /hooks/
ENTRYPOINT ["/bin/bash", "-e", "/init/entrypoint"]
CMD ["run"]
#ENTRYPOINT ["/bin/bash"]

