# Arcón Two Bites: cómo leerlo y escribirlo

Página: https://claude.ai/artifact/Ta4V2LBRZR6E8L2sWWD5vA (herramienta `ArtifactData`). Marc la rellena tocando las cajas en el móvil o dictándolo en el chat: las dos vías escriben lo mismo.

## El arcón

- 2 filas (pilas) de 4 cajas de 50 empanadas cocinadas, más el lateral: 1 caja de pie (50) y una cajita de alfajores.
- Abajo, lo intacto. Arriba, lo manipulado en el evento anterior, que se gasta 1º o 2º.
- Como mucho 2 sabores por caja, a veces en dos capas (arriba y abajo). Al juntar restos, una caja puede llevar más de 50 (52, 62…).

## Colección `cajas` (un documento por hueco)

| `doc_id` | Hueco |
|---|---|
| `f1-1` … `f1-4` | Fila 1, de abajo (1) a arriba (4) |
| `f2-1` … `f2-4` | Fila 2, igual |
| `lat-pie` | Lateral · caja de pie |
| `lat-alf` | Lateral · cajita de alfajores |

Campos:
- `posicion`: el hueco en texto ("Fila 2 · 3ª desde abajo").
- `lineas`: `[{ sabor, uds, capa? }]`. `capa` ("arriba" o "abajo") solo si la caja tiene las dos capas.
- `prioridad`: 1 = gastar 1º, 2 = gastar 2º, 0 = intacta.
- `sinContar`: true si se guardó con prisa; las `uds` son aproximadas.
- `actualizado`: fecha y hora ISO.
- Hueco vacío: sin documento o con `lineas: []`.

`sabor`, con el nombre del catálogo: Carne suave, Carne picante, Carne a cuchillo, Pollo suave ("pollo" a secas), Pollo picante, Jamón y roquefort, Jamón y queso, Cebolla y queso, Bacon y queso, Chorizo picante, Humita, Espinaca y queso, Caprese, Atún, 4 quesos, Verduras; premium: Vacío y provolone, Smashburger, Cabra y caramelizada, Provolone y oliva; halal: Carne suave halal, Carne picante halal; Alfajores (o Alfajor mini, Alfajor mini pistacho, Alfajor grande).

## Colección `recuentos` (uno por día, `doc_id` = AAAA-MM-DD)

`fecha`, `hora`, `empanadas`, `alfajores`, `cajas`, `sinContar`, `porSabor: [{ sabor, uds }]`. La página lo reescribe sola cada vez que se guarda una caja. La diferencia entre dos días es lo que salió (eventos) o entró (compras): sirve para saber cuánto se vende en cada evento.

## Cuando Marc dicta el stock

1. Lista `cajas` para tener las `version` y lo que hay.
2. Escribe con `set` el documento entero de cada caja que cambie (`if_version` si ya existe). Varias cajas, en una sola `batch`.
3. Reescribe el recuento de hoy (`recuentos/<hoy>`) con los totales nuevos, en la misma `batch`.
4. Confirma en 1 a 3 líneas: total de empanadas y qué hay que sacar primero.

- Si no queda claro el hueco, el sabor o las unidades, pregunta antes de escribir. No inventes unidades.
- No borres documentos: una caja vacía se escribe con `lineas: []`.
