FROM registry.gitlab.steamos.cloud/steamrt/sniper/platform
LABEL author="BuSheeZy"
LABEL maintainer="BuSheeZy@BadServers.net"
LABEL org.opencontainers.image.source="https://github.com/BadServersNet/sniper-css-yolk"

RUN apt-get update \
  && apt-get install -y iproute2 libtinfo5:i386 python3 \
  && rm -rf /var/lib/apt/lists/* \
  && adduser --disabled-password --home /home/container container

USER container
ENV USER=container
ENV HOME=/home/container
WORKDIR /home/container

COPY ./entrypoint.sh /entrypoint.sh
COPY ./startup.py /startup.py
CMD [ "/bin/bash", "/entrypoint.sh" ]
