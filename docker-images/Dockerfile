#Seleccionamos el sistema operativo y su version
FROM debian:latest

#Ponemos una etiqueta al dockerfile
LABEL version=1.0

#Actualizamos y instalamos apache
RUN apt update && apt install apache2 -y

#Copiamos la ruta donde se hospeda nuestra pagina web en la ruta de destino de apache
COPY ./beryllium /var/www/html 

#Creamos un html en dicha ruta y dentro un un echo
RUN echo "$(whoami)" > /var/www/html/user1.html

#Hasta ahora hemos trabajado con el user root, ahora creamos un nuevo usuario
RUN useradd ciber

#Trabajamos con ese user
USER ciber

#Con este usuario, creamos un html es dicha ruta con un echo
#No lo creamos en /var/www/html porque el usuario de ciber no tiene permisos de root de apache
RUN echo "$(whoami)" > /tmp/user2.html

#Usamos el  user root con permisos para copiar el fichero hacia /var/www/html
USER root

#Copiamos este fichero de una ruta a otra para imprimirlo en nuestra web
RUN cp /tmp/user2.html /var/www/html/user2.html

#Iniciamos apache en segundo plano 
CMD ["apachectl", "-D", "FOREGROUND"]



