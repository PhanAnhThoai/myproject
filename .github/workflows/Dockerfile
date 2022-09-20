FROM ubuntu
MAINTAINER NhanLe

RUN apt-get -y update
RUN apt-get install -y software-properties-common
RUN apt-get -y install iputils-ping
RUN apt-get -y install net-tools vim
RUN apt-get -y install tzdata
RUN apt-get -y install apache2
RUN apt-get -y install php libapache2-mod-php php-mysql
RUN apt-get -y install certbot python3-certbot-nginx

EXPOSE 80
CMD ["/usr/sbin/apachectl", "-D", "FOREGROUND"]