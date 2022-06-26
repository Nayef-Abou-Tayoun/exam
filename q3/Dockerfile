FROM ubi8/ubi:8.5

RUN yum -y update && yum -y install httpd && yum clean all && mkdir -p /var/www/html

ONBUILD COPY /src /var/www/html
 

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf && chgrp -R 0 /var/log/httpd /var/run/httpd && chmod -R g=u /var/log/httpd /var/run/httpd

USER 1001

EXPOSE 8080

LABEL io.openshift.expose-services="8080:http"


