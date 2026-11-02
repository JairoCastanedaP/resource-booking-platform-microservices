# Lineamientos tecnológicos

**Estado:** propuesta inicial basada en los recursos del curso; validar versiones y decisiones al iniciar el desarrollo. No es una especificación cerrada.

## Stack base propuesto

- Java 21 y Spring Boot 4.x, siguiendo las versiones compatibles usadas en el curso.
- Maven Wrapper para builds reproducibles.
- Spring MVC para APIs REST; Spring Data JPA y Flyway para persistencia.
- PostgreSQL en el entorno integrado con Docker Compose; H2 solo si facilita pruebas/desarrollo local y sin asumir equivalencia total con PostgreSQL.
- Bean Validation y respuestas de error consistentes basadas en Problem Details.
- Spring Security y JWT para autenticación/autorización.
- Docker y Docker Compose para desarrollo local.

Las versiones exactas se fijarán en el repositorio y se revisarán por compatibilidad antes de actualizar.

## Principios de implementación

- Mantener DTOs como contratos API; no exponer entidades JPA directamente.
- Validar entradas en los bordes y reglas de negocio en la capa de aplicación/dominio.
- Versionar cambios de esquema con migraciones Flyway.
- Cada servicio es dueño de sus datos; evitar leer o escribir directamente en la base de otro servicio.
- Definir timeouts explícitos para llamadas remotas. Reintentar solo operaciones seguras/idempotentes.
- Proteger endpoints por rol y por propiedad del recurso, no solo por rol general.
- No guardar secretos reales en Git. Usar variables locales ignoradas y documentar nombres de variables sin valores sensibles.
- Registrar logs útiles sin contraseñas, tokens ni datos personales innecesarios.
- Mantener pruebas para reglas críticas, particularmente solapamiento/concurrencia, permisos y transiciones de estado.

## Calidad y estilo

- Código organizado por capacidad y responsabilidad; evitar abstracciones prematuras.
- Nombres, commits y documentación del repositorio en inglés para mantener consistencia técnica; documentación de planeación puede permanecer en español mientras el equipo lo prefiera.
- Todo endpoint debe incluir ejemplos de solicitud/respuesta, errores y requisitos de autorización.
- Toda funcionalidad se considera lista cuando tiene criterios de aceptación cubiertos, migración si aplica y documentación actualizada.

## Uso de microservicios

Practicar límites de servicio y propiedad de datos, pero no dividir cada entidad en un servicio. Confirmar primero límites de negocio y necesidades de despliegue. Mantener comunicación síncrona simple en el MVP; introducir mensajería solo si un flujo asíncrono resuelve una necesidad concreta y el equipo puede operarla.

## Pendiente de decidir

Versiones exactas de Spring, estrategia de autenticación para el piloto, necesidad de API Gateway/Service Discovery, estrategia técnica de exclusión de reservas solapadas, logging/métricas y destino de despliegue.
