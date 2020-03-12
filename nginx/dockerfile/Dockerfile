FROM centos:7

MAINTAINER xy

RUN yum -y install wget && \
    mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo.bak && \
    wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo && \
    yum -y install epel-release && \
    mkdir /usr/local/server && \
    yum -y install gcc gcc-c++ autoconf automake make cmake ncurses ncurses-devel bison zlib zlib-devel openssl openssl-devel pcre pcre-devel lua lua-devel git && \
    wget http://nginx.org/download/nginx-1.16.0.tar.gz -P /usr/local/src && \
    tar xzvf /usr/local/src/nginx-1.16.0.tar.gz -C /usr/local/src && \
    cd /usr/local/src/nginx-1.16.0 && \
    ./configure --prefix=/usr/local/server/nginx --with-http_ssl_module --with-http_v2_module --with-http_realip_module --with-http_stub_status_module && \
    make && \
    make install && \
    ln -s /usr/local/server/nginx/sbin/nginx /usr/local/sbin

EXPOSE 80 443

CMD ["nginx","-g","daemon off;"]
     
