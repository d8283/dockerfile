FROM registry.cn-hangzhou.aliyuncs.com/d8283/openjdk:1.8

MAINTAINER X

ENV VERSION 9.0.35
ENV CATALINA_HOME /usr/local/tomcat
ENV PATH $PATH:$CATALINA_HOME/bin

ADD apache-tomcat-${VERSION}.tar.gz /usr/local/src

RUN mv /usr/local/src/apache-tomcat-${VERSION} /usr/local/tomcat

CMD ["catalina.sh","run"]
