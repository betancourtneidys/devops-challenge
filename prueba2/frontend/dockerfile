# Etapa de build
FROM node:18-alpine as build

WORKDIR /app

COPY frontend/package*.json ./
RUN npm install

COPY frontend .

RUN npm run build

# Etapa final (Nginx para servir el frontend)
FROM nginx:alpine

COPY --from=build /app/build /usr/share/nginx/html

EXPOSE 80
