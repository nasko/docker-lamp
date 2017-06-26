FROM library/ubuntu:17.04
MAINTAINER Atanas Vasilev <atanas.vasilev@gmail.com>

RUN apt-get update -y && \
	apt-get install apt-utils -y && \
	apt-get install php -y && \
	apt-get install php-cli -y && \
	apt-get install libapache2-mod-php -y && \
	apt-get install php-mcrypt -y && \
	apt-get install php-mysql -y && \
	apt-get install php-pear -y && \
	apt-get install libmcrypt-dev -y && \
	apt-get install mcrypt -y && \
	apt-get install php-curl -y && \
	apt-get install php-mbstring -y && \
	apt-get install php-gd -y && \
	apt-get install php-imagick -y && \
	apt-get install php-json -y && \
	apt-get install php-xml -y

RUN apt-get update -y && \
	apt-get install apache2 -y && \
	a2enmod rewrite

RUN echo "ServerName localhost" | tee /etc/apache2/conf-available/servername.conf && \
    a2enconf servername

RUN apt-get update -y && \
	apt-get install curl -y && \
	apt-get install less -y && \
	apt-get install vim -y

RUN	apt-get clean && \
	rm -rf \var\lib\lists\*

RUN service apache2 restart
EXPOSE 80
CMD ["apache2ctl", "-D", "FOREGROUND"]