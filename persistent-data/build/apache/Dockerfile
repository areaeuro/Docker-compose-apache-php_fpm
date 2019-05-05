FROM httpd:2.4

# SET TIMEZONE && GENERATE LOCALES
ENV TIMEZONE=Europe/Madrid
RUN apt-get update && \
    apt-get install -y apt-utils && \
    apt-get install -y locales && \
    locale-gen en_US.UTF-8 en_GB.UTF-8 de_DE.UTF-8 es_ES.UTF-8 fr_FR.UTF-8 it_IT.UTF-8 km_KH sv_SE.UTF-8 fi_FI.UTF-8 && \
    echo $TIMEZONE > /etc/timezone  && \
    cp /usr/share/zoneinfo/${TIMEZONE} /etc/localtime

# SET www-data UID and GID to 1000
RUN usermod -u 1000 www-data && \
    groupmod -g 1000 www-data

EXPOSE 80

VOLUME /var/www/html

WORKDIR /var/www/html
