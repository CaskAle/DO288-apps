# Use the httpd-parent image as base
FROM quay.io/redhattraining/httpd-parent

EXPOSE 8080

LABEL io.openshift.expose-services="8080:http" \
      io.k8s.display-name="Apache HTTP Server" \
      io.k8s.decsription="An ONBUILD modified web server" \
      io.opensift.tags="apache, httpd"

RUN sed -i "s/Listen 80/Listen 8080/g" /etc/httpd/conf/httpd.conf
RUN chmod -R g=u /var/log/httpd /var/run/httpd && \
    chgrp -R 0 /var/log/httpd /var/run/httpd

USER 1001
