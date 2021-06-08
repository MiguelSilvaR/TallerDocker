#docker build -t miejemplo1 .
#docker run -d -p 8000:80 miejemplo1

FROM centos:7

RUN yum -y install httpd

CMD ["apachectl", "-DFOREGROUND"]