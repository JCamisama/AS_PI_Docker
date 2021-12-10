FROM node:14-slim as build

ARG ANGULAR_ENV
ARG ANGULAR_PATH

# Directorio base
WORKDIR /app

# Añadiendo `/app/node_modules/.bin` a $PATH
ENV PATH /app/node_modules/.bin:$PATH

# Instalando las dependencias de la app
COPY package.json /app/package.json
RUN npm install
RUN npm install -g @angular/cli@latest

# Copiando los contenidos de app
COPY . /app

# Generanco el build de la aplicación
RUN npm run build


### Despliegue en producción ###

# Imagen base del servidor
FROM nginx:1.16.0-alpine

# Copiando el artefacto construido
COPY --from=build /app/dist/frontend-couchdb /usr/share/nginx/html

# Exponiendo el puerto 80 relacionado a HTTP
EXPOSE 80

# Comando de arranque del servidor
CMD ["nginx", "-g", "daemon off;"]