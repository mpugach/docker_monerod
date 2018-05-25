FROM ubuntu:16.04

LABEL maintainer="Maksym Pugach <pugach.m@gmail.com>"

ENV MONERO_VERSION=0.12.0.0 MONERO_SHA256=928ad08ff0dea2790c7777a70e610b2d33c35a5df5900fbb050cc8c659237636

RUN apt-get update && \
    apt-get install -y curl bzip2 ca-certificates && \
    curl https://downloads.getmonero.org/cli/monero-linux-x64-v$MONERO_VERSION.tar.bz2 -O &&\
    echo "$MONERO_SHA256  monero-linux-x64-v$MONERO_VERSION.tar.bz2" | sha256sum -c - &&\
    tar -xjvf monero-linux-x64-v$MONERO_VERSION.tar.bz2 &&\
    rm monero-linux-x64-v$MONERO_VERSION.tar.bz2 &&\
    ln -s monero-v$MONERO_VERSION /monero &&\
    apt-get autoremove -y curl bzip2 &&\
    apt-get clean && \
    rm -rf /var/lib/apt

EXPOSE 18080 18081 28081 38081

WORKDIR /monero

ENV PATH="/monero:${PATH}"

CMD ["monerod"]
