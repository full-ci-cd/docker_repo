FROM fullcicd/common_centos:0.1.2
RUN yum install -y openssh-server openssh-clients 
RUN ssh-keygen -P "" -t rsa -f /etc/ssh/ssh_host_rsa_key
RUN ssh-keygen -P "" -t ed25519 -f /etc/ssh/ssh_host_ec25519_key
RUN ssh-keygen -P "" -t dsa -f /etc/ssh/ssh_host_dsa_key

RUN /usr/sbin/sshd
RUN yum update && yum install -y  sudo python unzip
RUN mkdir /var/run/sshd
RUN echo 'root:screencast' | chpasswd
#RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config

# SSH login fix. Otherwise user is kicked off after login
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd

ENV NOTVISIBLE "in users profile"
RUN echo "export VISIBLE=now" >> /etc/profile

EXPOSE 22

