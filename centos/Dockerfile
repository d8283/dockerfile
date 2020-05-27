FROM centos:7

MAINTAINER X 

ENV LANG en_US.UTF-8

RUN ln -sf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && \
    echo 'Asia/Shanghai' > /etc/timezone && \
    curl -o /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo && \
    yum -y install epel-release && \
    yum clean all && \
    yum makecache fast && \
    yum -y install net-tools telnet
