FROM centos:centos7

MAINTAINER hiabe
ENV container docker
RUN (cd /lib/systemd/system/sysinit.target.wants/; \
for i in *; do [ $i == systemd-tmpfiles-setup.service ] || rm -f $i; done); \
rm -f /lib/systemd/system/multi-user.target.wants/*;\
rm -f /etc/systemd/system/*.wants/*;\
rm -f /lib/systemd/system/local-fs.target.wants/*; \
rm -f /lib/systemd/system/sockets.target.wants/*udev*; \
rm -f /lib/systemd/system/sockets.target.wants/*initctl*; \
rm -f /lib/systemd/system/basic.target.wants/*;\
rm -f /lib/systemd/system/anaconda.target.wants/*; \
yum update -y; \
# 後でMySQLをインストールするためここでWGET,EPEL,Remiを追加
yum install -y wget epel-release; \ 
cd /etc/yum.repos.d; \
wget http://rpms.famillecollet.com/enterprise/remi.repo; 

VOLUME [ "/sys/fs/cgroup" ]
CMD ["/usr/sbin/init"]