# Proyecto Semestral DevOps

## Descripción General

Este proyecto corresponde a una arquitectura basada en microservicios desarrollada con tecnologías modernas orientadas a entornos DevOps.

La solución está compuesta por:

* Un frontend desarrollado en React + Vite.
* Un microservicio de Ventas desarrollado en Spring Boot.
* Un microservicio de Despachos desarrollado en Spring Boot.
* Una base de datos MariaDB.
* Orquestación mediante Docker Compose.

El objetivo principal del proyecto es demostrar la integración de múltiples servicios utilizando contenedores Docker y comunicación entre componentes dentro de una infraestructura desacoplada.

---

# Arquitectura del Proyecto

```text
┌──────────────────────┐
│      Frontend        │
│   React + Vite       │
│      Puerto 4173     │
└──────────┬───────────┘
           │
           │ HTTP
           │
 ┌─────────▼─────────┐
 │ Backend Ventas    │
 │ Spring Boot       │
 │ Puerto 8080       │
 └─────────┬─────────┘
           │
           │
 ┌─────────▼─────────┐
 │ Backend Despacho  │
 │ Spring Boot       │
 │ Puerto 8081       │
 └─────────┬─────────┘
           │
           │ JDBC
           │
 ┌─────────▼─────────┐
 │     MariaDB       │
 │     Puerto 3306   │
 └───────────────────┘
```

---

# Tecnologías Utilizadas

## Frontend

* React
* Vite
* TailwindCSS
* JavaScript

## Backend

* Java 17
* Spring Boot
* Spring Data JPA
* Maven
* Swagger / OpenAPI

## Base de Datos

* MariaDB 10.11

## DevOps

* Docker
* Docker Compose

---

# Estructura del Proyecto

```text
proyecto semestral/
│
├── front_despacho/
│   ├── src/
│   ├── public/
│   ├── package.json
│   └── Dockerfile
│
├── back-Ventas_SpringBoot/
│   └── Springboot-API-REST/
│       ├── src/
│       ├── pom.xml
│       └── dockerfile
│
├── back-Despachos_SpringBoot/
│   └── Springboot-API-REST-DESPACHO/
│       ├── src/
│       ├── pom.xml
│       └── dockerfile
│
├── docker-compose.yml
└── .env
```

---

# Servicios Disponibles

## Frontend

| Servicio       | Puerto |
| -------------- | ------ |
| Frontend React | 4173   |

## Backend

| Servicio      | Puerto |
| ------------- | ------ |
| API Ventas    | 8080   |
| API Despachos | 8081   |

## Base de Datos

| Servicio | Puerto |
| -------- | ------ |
| MariaDB  | 3306   |

---

# Ejecución del Proyecto

## Requisitos Previos

Instalar:

* Docker
* Docker Compose
* Git

Verificar instalación:

```bash
docker --version
docker compose version
```

---

# Clonar el Proyecto

```bash
git clone <URL_DEL_REPOSITORIO>
cd "proyecto semestral"
```

---

# Levantar los Servicios

Desde la raíz del proyecto:

```bash
docker compose up --build
```

Para ejecutar en segundo plano:

```bash
docker compose up -d --build
```

---

# Detener Contenedores

```bash
docker compose down
```

---

# Acceso a los Servicios

## Frontend

```text
http://localhost:4173
```

## API Ventas

```text
http://localhost:8080
```

## API Despachos

```text
http://localhost:8081
```

---

# Documentación Swagger

## Swagger Ventas

```text
http://localhost:8080/swagger-ui/index.html
```

## Swagger Despachos

```text
http://localhost:8081/swagger-ui/index.html
```

---

# Características Implementadas

## Frontend

* Interfaz web moderna.
* Componentes reutilizables.
* Formularios de gestión.
* Tablas dinámicas.
* Navegación con rutas.
* Diseño responsive.

## Backend Ventas

* CRUD de ventas.
* Arquitectura por capas.
* Manejo de excepciones.
* Persistencia con JPA.
* API REST.

## Backend Despachos

* CRUD de despachos.
* Arquitectura desacoplada.
* Servicios y repositorios.
* Manejo de errores.
* API REST.

## DevOps

* Contenedorización con Docker.
* Orquestación con Docker Compose.
* Variables de entorno.
* Separación por servicios.
* Infraestructura reproducible.

---
# CI/CD con GitHub Actions

El proyecto implementa integración y despliegue continuo utilizando GitHub Actions.

## Características

- Build automático de microservicios.
- Construcción de imágenes Docker.
- Uso de GitHub Secrets para credenciales seguras.
- Despliegue automático en AWS.
- Automatización del flujo DevOps.
- Pipeline reproducible y escalable.

## Tecnologías utilizadas

- GitHub Actions
- Docker Hub / ECR
- AWS EC2
- SSH Deployment
- Secrets Management

---
# Docker Compose

El proyecto utiliza un archivo `docker-compose.yml` para levantar automáticamente:

* Frontend React.
* Backend Ventas.
* Backend Despachos.
* Base de datos MariaDB.

Servicios definidos:

```yaml
services:
  frontend:
  backend-ventas:
  backend-despachos:
  proyecto-db:
```

---

# Posibles Mejoras Futuras

* Balanceador de carga.
* Kubernetes.
* Autenticación JWT.
* Monitoreo con Prometheus y Grafana.
* Logs centralizados.
* Testing automatizado.

---

# Pruebas

Los proyectos backend incluyen estructura de testing mediante JUnit.

Ejecutar pruebas:

```bash
./mvnw test
```

---

# Autor

Proyecto desarrollado con enfoque académico para prácticas de DevOps, contenedores y arquitectura de microservicios.

---

# Licencia

Uso académico y educativo.
