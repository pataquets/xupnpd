FROM gcc

RUN \
  apt-get update && \
  DEBIAN_FRONTEND=noninteractive \
    apt-get install -y uuid-dev \
  && \
  apt-get clean && \
  rm -rf /var/lib/apt/lists/*

COPY . /usr/src/xupnpd
WORKDIR /usr/src/xupnpd

RUN \
  make clean && \
  make x86

ENTRYPOINT [ "./xupnpd" ]
