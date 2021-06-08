#docker build -t miejemplo2 .
#docker run -d -p 8000:80 miejemplo2
FROM centos:7

LABEL version="1.2"
LABEL author="Yo mero"

ENV MIVARIABLE="LA VARIABLE"

RUN yum -y install httpd

ADD https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/css/bootstrap.min.css /var/www/html
ADD https://cdn.jsdelivr.net/npm/bootstrap@5.0.1/dist/js/bootstrap.bundle.min.js /var/www/html
COPY ./index.html /var/www/html
COPY proyecto_x /var/www/html

RUN echo "$(whoami)" > /var/www/html/user1.html

RUN useradd toneyglobe
USER toneyglobe

RUN echo "$(whoami)" > /tmp/user2.html

USER root 

RUN cp /tmp/user2.html /var/www/html/user2.html

RUN echo "$(ls)" > /var/www/html/ls.html

WORKDIR /var/www/html

RUN echo "$(ls)" > /var/www/html/ls2.html

WORKDIR /var/www/html/proyecto_x

RUN echo "$(ls)" > /var/www/html/ls3.html

RUN echo "$MIVARIABLE" > /var/www/html/env.html

VOLUME /var/www/html

CMD ["apachectl", "-DFOREGROUND"]