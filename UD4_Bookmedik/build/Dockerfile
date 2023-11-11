FROM php:7.4-apache
RUN apt-get update && apt-get install -y mariadb-client
RUN docker-php-ext-install mysqli && docker-php-ext-enable mysqli
ADD bookmedik /var/www/html/
RUN chown -R www-data:www-data /var/www/html
EXPOSE 80
ENV DB_USER admin
ENV DB_PASS admin
ENV DB_NAME usuarios
ENV DB_HOST mariadb
ADD script.sh /usr/local/bin/script.sh
ADD bookmedik/schema.sql /opt
RUN chmod +x /usr/local/bin/script.sh
RUN chmod +x /opt/schema.sql
CMD ["/usr/local/bin/script.sh"]


