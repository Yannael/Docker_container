FROM docker-cdh54

MAINTAINER Yann Ael Le Borgne

RUN  yum install -y http://mirror.oss.ou.edu/epel/6/i386/epel-release-6-8.noarch.rpm
RUN  yum install -y R
RUN  yum install -y --nogpgcheck https://download2.rstudio.org/rstudio-server-rhel-0.99.484-x86_64.rpm
RUN  useradd guest
RUN echo guest | /usr/bin/passwd guest --stdin
RUN echo "nohup /usr/lib/rstudio-server/bin/rserver --server-daemonize 0&" >> /usr/bin/cdh_centos_startup_script.sh

EXPOSE 8787




