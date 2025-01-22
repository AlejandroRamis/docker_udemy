
FROM debian:latest

# Actualizar listas de paquetes e instalar Apache
RUN apt update && apt install apache2 -y

# Exponer el puerto 80 para Apache
EXPOSE 80

# Iniciar Apache en modo foreground (ejecuta apache en primer plano)
CMD ["apachectl", "-D", "FOREGROUND"]
