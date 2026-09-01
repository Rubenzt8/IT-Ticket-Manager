# 🎫 IT Ticket Manager

> API REST para la gestión de incidencias tecnológicas desarrollada con Java y Spring Boot.

🚧 **Estado del proyecto: En desarrollo**

---

## 📌 Descripción

**IT Ticket Manager** es una aplicación backend orientada a la gestión de incidencias tecnológicas.

El proyecto permitirá registrar, consultar y gestionar tickets relacionados con problemas IT, clasificándolos por categoría, prioridad y estado, además de permitir su seguimiento mediante comentarios.

Ejemplo de flujo de una incidencia:

```text
OPEN → IN_PROGRESS → RESOLVED
```

Este proyecto nace como una evolución de mi TFG de DAM, **TaskMaster Flow**, pasando de una aplicación de escritorio desarrollada con JavaFX y JDBC a una arquitectura backend orientada a servicios REST.

El objetivo principal es seguir profundizando en el ecosistema Java y aprender Spring Boot mediante el desarrollo de un proyecto completo y progresivo.

---

## 🎯 Objetivos

Con este proyecto quiero trabajar de forma práctica conceptos como:

- Desarrollo de APIs REST con Spring Boot.
- Arquitectura por capas.
- Persistencia con Spring Data JPA e Hibernate.
- Diseño y uso de DTOs.
- Validación de datos.
- Gestión global de excepciones.
- Testing automatizado.
- Autenticación y autorización.
- Contenerización con Docker.
- Documentación de APIs.

La idea no es únicamente utilizar estas tecnologías, sino comprender el papel que desempeña cada una dentro de una aplicación backend.

---

## 🛠️ Stack tecnológico

### Base del proyecto

- **Java 21**
- **Spring Boot**
- **Spring Web**
- **Spring Data JPA**
- **PostgreSQL**
- **Maven**

### Tecnologías que se incorporarán durante el desarrollo

- **Bean Validation**
- **JUnit**
- **Mockito**
- **Spring Security**
- **JWT**
- **Docker**
- **Docker Compose**
- **Swagger / OpenAPI**

---

## 🧱 Arquitectura

El proyecto seguirá una arquitectura por capas sencilla:

```text
HTTP Request
     │
     ▼
Controller
     │
     ▼
Service
     │
     ▼
Repository
     │
     ▼
PostgreSQL
```

Estructura prevista:

```text
src/main/java/...
│
├── controller/
├── service/
├── repository/
├── entity/
├── dto/
├── exception/
├── security/
└── config/
```

### Responsabilidades

**Controller**
- Gestión de peticiones HTTP.
- Recepción y devolución de DTOs.
- Validaciones de entrada.
- Códigos de estado HTTP.

**Service**
- Lógica de negocio.
- Validaciones de negocio.
- Coordinación entre repositorios.
- Conversión entre entidades y DTOs.

**Repository**
- Acceso y persistencia de datos mediante Spring Data JPA.

---

## ⚙️ Funcionalidades previstas

### 👤 Usuarios

- Registro de usuarios.
- Inicio de sesión.
- Roles `USER` y `ADMIN`.
- Autenticación mediante JWT.

### 🎫 Tickets

- Crear incidencias.
- Consultar incidencias.
- Actualizar incidencias.
- Clasificar por prioridad.
- Modificar su estado.
- Filtrar tickets.
- Cierre lógico de incidencias.

Estados previstos:

```text
OPEN
IN_PROGRESS
RESOLVED
CLOSED
```

Prioridades:

```text
LOW
MEDIUM
HIGH
```

### 💬 Comentarios

Los usuarios podrán añadir comentarios a los tickets para realizar un seguimiento de la incidencia.

### 📊 Estadísticas

Está prevista la incorporación de un endpoint de estadísticas para practicar consultas agregadas y DTOs de respuesta personalizados.

---

## 🔗 Endpoints previstos

### Autenticación

```http
POST /api/auth/register
POST /api/auth/login
```

### Tickets

```http
GET    /api/tickets
GET    /api/tickets/{id}
POST   /api/tickets
PUT    /api/tickets/{id}
DELETE /api/tickets/{id}
```

### Filtros

```http
GET /api/tickets?status=OPEN
GET /api/tickets?priority=HIGH
```

### Estadísticas

```http
GET /api/tickets/stats
```

---

## 🗃️ Modelo de datos

Modelo inicial:

```text
User 1 -------- N Ticket
User 1 -------- N Comment
Ticket N ------ 1 Category
Ticket 1 ------ N Comment
```

Entidades principales:

- `User`
- `Ticket`
- `Category`
- `Comment`

---

## 🗺️ Roadmap

### ✅ Fase 1 — Base del proyecto

- [ ] Crear proyecto Spring Boot.
- [ ] Configurar PostgreSQL.
- [ ] Crear entidades.
- [ ] Crear repositorios.
- [ ] Configurar persistencia con JPA.

### 🌐 Fase 2 — API REST

- [ ] Implementar CRUD de tickets.
- [ ] Crear capa Service.
- [ ] Implementar DTOs.
- [ ] Separar responsabilidades entre capas.

### 🧪 Fase 3 — Validación y testing

- [ ] Bean Validation.
- [ ] Gestión global de excepciones.
- [ ] Tests con JUnit.
- [ ] Tests de servicios con Mockito.

### 🔐 Fase 4 — Seguridad

- [ ] Spring Security.
- [ ] BCrypt.
- [ ] JWT.
- [ ] Roles `USER` y `ADMIN`.
- [ ] Autorización de endpoints.

### 🐳 Fase 5 — Docker

- [ ] Crear Dockerfile.
- [ ] Dockerizar la aplicación.
- [ ] Dockerizar PostgreSQL.
- [ ] Configurar Docker Compose.
- [ ] Configurar volúmenes.
- [ ] Configurar variables de entorno.

### 📚 Fase 6 — Documentación

- [ ] Swagger / OpenAPI.
- [ ] Documentar endpoints.
- [ ] Añadir instrucciones de instalación.
- [ ] Completar documentación técnica.

---

## 🚀 Ejecución

Las instrucciones para ejecutar el proyecto se añadirán a medida que se complete la configuración inicial.

---

## 📚 Contexto

Este proyecto forma parte de mi proceso de aprendizaje y evolución hacia el desarrollo backend con Java.

Después de desarrollar **TaskMaster Flow** como TFG de DAM utilizando Java, JavaFX, JDBC y MySQL, el objetivo ahora es dar el salto hacia una arquitectura web moderna utilizando Spring Boot, APIs REST, JPA, PostgreSQL y Docker.

---

## 👨‍💻 Autor

**Ruben Flores**

GitHub: [Rubenzt8](https://github.com/Rubenzt8)
