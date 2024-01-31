FROM quay.io/redhattraining/httpd-parent


ENV DOCROOT=/var/www/html

ONBUILD COPY src/ /var/www/html

RUN chmod -R g=u /var/run/httpd /var/log/httpd && \
    chgrp -R 0 /var/run/httpd /var/log/httpd

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf && \
    sed -i "s/#ServerName www.example.com:80 0.0.0.0.:8080" /etc/httpd/conf/httpd.conf

EXPOSE 8080

USER 1001
