FROM seif/docker-mono-fastcgi-nginx:latest

RUN apt-get update && apt-get -y install unzip

ADD https://dockerdemo001.blob.core.windows.net/docker/Demo/Demo02.Web.zip /tmp/Demo02.Web.zip
RUN unzip /tmp/Demo02.Web.zip -d /tmp/www/ && \
 site_dir=$(dirname "`find /tmp/www/ -d -name 'Web.config' | tail -n 1`") && \
 rm -r /var/www && \
 mv -v "$site_dir" /var/www && \
 rm -r /tmp/*
#ADD runit_bootstrap_ext /usr/sbin/runit_bootstrap_ext
#CMD ["/usr/sbin/runit_bootstrap_ext"]
CMD ["/usr/sbin/runit_bootstrap"]