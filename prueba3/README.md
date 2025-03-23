# 🚀 CI/CD con Docker y GitHub Actions

Este proyecto consiste en una página web estática servida con **Nginx**, contenida en una imagen Docker. Se implementa un flujo de integración y despliegue continuo (**CI/CD**) utilizando **GitHub Actions**, de manera que cada vez que se modifica el archivo `index.html`, se construye una nueva imagen y se publica automáticamente en **Docker Hub**.

## ⚙️ ¿Cómo funciona?

1 - Cada vez que se modifica el archivo `index.html` (ubicado en `sitio/`), se activa el pipeline de GitHub Actions.

2 - El pipeline realiza las siguientes acciones:
   - Hace checkout del código
   - Inicia sesión en Docker Hub
   - Construye una nueva imagen Docker con el archivo actualizado
   - Publica la imagen como `neidys/prueba3:latest` *(puede cambiar según el usuario)*

3 - Esta imagen puede ser desplegada en cualquier entorno con **Docker**, **Kubernetes**, **ECS**, etc.

## 🐳 Dockerfile

```Dockerfile
FROM nginx:alpine
COPY sitio/index.html /usr/share/nginx/html/index.html
```

## 🔄 CI/CD - GitHub Actions

El archivo `.github/workflows/main.yml` define el pipeline. Actualmente, se activa al hacer algun cambio en el index.html:

```main.yml
on:
  push:
    paths:
      - 'prueba3/sitio/index.html'
```

## 🛠️ Requisitos previos

Para que el pipeline funcione correctamente, se deben definir los siguientes secrets en la configuración del repositorio en GitHub:

`DOCKERHUB_USERNAME` → tu nombre de usuario de Docker Hub

`DOCKERHUB_TOKEN` → tu token de acceso (desde Docker Hub > Security)
