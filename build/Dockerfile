FROM arm64v8/php:8.4.2-apache-bookworm
RUN apt update && apt upgrade -y
COPY ./_files_to_export_on_webserver/. /var/www/html/
COPY ./html-and-images/. /var/www/html
RUN chown -R www-data:www-data /var/www/
RUN a2enmod remoteip
