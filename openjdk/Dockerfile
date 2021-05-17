FROM registry.cn-hangzhou.aliyuncs.com/d8283/centos:7

MAINTAINER X 

ENV JAVA_HOME /usr/lib/jvm/java
ENV JRE_HOME=${JAVA_HOME}/jre
ENV CLASSPATH .:${JAVA_HOME}/lib:${JRE_HOME}/lib

RUN echo '* - nofile 655350' >> /etc/security/limits.conf && \
    sed -i -n '/^#/ p' /etc/security/limits.d/20-nproc.conf && \
    echo '* - nproc 655350' >> /etc/security/limits.d/20-nproc.conf && \
    yum -y install java-1.8.0-openjdk java-1.8.0-openjdk-devel && \
    yum -y install mysql-connector-java
