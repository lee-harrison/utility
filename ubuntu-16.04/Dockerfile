FROM 1and1internet/ubuntu-16.04
MAINTAINER lee.harrison@fasthosts.com
RUN \
  sed -i 's/# \(.*multiverse$\)/\1/g' /etc/apt/sources.list && \
  DEBIAN_FRONTEND=noninteractive apt-get -y update && \
  DEBIAN_FRONTEND=noninteractive apt-get -y upgrade && \
  DEBIAN_FRONTEND=noninteractive apt-get -y install telnet && \
  DEBIAN_FRONTEND=noninteractive apt-get -y clean && \
  rm -rf /var/lib/apt/lists/*
CMD ["/bin/bash"]
