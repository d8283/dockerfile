FROM centos:7

MAINTAINER xiayong

WORKDIR /usr/local/src

ENV MYSQL_NAME mysql-5.7.15-linux-glibc2.5-x86_64
ENV PATH $PATH:/usr/local/server/mysql/bin    

ADD $MYSQL_NAME.tar.gz .

RUN yum -y install libaio* && \
    mkdir /usr/local/server && \
    mv $MYSQL_NAME /usr/local/server/mysql && \
    groupadd -g 501 mysql && useradd -u 501 -s /sbin/nologin -g mysql mysql && \
    mkdir /pub/data/{mysql,log} -p && mkdir /tmp/mysql -p && \
    /usr/local/server/mysql/bin/mysqld \
    --initialize-insecure \
    --user=mysql \
    --basedir=/usr/local/server/mysql \
    --datadir=/pub/data/mysql && \
    chown -R root:mysql /usr/local/server/mysql && \
    chown -R mysql:mysql /pub/data && \
    chown -R mysql:mysql /tmp/mysql && \
    echo -e "[mysqld]\ndatadir=/pub/data/mysql\nsocket=/tmp/mysql.sock\nuser=mysql\nsymbolic-links=0\nlog-error=/pub/data/log/mysqld.log" > /etc/my.cnf && \
    \cp /usr/local/server/mysql/support-files/mysql.server /etc/init.d/mysqld && \
    sed -i "s#/usr/local/mysql#/usr/local/server/mysql#g" /etc/init.d/mysqld && \
    chkconfig --add mysqld && \
    /etc/init.d/mysqld start && \
    mysqladmin -uroot password '1234xpxp' && \
    mysql -uroot -p1234xpxp -e "grant all on *.* to root@'%' identified by '1234xpxp';" && \
    sed -i 's#&$##g' /etc/init.d/mysqld

EXPOSE 3306

CMD ["/etc/init.d/mysqld","start"]

