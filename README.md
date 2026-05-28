# Docker Compose App 🐳

Aplicación multi-contenedor con Nginx y MySQL usando Docker Compose.  
Diseñada para demostrar orquestación básica de contenedores en entornos de desarrollo local.

## Servicios incluidos

### 🌐 Web Server (Nginx)
- Imagen: `nginx:alpine`
- Puerto expuesto: `8080:80`
- Volumen: `./app` montado en `/usr/share/nginx/html`
- Sirve contenido HTML estático

### 🗄️ Base de Datos (MySQL 8.0)
- Imagen: `mysql:8.0`
- Variables de entorno desde archivo `.env`
- Volumen persistente: `datos-mysql`
- Red interna aislada

## Estructura del proyecto

docker-compose-app/
├── docker-compose.yml
├── .env
├── .gitignore
├── app/
│ └── index.html
└── README.md

## Variables de entorno

Crear archivo `.env` con:

```env
DB_ROOT_PASSWORD=rootpass
DB_NAME=miapp
DB_USER=appuser
DB_PASSWORD=apppass

Cómo ejecutar

# Levantar los servicios
docker-compose up -d

# Ver estado
docker-compose ps

# Ver logs
docker-compose logs -f

# Detener servicios
docker-compose down

Acceso

    Web: http://localhost:8080

    MySQL interno: base-datos:3306

Conceptos aplicados

    Docker Compose — orquestación multi-contenedor

    Redes personalizadas — bridge para aislamiento

    Volúmenes persistentes — datos que sobreviven al contenedor

    Variables de entorno — configuración sin hardcoding

    Dependencia entre servicios — depends_on para orden de inicio

Uso en el mundo laboral

Este proyecto replica el flujo típico de una aplicación web con backend de base de datos en desarrollo local. Docker Compose es estándar en equipos DevOps para entornos de prueba y CI/CD.
Tecnologías

https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white
https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white
https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white
Autor

Cristian Robledo Macleood — LinkedIn | Portfolio
