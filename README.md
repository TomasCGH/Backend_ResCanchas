# ResCanchas Backend

API REST para la gestión y reserva de canchas deportivas. Este repositorio corresponde a la capa de backend del proyecto ResCanchas, desarrollada en Java con Spring Boot para gestionar clientes, encargados, canchas, reservas, horarios, facturación y demás procesos del negocio.

## Descripción general

ResCanchas es un sistema pensado para facilitar la administración de instalaciones deportivas, permitiendo:

- registrar y administrar canchas
- gestionar clientes y encargados
- controlar reservas y disponibilidad horaria
- mantener estados de verificación y reservas
- administrar reseñas y facturación
- ofrecer una API robusta para consumo desde un frontend web

El backend y el frontend de este proyecto funcionan de forma integrada como una solución completa para la gestión de espacios deportivos.

## Repositorio relacionado

- Frontend: https://github.com/TomasCGH/Frontend_ResCanchas

## Stack tecnológico

- Java 24
- Spring Boot 3.4.5
- Spring Web
- Spring Data JPA
- Spring JDBC
- PostgreSQL
- Maven

## Arquitectura

El proyecto está organizado por capas para mantener un diseño ordenado y escalable:

- api: controladores REST
- businesslogic: lógica de negocio
- facade: abstracción de casos de uso
- assembler: conversión entre entidades y DTOs
- data: acceso a datos y DAO
- entity: modelos de dominio
- dto: objetos de transferencia
- crosscutting: utilidades, constantes y excepciones
- config: configuración global

## Funcionalidades principales

- CRUD de canchas, clientes, encargados y organizaciones deportivas
- gestión de departamentos, municipios y ubicaciones precisas
- control de horarios disponibles y horarios especiales
- administración de reservas y estados de reserva
- validación de estados de verificación
- manejo de facturas y reseñas
- manejo centralizado de excepciones y errores

## Requisitos previos

Antes de ejecutar el proyecto asegúrate de contar con:

- JDK 24 o superior
- Maven 3.9+
- PostgreSQL
- Git

## Configuración de la base de datos

La aplicación usa PostgreSQL como base de datos principal. La configuración actual está en `src/main/resources/application.properties`:

```properties
spring.jpa.database=POSTGRESQL
spring.sql.init.platform=postgres
spring.datasource.url=jdbc:postgresql://localhost:5432/postgres
spring.datasource.username=postgres
spring.datasource.password=tu_password
spring.jpa.show-sql=true
spring.jpa.generate-ddl=true
spring.jpa.hibernate.ddl-auto=update
spring.datasource.driver-class-name=org.postgresql.Driver
server.port=8081
```

Ajusta los valores según el entorno local o la base de datos que vayas a usar.

## Ejecución

Desde la raíz del repositorio ejecuta:

```bash
./mvnw spring-boot:run
```

O con Maven:

```bash
mvn spring-boot:run
```

La API quedará disponible en:

```text
http://localhost:8081
```

## Estructura del proyecto

```text
Backend_ResCanchas/
├── src/
│   └── main/
│       ├── java/
│       │   └── co/edu/uco/backend/
│       │       ├── api/
│       │       ├── businesslogic/
│       │       ├── config/
│       │       ├── crosscutting/
│       │       ├── data/
│       │       ├── dto/
│       │       ├── entity/
│       │       └── init/
│       └── resources/
│           └── application.properties
├── .mvn/
├── .gitignore
├── pom.xml
├── mvnw
├── mvnw.cmd
├── README.md
└── ...
```

## Buenas prácticas aplicadas

- separación clara entre capas de negocio, acceso a datos y controladores
- DTOs y entidades organizados por dominio
- manejo centralizado de excepciones
- configuración preparada para entorno local y despliegue posterior
- estructura modular para facilitar mantenimiento y escalabilidad

## Estado del proyecto

Este repositorio se encuentra en desarrollo activo como parte del sistema ResCanchas. La API REST ya está preparada para integrarse con el frontend del mismo proyecto y continuar con la expansión del sistema.

## Licencia

Actualmente no se ha definido una licencia pública para este repositorio.

---

Desarrollado como parte del proyecto ResCanchas.
