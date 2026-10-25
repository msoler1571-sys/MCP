---
name: revision-semanal
description: Revisión comercial semanal de Two Bites (lunes por la mañana). Úsalo cuando Marc pida la revisión de la semana, el estado de los leads, "qué tengo pendiente", "a quién tengo que escribir" o "cómo va el pipeline".
---

# Revisión semanal (lunes, 30 min)

Sigue la pauta del Plan de Escalado: lunes, máximo 3 prioridades; la venta pasa en el bloque del lunes de 9 a 11 h.

## Pasos

1. **Leer el estado:** sección "Leads activos" de `CLAUDE.md`. Si están conectados: Gmail (hilos de los últimos 7 días con clientes y leads) y Calendar (esta semana).
2. **Tabla de leads**, ordenada por valor esperado:

| Lead | Segmento | Fase | Último contacto | Siguiente paso | Fecha | Margen estimado/mes |
|---|---|---|---|---|---|---|

3. **Alertas:**
   - Leads sin siguiente paso con fecha.
   - Leads sin contacto desde hace más de 7 días.
   - Degustaciones pendientes de fijar día.
   - Propuestas por debajo del suelo de margen (ver la skill `lead-a-cliente`).
   - Capacidad: pedidos que coinciden en la misma franja (sobre todo el viernes por la tarde).
4. **Borradores:** para cada alerta, un mensaje listo siguiendo las reglas de la skill `lead-a-cliente`. En Gmail, solo como borrador; nunca se envía.
5. **Números del mes** frente al Plan de Escalado: margen bruto acumulado frente al objetivo del mes, clientes B2B recurrentes (gate: 5 o más), degustaciones hechas. Si el diario de ventas no está al día, dilo y pide a Marc los datos de la semana.
6. **Tres prioridades de la semana**, ordenadas por impacto financiero y esfuerzo.

## Formato

Sin introducción. Tabla de leads → alertas → borradores → números → 3 prioridades. Al final, actualiza `CLAUDE.md` con lo que haya cambiado y haz commit ("Memoria: revisión semanal dd/mm").
