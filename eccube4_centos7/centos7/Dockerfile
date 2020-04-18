FROM hiabe/centos7-systemd

MAINTAINER hiabe
RUN yum -y install httpd mod_ssl
#RUN /bin/cp /usr/share/zoneinfo/Asia/Tokyo /etc/localtime

# -----------------------------------------------------------------------------
# Apache 2.4 + (PHP 7.3 from Remi)
# -----------------------------------------------------------------------------
RUN yum -y install http://rpms.remirepo.net/enterprise/remi-release-7.rpm
RUN yum -y install epel-release yum-utils

RUN yum-config-manager --disable remi-php54
RUN yum-config-manager --enable remi-php73

RUN yum install -y php php-common php-mbstring php-gd php-xml php-xmlrpc\
 php-devel php-cli php-pdo php-pgsql php-mysql php-odbc php-pear php-mcrypt\
 php-pecl-apcu php-intl php-zip php-mysqli php-curl php-xmlrpc

#Install composer
#RUN curl -sS https://getcomposer.org/installer | php \
#&& mv composer.phar /usr/local/bin/composer

#set the files for EC-CUBE

#httpd.conf

#mysqld
RUN systemctl enable httpd.service

EXPOSE 80 443

#mysqld,httpdの起動スクリプトの実行
CMD ["/usr/sbin/init"]