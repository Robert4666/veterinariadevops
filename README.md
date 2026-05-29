# Tienda de Alimentos para Perritos 🐶

Aplicación de ejemplo en 3 capas usando Docker y Docker Compose:

- Frontend: HTML + JavaScript (Nginx)
- Backend: Node.js + Express
- Base de datos: MySQL

## CI/CD

El repositorio incluye workflows separados para:

- Frontend
- Backend
- Base de datos

La idea es construir la imagen de cada componente, publicarla en Amazon ECR y desplegarla en EC2 mediante AWS Systems Manager.

## Requisitos

- Docker Desktop instalado

## Estructura del proyecto

```text
.
├── docker-compose.yml
├── frontend
│   ├── Dockerfile
│   ├── index.html
│   └── app.js
├── backend
│   ├── Dockerfile
│   ├── package.json
│   └── server.js
└── db
    └── init.sql
```

## Cómo ejecutar

1. Abrir una terminal en la carpeta del proyecto
2. Ejecutar:

```bash
docker compose build
docker compose up -d
```

3. Abrir en el navegador:

- Frontend: http://localhost:8080
- Backend (API): http://localhost:3001/api/productos

4. Para detener los contenedores:

```bash
docker compose down
```

## Notas

- La base de datos se inicializa automáticamente con el script `db/init.sql` en el primer arranque.
- Puedes modificar el frontend y backend, reconstruir y volver a levantar los contenedores.
- Los Dockerfiles usan una estructura multi-stage o separada por etapas para mejorar limpieza y seguridad.
