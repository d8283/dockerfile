FROM registry.cn-hangzhou.aliyuncs.com/d8283/centos:7

MAINTAINER X 

ENV JAVA_HOME /usr/lib/jvm/java
ENV JRE_HOME=${JAVA_HOME}/jre
ENV CLASSPATH .:${JAVA_HOME}/lib:${JRE_HOME}/lib

RUN echo '* - nofile 655350' >> /etc/security/limits.conf && \
    sed -i -n '/^#/ p' /etc/security/limits.d/20-nproc.conf && \
    echo '* - nproc 655350' >> /etc/security/limits.d/20-nproc.conf && \
    #echo "net.ipv4.tcp_keepalive_time = 300" >> /etc/sysctl.conf && \ #容器里的sysctl使用的还是宿主机的sysctl,配置在容器里不起作用。
    #echo "net.ipv4.tcp_keepalive_intvl = 10" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_keepalive_probes = 5" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_tw_reuse = 1" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_tw_recycle = 0" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_timestamps = 1" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_ecn = 0" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_sack = 1" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_dsack = 0" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_fin_timeout = 3" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_rmem = 4096 2097152 16777216" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_wmem = 4096 2097152 16777216" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_max_orphans = 3276800" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_max_tw_buckets = 18000" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_no_metrics_save = 1" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_max_syn_backlog = 262144" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_synack_retries = 2" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_syn_retries = 2" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_syncookies = 1" >> /etc/sysctl.conf && \
    #echo "net.ipv4.icmp_echo_ignore_broadcasts = 1" >> /etc/sysctl.conf && \
    #echo "net.ipv4.conf.all.accept_redirects = 0" >> /etc/sysctl.conf && \
    #echo "net.ipv4.conf.all.accept_source_route = 0" >> /etc/sysctl.conf && \
    #echo "net.ipv4.conf.default.accept_source_route = 0" >> /etc/sysctl.conf && \
    #echo "net.ipv4.tcp_mem = 196608 2097152 3145728" >> /etc/sysctl.conf && \
    #echo "net.ipv4.ip_local_port_range = 1024 65000" >> /etc/sysctl.conf && \
    #echo "net.core.rmem_default = 16777216" >> /etc/sysctl.conf && \
    #echo "net.core.wmem_default = 16777216" >> /etc/sysctl.conf && \
    #echo "net.core.rmem_max = 16777216" >> /etc/sysctl.conf && \
    #echo "net.core.wmem_max = 16777216" >> /etc/sysctl.conf && \
    #echo "net.core.somaxconn = 262144" >> /etc/sysctl.conf && \
    #echo "net.core.netdev_max_backlog = 300000" >> /etc/sysctl.conf && \
    #echo "fs.file-max = 1280000" >> /etc/sysctl.conf && \
    #echo "net.unix.max_dgram_qlen = 10000" >> /etc/sysctl.conf && \
    #echo "vm.min_free_kbytes = 1048576" >> /etc/sysctl.conf && \
    #echo "vm.swappiness = 0" >> /etc/sysctl.conf && \
    yum -y install java-1.8.0-openjdk java-1.8.0-openjdk-devel && \
    yum -y install mysql-connector-java
