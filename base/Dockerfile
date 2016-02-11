FROM 137112412989.dkr.ecr.ap-northeast-1.amazonaws.com/amazonlinux:latest

RUN yum -y update && \
    yum -y install openssh-server

RUN echo "root:" | chpasswd -e && \
    sed -ri 's/^#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config && \
    sed -ri 's/^#PermitEmptyPasswords no/PermitEmptyPasswords yes/' /etc/ssh/sshd_config && \
    sed -ri 's/^#PermitRootLogin yes/PermitRootLogin yes/' /etc/ssh/sshd_config && \
    /etc/init.d/sshd start

EXPOSE 22 17022
