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

Tecnologías

https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white
https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white
https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white
Conceptos aplicados

    Docker Compose

    Redes personalizadas (bridge)

    Volúmenes persistentes

    Variables de entorno

    Dependencia entre servicios (depends_on)

Autor

Cristian Robledo Macleood — LinkedIn | Portfolio
