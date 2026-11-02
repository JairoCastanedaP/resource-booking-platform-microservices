# Registro de decisiones de arquitectura (ADR)

Guardar aquí decisiones que afectan el producto o la arquitectura. Una decisión registra contexto, opciones, elección, consecuencias y estado; no es una lista de tareas.

## Plantilla

Copiar para cada decisión como `NNNN-titulo-corto.md`:

```markdown
# ADR-NNNN: Título

- Estado: Propuesta | Aceptada | Reemplazada
- Fecha: YYYY-MM-DD

## Contexto
¿Qué problema o restricción requiere una decisión?

## Opciones consideradas
- Opción A
- Opción B

## Decisión
¿Qué se elige y por qué?

## Consecuencias
¿Qué ventajas, costos y tareas derivan?
```

## Primeras decisiones por registrar

- Límite inicial de servicios y propiedad de datos.
- Cómo se previenen reservas solapadas bajo concurrencia.
- Identidad y autorización para el primer piloto.
- Si y cuándo introducir API Gateway, Service Discovery o mensajería.
