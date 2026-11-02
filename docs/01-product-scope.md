# Alcance y requisitos del MVP

**Estado:** borrador para validar con usuarios potenciales.  
**Producto:** plataforma de reservas de recursos compartidos para organizaciones.  
**Nombre del repositorio:** `resource-booking-microservices` (propuesto).

## Problema

Organizaciones coordinan salas, equipos u otros recursos por correo, chat o calendarios dispersos. Esto puede causar conflictos de horario, trabajo administrativo y baja visibilidad de la utilización. Hay que confirmar que este problema existe para el primer segmento elegido.

## Usuario inicial

**Por validar antes de desarrollar:** seleccionar una organización o segmento inicial (por ejemplo, empresa pequeña/mediana, coworking o institución educativa), quién administra los recursos y quién los reserva. Evitar diseñar para todos los sectores a la vez.

## Propuesta de valor

Permitir que una organización publique recursos y reglas, consulte disponibilidad y gestione reservas desde un lugar central, evitando asignaciones incompatibles y haciendo visible el uso de los recursos.

## MVP propuesto

- Autenticación y roles básicos: administrador y usuario.
- Alta, consulta, edición y desactivación de recursos reservables.
- Definición de disponibilidad y reglas de reserva.
- Consulta de disponibilidad por recurso y periodo.
- Creación, consulta, modificación y cancelación de reservas según permisos y reglas.
- Prevención de reservas incompatibles, incluso ante solicitudes concurrentes.
- Historial básico y vista administrativa de reservas.
- Ejecución local reproducible con Docker Compose y documentación de uso.

## Fuera del MVP

- Cobro o facturación.
- Integraciones con Google/Microsoft Calendar, SSO corporativo o sistemas de RR. HH.
- Aplicaciones móviles nativas.
- Optimización automática de asignaciones, analítica avanzada y multiempresa autoservicio.
- Alta disponibilidad productiva o despliegue cloud antes de validar el primer caso de uso.

## Criterios de éxito iniciales

Acordar métricas con el primer usuario piloto. Hipótesis a validar: reducir el tiempo para coordinar una reserva, eliminar reservas duplicadas y facilitar que un administrador vea ocupación y cancelaciones. No se fijan metas numéricas hasta tener una línea base.

## Preguntas abiertas

1. ¿Qué organización o equipo será el primer usuario piloto?
2. ¿Qué recursos generan hoy más conflictos y con qué frecuencia?
3. ¿Qué reglas de horario, duración, anticipación y cancelación ya existen?
4. ¿Quién puede aprobar, bloquear o cancelar reservas?
5. ¿Qué datos personales se necesitan realmente?
