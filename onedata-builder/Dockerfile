FROM onedata/builder
MAINTAINER Jakub Valenta version: 0.1

RUN apt-get install libcurl4-openssl-dev libdb++-dev libgoogle-glog-dev libboost-all-dev

WORKDIR /opt
RUN git clone https://github.com/leethomason/tinyxml2.git
WORKDIR /opt/tinyxml2
RUN git checkout 6.2.0
RUN cmake . && make && make install

WORKDIR /opt
RUN git clone https://github.com/jakub-valenta/libodata.git
WORKDIR /opt/libodata
RUN cmake . && make && make install

