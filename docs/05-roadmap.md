# Roadmap de implementación

Roadmap por entregables demostrables. Las fases son propuestas y deben ajustarse tras validar el primer usuario piloto. No asumir despliegue productivo hasta completar seguridad, respaldo y operación.

| Fase | Objetivo | Entregable / salida |
|---|---|---|
| 0. Validación | Entrevistar usuarios y elegir segmento, recursos iniciales y flujo actual. | Problema confirmado, usuario piloto y reglas prioritarias documentadas. |
| 1. Definición MVP | Cerrar historias, roles, estados, políticas y criterios de aceptación. | Alcance aprobado y backlog priorizado. |
| 2. Diseño técnico | Confirmar límites de servicios, datos, auth, concurrencia y ejecución local. | Diagramas y decisiones registradas; esqueleto de proyecto. |
| 3. Recursos | Gestionar recursos, sedes/horarios necesarios y permisos administrativos. | API documentada y persistencia/migraciones. |
| 4. Reservas | Consultar disponibilidad, crear y cancelar reservas; evitar solapamientos en concurrencia. | Flujo funcional cubierto por pruebas de reglas y concurrencia. |
| 5. Seguridad y experiencia | Login/roles, autorización por propiedad y mensajes de validación claros. | Recorridos de usuario y administrador demostrables. |
| 6. Calidad de integración | Ejecutar flujo completo, fallos controlados, pruebas API e integración. | Versión candidata con evidencia de aceptación. |
| 7. Piloto | Desplegar en entorno controlado con backups, monitoreo básico y guía de soporte. | Prueba con usuarios y registro de problemas/uso real. |
| 8. Evolución | Priorizar según feedback: calendario, notificaciones, recurrencias, reportes o multi-sede. | Incrementos con valor medido, no por anticipación. |

## Definition of Done inicial

- Criterios de aceptación satisfechos.
- Pruebas para reglas críticas y permisos.
- Migraciones probadas desde una base vacía.
- Errores/API documentados.
- Sin secretos en el repositorio.
- Arranque y uso documentados y repetibles.

## Dependencias que bloquean el compromiso de fechas

La fase 0 debe identificar al usuario piloto y políticas reales. No estimar integración con calendarios, SSO o despliegue cloud hasta conocer sus sistemas y requisitos.
