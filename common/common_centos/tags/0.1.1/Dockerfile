FROM centos:7

COPY ./epel-testing.repo /etc/yum.repos.d/ 

COPY ./epel-testing.repo.rpmnew /etc/yum.repos.d/ 

COPY ./epel.repo /etc/yum.repos.d/ 

COPY ./epel.repo.rpmnew /etc/yum.repos.d/ 

RUN yum update -y  && yum install wget -y && \ 
    cd /etc/pki/rpm-gpg && wget http://dl.fedoraproject.org/pub/epel/RPM-GPG-KEY-EPEL-7 && \
    rm -f /etc/yum.repos.d/CentOS-Media.repo  && \
    chmod 644 /etc/yum.repos.d/epel* 

RUN yum update -y



