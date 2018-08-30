FROM onedata/builder
MAINTAINER Jakub Valenta version: 0.1

RUN apt-get update
RUN apt-get install -y libcurl4-openssl-dev libdb++-dev libgoogle-glog-dev libboost-all-dev libtinyxml2-dev

COPY odata-libodata-dev.deb /opt
COPY odata-libodata.deb /opt
RUN dpkg -i /opt/odata-libodata.deb
RUN dpkg -i /opt/odata-libodata-dev.deb
