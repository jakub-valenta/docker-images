FROM debian
MAINTAINER Jakub Valenta version: 0.1

RUN apt-get update && apt-get install -y maven openjdk-8-jre bc wget unzip

RUN adduser --no-create-home --disabled-password --quiet --gecos "" dhus

RUN mkdir /mnt/data-archive
RUN wget https://github.com/jakub-valenta/docker-images/releases/download/product-database/products.tar.gz
RUN tar xf products.tar.gz -C /mnt/data-archive
RUN rm products.tar.gz
RUN chown -R dhus:dhus /mnt/data-archive/

COPY dhus.tar.gz .
RUN tar xf dhus.tar.gz -C /var
RUN rm dhus.tar.gz

RUN wget https://github.com/SentinelDataHub/dhus-distribution/releases/download/1.0/dhus-software-1.0-distribution.zip
RUN unzip dhus-software-1.0-distribution.zip -d /var/dhus/dhus-datahub
RUN rm dhus-software-1.0-distribution.zip

COPY dhus.xml /var/dhus/dhus-datahub/etc/

RUN sed -i 's/Xms12/Xms2/g' /var/dhus/dhus-datahub/start.sh
RUN sed -i 's/Xmx12/Xmx6/g' /var/dhus/dhus-datahub/start.sh
RUN sed -i 's/etc:lib/\$DHUS_HOME\/etc:\$DHUS_HOME\/lib/g' /var/dhus/dhus-datahub/start.sh

RUN chown -R dhus:dhus /var/dhus

EXPOSE 8081


CMD ["/var/dhus/dhus-datahub/start.sh"]

