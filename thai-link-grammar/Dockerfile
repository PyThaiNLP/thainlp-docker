FROM ubuntu:focal
ARG DEBIAN_FRONTEND=noninteractive
ENV TZ=Etc/UTC
RUN apt-get update && apt-get install git build-essential python3-dev libpcre2-dev python-is-python3 libtre-dev wget automake locales libtool flex m4 autoconf-archive autoconf pkg-config swig libthai-dev help2man -y && rm -rf /var/lib/apt/lists/*
RUN (echo "en_US.UTF-8 UTF-8" > /etc/locale.gen && \
     echo "ru_RU.UTF-8 UTF-8" >> /etc/locale.gen && \
     echo "he_IL.UTF-8 UTF-8" >> /etc/locale.gen && \
     echo "de_DE.UTF-8 UTF-8" >> /etc/locale.gen && \
     echo "lt_LT.UTF-8 UTF-8" >> /etc/locale.gen && \
     echo "fa_IR.UTF-8 UTF-8" >> /etc/locale.gen && \
     echo "ar_AE.UTF-8 UTF-8" >> /etc/locale.gen && \
     echo "kk_KZ.UTF-8 UTF-8" >> /etc/locale.gen && \
     echo "tr_TR.UTF-8 UTF-8" >> /etc/locale.gen && \
     echo "th_TH.UTF-8 UTF-8" >> /etc/locale.gen)
RUN locale-gen en_US.UTF-8 ru_RU.UTF-8 he_IL.UTF-8 de_DE.UTF-8 lt_LT.UTF-8 fa_IR ar_AE.UTF-8 kk_KZ.UTF-8 tr_TR.UTF-8 th_TH.UTF-8
ENV LANG th_TH.UTF-8 
ENV LANGUAGE th_TH:th
ENV LC_ALL th_TH.UTF-8
ENV PYTHONPATH=/usr/local/lib/python3.8/site-packages
RUN git clone https://github.com/kaamanita/link-grammar.git
WORKDIR link-grammar
RUN ./autogen.sh --disable-java-bindings --enable-python-bindings
RUN ./configure --disable-java-bindings --enable-python-bindings
RUN make
RUN make install
RUN ldconfig