FROM debian:stretch
MAINTAINER Jakub Valenta version: 0.1

RUN apt-get update && apt-get -y dist-upgrade
RUN apt-get -y install cmake git g++ libcurl4-openssl-dev libtinyxml2-dev libdb++-dev libgoogle-glog-dev libboost-all-dev libfuse-dev dpkg-dev libgtest-dev googletest

WORKDIR /usr/src/googletest
RUN cmake . && make && make install

WORKDIR /opt
RUN git clone https://github.com/jakub-valenta/libodata.git
WORKDIR /opt/libodata
