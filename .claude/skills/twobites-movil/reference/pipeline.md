# Pipeline Two Bites: cómo leerlo y escribirlo

Solo si tienes una herramienta para la base de datos del artifact https://claude.ai/artifact/Ra6ovVK3zZ4srzH2WN7stN (colección `leads`). Si no la tienes, usa el bloque "Para apuntar" del SKILL.md.

El pipeline es la única fuente de verdad de lo comercial de Marc, y lo leen también los agentes programados. Un cambio mal hecho (notas pisadas, una fecha olvidada, un lead borrado) hace que vuelva a salir en "Qué toca hoy" o que el agente lo vuelva a meter.

## Leer

- Lista todos los leads (límite alto, por ejemplo 1000). El `doc_id` está en kebab-case a partir del nombre (`tuset-eventos`).
- **Lee siempre antes de escribir**: necesitas la `version` del documento (sin ella la escritura se rechaza) y las `notas` actuales.
- Qué vence: leads no `descartado` con `fechaProximo` hasta hoy + 3 días (vencidos, hoy, pronto).
- Emails de los leads `contactado` y `conversando` están en el campo `contacto`: úsalos para buscar sus respuestas en Gmail (`from:(dominio1 OR dominio2…)`; con gmail.com, hotmail.com, etc., el email completo).

## Qué cambiar según lo que haya pasado

| Lo que pasa | `estado` | `ultimoContacto` | `fechaProximo` | `proximoPaso` |
|---|---|---|---|---|
| Marc ha escrito, llamado o visitado | `contactado` | hoy | hoy + 7 | "Seguimiento si no contesta" |
| Ha respondido | `conversando` | fecha de la respuesta | hoy (o +2 si Marc ya respondió) | "Responder: <resumen en 10 palabras>" |
| Cerrado o cliente | `ganado` | hoy | lo que toque (entrega, montaje…) | el siguiente paso concreto |
| "Ahora no" o hay que esperar | `aparcado` | se deja | cuándo reabrir | "Reabrir en <mes>: <qué hacer>" |
| No interesa o no encaja | `descartado` | se deja | `""` | "Descartado el d/m por Marc: <motivo corto>" |

- Fechas en `notas` y `proximoPaso` como `d/m`; en los campos de fecha, `AAAA-MM-DD`.
- Añade **siempre** una frase a `notas` con el formato `" · [d/m] texto"`, escribiendo el campo entero: las notas viejas tal cual, más la frase nueva. **Nunca reemplaces** las notas de Marc.
- Tras dejar un borrador de seguimiento: `proximoPaso` = "Revisar y enviar el seguimiento (borrador en el hilo, d/m)".
- `ganado` con pedido recurrente: `pedidos` (número de pedidos entregados; con 4 o más es "cliente que repite") y `margenSemana` (euros, número).
- Etiquetas (`etiqueta`): `1-Urgente`, `2-Navidad` (solo fiestas de Navidad de adultos; desde el 15/11 pasan a `3-Agencias`), `3-Agencias`, `4-Cantinas`, `5-Bodas`, `Aparcar-2027` (con estado `aparcado`). HORECA y oficinas no llevan etiqueta.

## Caja de degustación (campo `degustacion`)

```
degustacion: { estado, dia, hora, direccion, contacto, que, entregada, avisoId }
```

| Pasa esto | `degustacion.estado` | Además |
|---|---|---|
| Se la ofrecemos dentro de una conversación | `ofrecida` | — |
| Dicen que sí ("mándala", "encantados", "déjala en…") | `confirmada` | `direccion`, `dia`, `hora`, `contacto` con lo que digan; lo que falte va al `proximoPaso` ("Fijar día para la caja…") |
| Marc la entrega | `entregada` | `entregada` = hoy, `proximoPaso` = "Pedir feedback de la caja de degustación", `fechaProximo` = hoy + 3 |
| Marc pide la opinión | `feedback pedido` | `fechaProximo` = hoy + 4 |

Si creas el aviso del calendario, guarda su id en `degustacion.avisoId`; si el día cambia, actualiza ese aviso en vez de crear otro.

## Reglas del Plan Comercial (25/10/2026)

- **Ningún lead caliente sin siguiente paso y fecha.** Un `conversando`, o con caja `ofrecida`, `confirmada` sin día, `entregada` o `feedback pedido`, sin `fechaProximo`, va a "Hoy toca" con la propuesta de fecha.
- Después de una degustación: hasta 3 seguimientos, los días 3, 7 y 14 desde la entrega, cada uno con una pregunta de sí o no ("¿Hacemos un primer pedido el viernes 6/11 o lo dejamos para enero?"). Después, uno al mes.
- Los lunes, una línea arriba con: degustaciones con fecha esta semana X/3 · hechas la semana pasada X/2 · clientes que repiten X/5 · calientes sin fecha X.

## Escribir

- Un lead: actualización con la `version` que leíste. Solo los campos que cambian.
- Varios leads: una sola escritura por lotes, si la herramienta la tiene.
- Si falla por la versión, vuelve a leer y repite. No fuerces la escritura.
- **Nunca borres un lead**: se descarta.
- Confirma a Marc en 1 a 3 líneas qué ha cambiado.
