FROM  phusion/baseimage:0.11

MAINTAINER  Mariusz Kraj <mariusz.kraj@codibly.com>

RUN echo "deb http://archive.ubuntu.com/ubuntu trusty main universe" > /etc/apt/sources.list

RUN apt-get -y update

RUN DEBIAN_FRONTEND=noninteractive apt-get install -y -q \
    python-software-properties \
    software-properties-common \
    unzip

ENV JAVA_VER 11
ENV JAVA_HOME /usr/lib/jvm/java-${JAVA_VER}-oracle

RUN add-apt-repository -y ppa:linuxuprising/java && \
    apt-get update && \
    echo "oracle-java${JAVA_VER}-installer shared/accepted-oracle-license-v1-2 select true" | /usr/bin/debconf-set-selections && \
    apt-get install -y --no-install-recommends oracle-java${JAVA_VER}-installer oracle-java${JAVA_VER}-set-default && \
    apt-get clean && \
    rm -rf /var/cache/oracle-jdk${JAVA_VER}-installer

RUN update-java-alternatives -s java-${JAVA_VER}-oracle

RUN echo "export JAVA_HOME=/usr/lib/jvm/java-${JAVA_VER}-oracle" >> ~/.bashrc

RUN apt-get clean && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*

CMD ["/sbin/my_init"]