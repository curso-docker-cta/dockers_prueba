FROM debian
RUN \
sed -i "s/main$/\0 contrib/" /etc/apt/sources.list && \
apt-get update && \
apt-get -y upgrade && \
apt-get -y install apache2 php5 libapache2-mod-php5 && \
a2dismod status && \
a2enmod php5 rewrite headers ssl && \
ln -sf /dev/stdout /var/log/apache2/access.log && \
ln -sf /dev/stderr /var/log/apache2/error.log
EXPOSE 80 443
ENTRYPOINT [ "apache2ctl", "-D", "FOREGROUND" ]
