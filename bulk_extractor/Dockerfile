FROM ubuntu:focal

RUN apt update --fix-missing && \
    DEBIAN_FRONTEND=noninteractive apt install -y build-essential flex libexpat1-dev libxml2-utils libssl-dev libtool make pkg-config zlib1g-dev git wget && \
    mkdir /build && cd /build && \
    wget https://github.com/libyal/libewf-legacy/releases/download/20140812/libewf-20140812.tar.gz && \
    tar zxvf libewf-20140812.tar.gz && \
    cd libewf-20140812 && \
    ./configure && \
    make && make install && ldconfig && \
    cd /build && \
    git clone --recursive https://github.com/simsong/bulk_extractor.git && \
    cd bulk_extractor && \
    ./bootstrap.sh && \
    ./configure && \
    make && make install && \
    cd / && rm -rf /build

WORKDIR /data

ENTRYPOINT ["bulk_extractor"]
