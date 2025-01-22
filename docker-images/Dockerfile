FROM debian:latest

RUN apt update && apt install apache2 -y
 
COPY ./beryllium /var/www/html

CMD ["apachectl", "-D", "FOREGROUND"]



