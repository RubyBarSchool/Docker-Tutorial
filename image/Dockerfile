FROM centos:latest

RUN cd /etc/yum.repos.d/
RUN sed -i 's/mirrorlist/#mirrorlist/g' /etc/yum.repos.d/CentOS-*
RUN sed -i 's|#baseurl=http://mirror.centos.org|baseurl=http://vault.centos.org|g' /etc/yum.repos.d/CentOS-*
RUN cd ../..
RUN yum update -y
RUN yum install httpd httpd-tools -y
RUN yum install epel-release -y
RUN yum update -y
RUN yum install htop -y

WORKDIR /var/www/html
EXPOSE 80

ADD ./test.html /var/www/html/

ENTRYPOINT [ "httpd" ]
CMD [ "-D", "FOREGROUND" ]
