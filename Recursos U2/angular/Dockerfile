FROM nginx:stable-alpine

 # use a volume is mor efficient and speed that filesystem
VOLUME /tmp

#Install web app on nginx server
RUN rm -rf /usr/share/nginx/html/*

COPY nginx.conf /etc/nginx/nginx.conf

COPY mime.types /etc/nginx/mime.types

COPY sistema-ventas-front /usr/share/nginx/html

#The ports 7080 for backend-app and 80 for web app
EXPOSE 80

#Ejecutar el comando: CMD[“nginx”, “-g”, “daemon off;”]
CMD [ "nginx", "-g", "daemon off;" ]