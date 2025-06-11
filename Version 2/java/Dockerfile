# Usar la imagen base con JRE 17 en alpine
FROM eclipse-temurin:17-alpine

# Crear un nuevo grupo llamado "devopsc" para el almacenamiento
RUN addgroup -g 1028 devopsc \
    && adduser -D -G devopsc admin 

# Crear la carpeta "tmp" pa el almacenamiento del cache
VOLUME /tmp

# Establecer una variable JAR_FILE para la ruta del archivo
ARG JAR_FILE

# Establecer una variable de entorno DB_PASSWORD con el valor del argumento
ARG DB_PASSWORD

# Agregar las variebles al .env
ENV DB_PASSWORD=$DB_PASSWORD

# Copiar el archivo JAR
COPY ${JAR_FILE} /tmp/app.jar

# Generar los permisos
RUN chown -R admin:devopsc /tmp

# Cambiar al usuario admin
USER admin

# Exponer el puerto 8080 (backend)
EXPOSE 8080

# Ejecutar el JAR para iniciar el contenedor
ENTRYPOINT ["java", "-jar", "/tmp/app.jar"]