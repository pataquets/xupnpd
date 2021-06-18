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
  sed -i \
    "s/cfg.ssdp_interface='lo'/cfg.ssdp_interface='any'/" \
    xupnpd.lua

RUN \
  make clean && \
  make

ENTRYPOINT [ "./xupnpd-x86" ]
