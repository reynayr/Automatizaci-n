# Usar node 18.17.1-alpine
FROM node:18.17.1-alpine

# Crear volumen /usr/src/app
VOLUME /usr/src/app

# Copiar package.json y package-lock.json
COPY package*.json .

# Ejecutar npm install
RUN npm install

# Copiar el contenido al contenedor
COPY . .

# Exponer el puerto 3000
EXPOSE 3000

# Ejecutar CMD ["node", "index.js"]
CMD ["node", "index.js"]