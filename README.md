# Backend Ktor App - Catálogo Musical

Este repositorio aloja la API RESTful diseñada para gestionar el catálogo de una aplicación de música. Está construida enteramente en **Kotlin** utilizando el framework **Ktor**, destacando por su rendimiento, ligereza y una estructura de código basada en *Clean Architecture*.

## Funcionalidades

La API expone endpoints para administrar las siguientes entidades:
* **Artistas (`/artistas`):** Registro y consulta de información de artistas o bandas.
* **Álbumes (`/albumes`):** Gestión de álbumes y su relación con los artistas correspondientes.
* **Tracks (`/tracks`):** Administración de las canciones/pistas individuales que pertenecen a cada álbum.

##  Arquitectura y Patrones

El proyecto promueve una alta cohesión y bajo acoplamiento dividiendo el código en capas claras:
1. **Rutas (`routes/`):** Controladores que reciben las peticiones HTTP y manejan las respuestas.
2. **Repositorios (`repositories/`):** Capa de abstracción que encapsula toda la lógica de acceso y manipulación de la base de datos.
3. **Modelos (`models/`):** Entidades de dominio que mapean directamente las tablas de la base de datos.
4. **DTOs (`dtos/`):** *Data Transfer Objects* utilizados para estructurar y validar los datos en formato JSON que entran o salen de la API, separándolos de la lógica de base de datos.

##  Tecnologías Utilizadas

* **Lenguaje Principal:** Kotlin
* **Framework Web:** Ktor Server
* **Serialización:** `kotlinx.serialization` (JSON)
* **Gestor de Dependencias:** Gradle (Kotlin DSL)
* **Seguridad:** Módulo de autenticación/seguridad integrado mediante los plugins de Ktor.

##  Estructura del Código Source (`src/main/kotlin/`)

```text
├── dtos/             # Objetos de transferencia de datos (JSON)
├── models/           # Clases de dominio (Entidades de BD)
├── plugins/          # Configuración modular de Ktor (CORS, Base de Datos, Rutas, etc.)
├── repositories/     # Lógica de acceso a datos
├── routes/           # Definición de los Endpoints REST
└── Application.kt    # Clase principal / Punto de entrada
