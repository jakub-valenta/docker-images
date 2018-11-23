FROM centos
MAINTAINER Jakub Valenta version: 0.1

RUN yum -y install epel-release centos-release-scl
RUN yum -y install devtoolset-7
RUN yum -y install devtoolset-7-gcc-c++ devtoolset-7-make cmake3 git vim
RUN yum -y install fuse-devel glog-devel libdb-cxx-devel boost148-devel libcurl-devel tinyxml2-devel gflags-devel

RUN ln -s /usr/include/boost148/boost /usr/include/boost
RUN for I in `ls /usr/lib64/boost148`; do ln -s /usr/lib64/boost148/$I /usr/lib64/$I; done

WORKDIR /opt
RUN git clone https://github.com/jakub-valenta/libodata.git

RUN scl enable devtoolset-7 bash
