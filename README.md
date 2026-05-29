# Docker Compose App 🐳

Aplicación multi-contenedor con Nginx y MySQL usando Docker Compose,
diseñada para demostrar orquestación de servicios en entornos reales.

## Servicios incluidos

### 🌐 Web Server — Nginx
Servidor web que sirve contenido HTML estático con volumen montado.
Puerto expuesto: `8080:80` para acceso desde el host.

### 🗄️ Base de Datos — MySQL 8.0
Base de datos relacional con volumen persistente y red interna aislada.
Variables de entorno configuradas desde archivo `.env`.

## Estructura del proyecto
docker-compose-app/
├── docker-compose.yml
├── .env              (no incluido — ver Variables de entorno)
├── .gitignore
├── app/
│   └── index.html
└── README.md
## Variables de entorno

Crear archivo `.env` en la raíz del proyecto:

```env
DB_ROOT_PASSWORD=rootpass
DB_NAME=miapp
DB_USER=appuser
DB_PASSWORD=apppass
```

## Cómo ejecutar

```bash
# Levantar todos los servicios
docker-compose up -d

# Ver estado de los contenedores
docker-compose ps

# Ver logs en tiempo real
docker-compose logs -f

# Detener y eliminar contenedores
docker-compose down
```

## Acceso

- **Web:** http://localhost:8080
- **MySQL interno:** `base-datos:3306`

## Conceptos aplicados

- **Docker Compose** — orquestación multi-contenedor en un solo archivo YAML
- **Redes personalizadas** — bridge para aislamiento entre servicios
- **Volúmenes persistentes** — datos que sobreviven al reinicio del contenedor
- **Variables de entorno** — configuración flexible sin hardcoding
- **depends_on** — orden de inicio entre servicios

## Uso en el mundo laboral

Este proyecto replica el flujo típico de una aplicación web con base de datos
en desarrollo local. Docker Compose es el estándar en equipos DevOps para
entornos de prueba, integración continua y desarrollo colaborativo.

## Tecnologías

![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat&logo=docker&logoColor=white)
![Nginx](https://img.shields.io/badge/Nginx-009639?style=flat&logo=nginx&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-4479A1?style=flat&logo=mysql&logoColor=white)
![YAML](https://img.shields.io/badge/YAML-CB171E?style=flat&logo=yaml&logoColor=white)

## Autor
Cristian Robledo Macleood — [LinkedIn](https://www.linkedin.com/in/cristian-robledo-macleood-7538331b5/) | [Portfolio](https://10101985.github.io/web-portfolio-personal)
