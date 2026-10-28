# kanban-backend-base (proyecto para completar)

Esqueleto limpio con **arquitectura MVC en capas**. Ya trae `pom.xml`, `application.yml`, las migraciones
de Flyway (tabla y datos de ejemplo) y la clase `KanbanApplication`.
Cada paquete tiene un `package-info.java` que indica qué crear (los `TODO`).

Sigue la guía `docs/GUIA-COMPLETA-PASO-A-PASO.md` del material de la clase 03
y compara con el proyecto terminado `kanban-backend`.

```
cl.ipss.kanban
├── enums         <- paso 2   (levantar y verificar)
├── entity        <- paso 2   (Model)
├── repository    <- paso 2
├── dto           <- paso 3   (levantar y verificar)
├── exception     <- paso 3
├── mapper        <- paso 4
├── service       <- paso 4   (interface)  /  service.impl <- paso 4 (levantar y verificar)
├── config        <- paso 5   (Swagger + CORS; levantar y ver Swagger)
└── controller    <- paso 6   (Controller; levantar y probar en Swagger)
```

## Base de datos (una sola vez)

Ejecuta [`crear-bd.sql`](crear-bd.sql) como superusuario `postgres`:

```powershell
psql -U postgres -h localhost -p 5432 -f crear-bd.sql
```

## Ejecutar

Se necesita Java 21 (`JAVA_HOME` apuntando a un JDK 21).

```powershell
.\mvnw.cmd spring-boot:run
```

Variables: `DB_HOST`, `DB_PORT`, `DB_NAME`, `DB_USER`, `DB_PASSWORD`, `SERVER_PORT` (8083 por defecto), `CORS_ORIGINS`, `LOG_LEVEL_APP`.
Swagger: http://localhost:8083/swagger-ui.html (vacío hasta que completes el paso 6).
