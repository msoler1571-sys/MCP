---
name: lead-a-cliente
description: Llevar un lead de Two Bites hasta el primer pedido y la recurrencia. Úsalo cuando Marc diga que le ha contactado un local, oficina, cafetería o distribuidor; que ha dado una caja de degustación; que un lead "ha dicho que sí", no contesta o pide descuento; o cuando pregunte cómo cerrar, cómo hacer el seguimiento o qué presupuesto enviar.
---

# Lead → cliente

Objetivo: que ningún lead se enfríe. Cada lead sale de esta skill con **un siguiente paso con fecha**, un mensaje listo para enviar y el margen comprobado.

## 1. Situar el lead

1. Busca el lead en `CLAUDE.md` (sección "Leads activos"). Si hay Gmail conectado, lee el hilo más reciente.
2. Clasifícalo:

| Segmento | Producto | Precio de referencia (sin IVA) |
|---|---|---|
| Oficina / empresa | Pedido entregado recién horneado | Clásica 2,80 €, premium 3,40 €, alfajor mini 1,30 € |
| Evento en oficina | Córner con horno | 14 €/persona afterwork, 12 € cóctel; mínimo 40 personas |
| HORECA / cafetería / local | Congelado o cocinado en cajas | Tarifa HORECA de `CLAUDE.md` |
| Distribuidor | Congelado, cajas de un sabor | Como ByKoko |
| Colectividad (Serunion, Aramark) | Alta de proveedor + HORECA | Tarifa HORECA |

3. Fase actual: contacto → degustación → feedback → propuesta → primer pedido → recurrente (4º pedido).

## 2. Comprobar el margen antes de proponer nada

- Costes Tío Bigotes: clásica 1,13 € congelada / 1,25 € cocinada; premium 1,30 € / 1,40 €; copetín 0,55 € / 0,65 €; alfajor mini 0,50 €, pistacho 0,65 €, grande 1,20 €. Cajas de 30 uds (copetín 40).
- Logística: unos 5,04 € por pedido en BCN. Fuera de BCN, calcula el desplazamiento aparte.
- **Avisa a Marc** si la propuesta deja menos de ~0,30 €/ud en HORECA o menos del 50 % en pedido entregado. Suelo propuesto (pendiente de que Marc lo confirme): clásica 1,45 € congelada / 1,60 € cocinada; premium 1,75 € / 1,85 €.
- Calcula siempre qué pasa si piden un 10 % de descuento. Si eso deja el margen cerca de cero, el descuento no se ofrece: se regalan alfajores.

## 3. Reglas de cierre

- **Un "sí" verbal se cierra en 24 h.** El mismo día: llamada o audio de WhatsApp. En menos de 24 h: propuesta escrita. En el mismo mensaje: dos fechas concretas para cerrar ("martes 17:30 o miércoles 10:00"), nunca "cuándo te va bien".
- **Pide un compromiso pequeño, no un contrato:** fecha del primer pedido, cantidades y sabores orientativos. Para locales que abren: "pedido de inauguración" con fecha.
- **La urgencia tiene que ser real.** Sirven: planificar producción con el fabricante, reservar el día de apertura, fijar los precios hasta una fecha. No se usan excusas inventadas ("estoy súper liado").
- **Propuesta con 2–3 opciones cerradas** (por ejemplo: pedido de apertura, pedido semanal, mes prepagado −5 %). Que el cliente elija, no que diseñe.
- **Condiciones de Marc:** sin penalizaciones ni plazos de pago impuestos; factura por pedido o mensual; sin permanencia; descuento máximo del 10 % o alfajores de regalo; sin chimichurri en los pedidos entregados.
- **Si piden descuento:** a cambio de algo (volumen, prepago, fecha fija). Primero alfajores; el 10 % es el máximo absoluto.

## 4. Seguimiento si no contestan

| Día | Acción |
|---|---|
| 0 | Propuesta + dos fechas |
| 3 | Audio o llamada corta: "¿Pudiste verla? ¿Te va bien el martes o el miércoles?" |
| 7 | Pregunta de sí o no: "¿Hacemos el primer pedido el [fecha] o lo dejamos para más adelante?" |
| 14 | Cierre amable: "Te dejo tranquila; si en algún momento os encaja, aquí estoy." Pasa a contacto mensual |

Nunca más de 3 seguimientos sin respuesta.

## 5. Qué entregar a Marc

1. **Diagnóstico** (2–3 líneas): segmento, fase, riesgo principal.
2. **Margen** de la propuesta (tabla corta), con aviso si queda por debajo del suelo.
3. **Mensaje listo para enviar**, en el canal que toque (WhatsApp y/o mail), con el tono de Marc: cercano, directo, sin presión.
4. **Propuesta**: si hace falta presupuesto formal, usa la plantilla de Drive (Presupuesto_Fundacio_Eina.docx) y el siguiente número de `CLAUDE.md`. Ninguna sección partida entre páginas; ejemplos de sabores variados al final, como orientativos.
5. **Siguiente paso con fecha** y, si hay Calendar conectado, propón crear el recordatorio.

Los mails se dejan como **borrador**; nunca se envían sin el visto bueno de Marc.

## 6. Cerrar el ciclo

Actualiza la línea del lead en `CLAUDE.md` (fase, último contacto, siguiente paso y fecha) y, si es un presupuesto nuevo, el último número usado. Haz commit con el mensaje "Memoria: <lead> — <cambio>".
