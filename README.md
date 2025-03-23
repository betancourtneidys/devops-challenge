
## ✅ Pruebas realizadas

### ☁️ **Prueba 1 - Diagrama de red distribuido en AWS**

Se diseñó una arquitectura distribuida y escalable que cumple con los requisitos de:
- Alta disponibilidad (HA)
- Soporte para cargas variables
- Frontend en JS, backend con base de datos relacional y no relacional
- Consumo de microservicios externos

Incluye:
- Imagen del diagrama de arquitectura
- Explicación detallada en `README.md` y PDF

📁 [Ver carpeta `prueba1`](./prueba1)

### 🐳 **Prueba 2 - Despliegue de una aplicación Django y React.js**

Se dockerizó una aplicación fullstack con Django como backend y React como frontend, orquestada con **Docker Compose**.

Incluye:
- `.env.example`
- Script `entrypoint.sh` para automatizar migraciones
- Instrucciones detalladas para despliegue local y en AWS (EC2)

📁 [Ver carpeta `prueba2`](./prueba2)

### 🔄 **Prueba 3 - CI/CD con Docker y GitHub Actions**

Se construyó una solución CI/CD completa para una app estática con **Nginx**, utilizando **GitHub Actions** para:

- Detectar cambios en `index.html`
- Construir y publicar automáticamente una nueva imagen Docker
- Subirla a Docker Hub

Incluye:
- `Dockerfile` optimizado
- Pipeline de GitHub Actions (`.github/workflows/main.yml` en la raíz del repositorio)
- Documentación de uso y requisitos

📁 [Ver carpeta `prueba3`](./prueba3)

## 👩‍💻 Autor

**Neidys Betancourt**  
[GitHub](https://github.com/betancourtneidys)
