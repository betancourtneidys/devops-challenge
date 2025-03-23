# 🐳 Despliegue de una aplicación Django + React (Docker Compose)

Este proyecto contiene una aplicación web fullstack compuesta por un backend en **Django** y un frontend en **React.js**, desplegada usando **Docker** y **Docker Compose**.

## 💻 Despliegue en entorno local

1. Clonar el repositorio e ir a la carpeta `prueba2`:

```bash
git clone https://github.com/betancourtneidys/devops-challenge.git
cd devops-challenge/prueba2
```

2 - Usar el archivo .env.example como base para crear tu archivo .env:

```bash
cp .env.example .env
```

3 - Construir y levantar los contenedores:

```bash
docker-compose up --build
```

4 - Acceder a la aplicación:

Frontend: http://localhost:3000

Backend/API: http://localhost:8000

## ☁️ Despliegue en AWS (EC2)

1 - Lanzar una instancia EC2 (Ubuntu 22.04 LTS recomendado)

2 - Instalar Docker y Docker Compose:

```bash
sudo apt update
sudo apt install docker.io docker-compose -y
sudo usermod -aG docker $USER
```
⚠️ Cierra sesión y vuelve a entrar después de modificar los grupos para que surta efecto.

3 - Subir el código al servidor (por scp, git clone, etc.)

4 - Crear el archivo .env como en los pasos anteriores:

```bash
cp .env.example .env
```

5 - Levantar los contenedores:

```bash
cd prueba2
docker-compose up --build -d
```

6 - Abrir puertos 3000 y 8000 en el Security Group de la EC2.

## 🧠 Justificación Técnica

**Docker Compose** permite definir y orquestar múltiples servicios de forma sencilla.

**React + Django** están separados en sus respectivos contenedores para facilitar el mantenimiento, despliegue independiente y escalabilidad.

**PostgreSQL** corre en un contenedor separado, siguiendo buenas prácticas de aislamiento.

**El script de entrypoint** personalizado en Django automatiza pasos como las migraciones y carga de datos iniciales.

Ideal tanto para desarrollo local como despliegue en servidores cloud.