# Reglas de negocio

**Estado:** hipótesis iniciales; confirmar con el usuario piloto antes de codificarlas.

## Conceptos

- **Recurso:** elemento reservable (por ejemplo, sala o equipo), identificado dentro de una organización.
- **Reserva:** solicitud de uso de un recurso durante un intervalo de tiempo por un usuario.
- **Administrador:** mantiene recursos, disponibilidad y políticas.
- **Usuario:** consulta disponibilidad y administra sus propias reservas, sujeto a políticas.

## Reglas propuestas

1. Una reserva corresponde a un recurso y a un intervalo con inicio anterior al fin.
2. Para recursos de capacidad exclusiva, no pueden existir reservas confirmadas con intervalos superpuestos. Los extremos se consideran semiabiertos: `[inicio, fin)`, por lo que una reserva puede iniciar cuando termina la anterior.
3. La validación de disponibilidad y la confirmación deben ser seguras ante solicitudes concurrentes; la interfaz no es la autoridad final.
4. Solo se puede reservar un recurso activo y dentro de su disponibilidad configurada.
5. El usuario puede consultar y cancelar sus propias reservas; el administrador puede gestionarlas todas. **Por validar:** permisos de modificación y cancelación por estado.
6. La cancelación conserva el registro e historial; no elimina físicamente la reserva.
7. El administrador puede desactivar un recurso. **Por validar:** efecto en reservas futuras ya existentes.
8. Las fechas se almacenan en UTC y se presentan en la zona horaria configurada para la organización.
9. Las operaciones que cambian estado deben ser auditables con actor y fecha/hora.

## Estados propuestos de reserva

`PENDING` (si se requiere aprobación) → `CONFIRMED` → `CANCELLED` o `COMPLETED`.

Si todas las reservas se confirman al crearse, eliminar `PENDING` del MVP. Estados, transiciones y necesidad de aprobación requieren validación con usuarios.

## Casos límite que deben acordarse

- ¿Se permite reservar con cuánta anticipación? ¿Hay duración mínima/máxima?
- ¿Se permiten reservas recurrentes o con buffers de preparación/limpieza?
- ¿Puede el usuario modificar una reserva confirmada? ¿Hasta cuándo?
- ¿Qué pasa al desactivar un recurso con reservas futuras?
- ¿Un recurso puede tener capacidad mayor que uno o reservas compartidas?
- ¿Cómo se manejan festivos, horarios por sede y zonas horarias?
- ¿Hay cuotas o límites por usuario/equipo?

## Ejemplos de aceptación

- Dos usuarios reservan simultáneamente la misma sala y periodo: como máximo una solicitud se confirma.
- Una reserva que empieza exactamente al terminar otra se acepta si no hay buffer configurado.
- Un usuario intenta cancelar la reserva de otra persona: se rechaza salvo permiso administrativo.
- Se solicita un periodo fuera del horario disponible: se rechaza con explicación clara.
