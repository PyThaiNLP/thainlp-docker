FROM ubuntu:focal
ARG DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC
RUN apt-get update && apt-get install build-essential wget automake libtool m4 autoconf-archive autoconf pkg-config swig libthai-dev help2man -y && rm -rf /var/lib/apt/lists/*
RUN wget https://github.com/tlwg/thpronun/releases/download/v0.2.0/thpronun-0.2.0.tar.xz
RUN tar xf thpronun-0.2.0.tar.xz
WORKDIR "/thpronun-0.2.0"
RUN ./configure --prefix=/usr
RUN make && make install