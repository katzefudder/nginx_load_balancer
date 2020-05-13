FROM ubuntu:18.04

RUN apt-get update && DEBIAN_FRONTEND=noninteractive apt-get install -y \
	curl dnsutils apache2 libapache2-mod-php php unzip \
&& apt-get clean

RUN sed -i -e "s/variables_order = \"GPCS\"/variables_order = \"EGPCS\"/" /etc/php/7.2/cli/php.ini
RUN sed -i -e "s/variables_order = \"GPCS\"/variables_order = \"EGPCS\"/" /etc/php/7.2/apache2/php.ini

RUN rm /var/www/html/index.html

ADD index.php /var/www/html/index.php
ADD img /var/www/html/img
ADD css /var/www/html/css

WORKDIR /var/www/html

ADD start.sh /

ENTRYPOINT ["/start.sh"]
