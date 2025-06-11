# Indicar la imagen base (nginx)
# alpine es una distribucion de linux muy ligera 
FROM nginx:alpine

# Instalar Java 8
# Ejecutar un comando en terminal
# apk es un comando de alpine
# Ejecutar un comando como si estuvieramos en terminal "RUN"
# apk es propio del comando alpine
# La primera opcion indica actualizar/agregar el paquete y despues descargar openjdk8
# Despues eliminar el cache.
RUN apk -U add openjdk \
    && rm -rf /var/cache/apk/*;
# Libreria ttf-dejavu
RUN apk add ttf-dejavu 

# Instalar los microservicios
ENV JAVA_OPTS=""

# Agregar variables de entorno
ARG JAR_FILE

ADD ${JAR_FILE} app.jar

# Transferir los archivos a nginx
VOLUME /tmp

# Eliminar los archivos del directorio de nginx (/usr/share/nginx/html)
RUN rm -rf /usr/share/nginx/html/*

# Copiar la configuracion del archivo nginx.conf
COPY nginx.conf /etc/nginx/nginx.conf

# Copiar la app de angular
COPY dist/billingApp /usr/share/nginx/html

#Copiar el archivo appshell.sh a la imagen
COPY appshell.sh appshell.sh

# Exponer los puertos necesarios (80, 8080)
EXPOSE 80 8080

# Ejecutar el script .sh
ENTRYPOINT ["sh", "/appshell.sh"]