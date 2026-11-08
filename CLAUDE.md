# Two Bites — contexto del negocio

Memoria persistente para futuras sesiones: producto, precios y reglas. Actualizar aquí cada dato operativo que Marc confirme; lo de cada lead va al Pipeline, no aquí.

## Seguimiento comercial (este chat)

- Este chat en la nube es la versión del móvil de «Seguimiento Pipeline Two Bites» del PC. Sigue siempre la skill `twobites-movil` (`.claude/skills/twobites-movil/`): respuestas cortas, solo borradores en Gmail (nunca enviar) y el pipeline al día.
- **Pipeline Two Bites** (https://claude.ai/artifact/Ra6ovVK3zZ4srzH2WN7stN, colección `leads`): la única fuente de verdad de los leads. Se lee y se escribe con la herramienta `ArtifactData`, con las reglas de `.claude/skills/twobites-movil/reference/pipeline.md`: leer antes de escribir y pasar la `version`, añadir a `notas` sin pisarlas, nunca borrar un lead. Desde aquí se apunta directamente: no hace falta el bloque «Para apuntar» de la skill.
- También lo mueven el chat del PC y un agente programado de lunes a viernes a las 8:30, que deja borradores. Antes de hablar de un lead, léelo en el pipeline: puede haber cambiado.
- Aquí también hay Google Drive: la carpeta «06 Comercial y clientes» está sincronizada desde el PC (Tarifa Two Bites 2026-27, Precios y estrategia 2026-27, carpeta Presupuestos, carpetas por cliente). Los precios salen de la Tarifa: no se inventan.

## Producto

- **Empanadas halal: ya preparadas, en stock.** No hay que producirlas bajo pedido ni pedir antelación extra por ellas (sustituye al "halal bajo pedido" del correo a Marca Condal del 15/10/2026).
- Sabores halal disponibles:
  - Carne suave
  - Carne picante
- Vegetarianas que se ofrecen: humita, espinaca y queso, caprese, cebolla y queso (vegana: verduras).
- **Conservación (fichas técnicas en Drive, oct 2026):**
  - Cruda congelada: caja de 30, 365 días a −18 °C. Hornear 7 min a 270 °C sin descongelar.
  - En horno profesional de cafetería-panadería (Pol Balbi, WhatsApp 13/03/2026): 200–210 °C, 7–10 min, girando la bandeja a mitad de cocción. "Cada horno es diferente".
  - Cocinada congelada: caja de 50. Regenerar desde congelada 12 min en horno convencional o 2 min en horno rápido; descongelada, 1 min a 270 °C. Descongelada en nevera aguanta 10 días (5 para conservar todas sus características); no se vuelve a congelar.
  - Una vez horneadas (las dos): consumir en 24 h o máx. 48 h en nevera (2–4 °C). El "5 días en nevera" que se usaba es de la cocinada descongelada sin hornear, no de lo horneado.
  - Argumento "sin merma": del congelador al horno en 7–10 min, el cliente hornea solo lo que vende.
- Copetín: 30–35 g, cajas de 40, coste 0,55 € crudo / 0,65 € cocinado.

## Stock (arcón)

- **Arcón Two Bites** (https://claude.ai/artifact/Ta4V2LBRZR6E8L2sWWD5vA, colecciones `cajas` y `recuentos`): la única fuente de verdad del stock. Marc lo rellena tocando las cajas o dictándolo en el chat; cómo leerlo y escribirlo, en `.claude/skills/twobites-movil/reference/arcon.md`.
- **En eventos (markets, córner) se llevan siempre 4 sabores:** carne a cuchillo, pollo, jamón y queso y caprese (Marc, 6/11/2026).
- El arcón: 2 filas de 4 cajas de 50 (cocinadas) apiladas, más el lateral (1 caja de pie de 50 y una cajita de alfajores). Abajo lo intacto; arriba lo manipulado del evento anterior, que se gasta 1º o 2º. Como mucho 2 sabores por caja, a veces en dos capas.
- **Control de eventos Two Bites** (https://claude.ai/artifact/SxEiLt7sW9swyeMsiDndEB, colección `eventos`): carga, ventas, invitaciones, merma, cuadre y caja de cada evento. El cambio inicial y el efectivo al cerrar se pueden contar por billetes y monedas: `caja.fondoDesglose` y `caja.efectivoDesglose` (unidades por valor en céntimos, p. ej. `"2000": 2` = 2 billetes de 20 €); `caja.fondo` y `caja.efectivo` son la suma. **Un market de varios días va como un evento por día** (Marc, 8/11/2026: caja y stock nuevos cada día, y cada día se cierra): «Palo Market 7 nov» y «Palo Market 8 nov». Si alguna vez hiciera falta un solo evento, «Cerrar la caja de hoy y empezar otro día» guarda el día en `caja.dias`.
- **Palo Market Fest** (mensual, Poblenou): de 12 a 22 h seguido; de 17:00 a 17:30 solo cambia el acceso del público, el puesto no se puede cerrar. Más de la mitad se vende de 19 a 22 h. Sábado 7/11/2026: 274 empanadas y 1.000 €; con 271 llevadas, se agotó hacia las 20:40. Plan y datos de septiembre: «Palo-Market-Plan-Integral-Two-Bites.pdf» en Drive. Espacio: 511,50 € en septiembre (módulo + 3.000 W). Octubre se canceló a mitad del sábado por lluvia y alerta roja; en compensación, noviembre costó el 50 % (Marc, 8/11/2026; apuntado como 255,75 € a medias entre los dos días).

## Precios (sin IVA, vigentes oct 2026)

- **Pedido entregado:** clásica o veggie 2,80 €, premium 3,40 €, alfajor mini 1,30 €. Mínimo 90 €. Entrega en Barcelona incluida desde 150 € (por debajo, 15 €). Se entregan recién horneadas, en cajas para abrir y comer, marcadas por sabor; veggie y halal en cajas aparte.
- **Córner con horno in situ:** afterwork 14 €/persona (3 empanadas + 1 alfajor mini), cóctel de Navidad 12 €/persona. Mínimo 40 personas; desde 80, a medida. Entre semana desde las 18 h y fines de semana.
- **Recena de boda con córner (Mas Vidrier, presupuesto 027, 3/11/2026):** 7 €/invitado sin IVA, para el espacio (el precio a las parejas lo pone él). Incluye 2 empanadas por invitado con chimichurri y servilletas, horno propio y servicio de hasta 2 h; hora extra 35 €. Mínimo 30 invitados. Margen para bajar a 6,50 € y suelo de 6 €, solo a cambio de hacer todas sus recenas de 2027. Los 9 €/invitado con mínimo de 80 del 28/10 se descartaron: sus bodas son de unas 40 personas.
- **Profesional / congelado (cotizaciones de oct 2026; la tarifa oficial es «Tarifa Two Bites 2026-27», en Drive):**
  - ByKoko (19/10/2026): clásica 1,55 €, premium 1,75 €; cajas de un sabor; mínimo 2 cajas en BCN, 4 fuera de zona; entrega 15 €, incluida desde 10 cajas.
  - Virginia / Luma, Llinars (16/10/2026): ~500 uds a 1,40 € clásica y 1,70 € premium, entrega incluida; desde el 2º pedido regular, 1,35 € y 1,65 €.
  - Coste de compra (Tío Bigotes): clásica 1,13 € congelada / 1,25 € cocinada; premium 1,30 € / 1,40 €. A 1,35 € la clásica cocinada deja solo 0,10 €/ud.
  - Cajas según las fichas técnicas: cruda 30 uds, cocinada 50 uds. Las "cajas de 50" que se le dijeron a ByKoko cuadran si su producto es la cocinada.

## Presupuestos

- Marc no quiere condiciones invasivas: nada de penalizaciones ni plazos de pago impuestos; factura por pedido o mensual, como prefiera el cliente.
- **Descuentos:** como máximo un 10 % o regalar alfajores. Nunca descuentos grandes (rechazó un 50 % el primer viernes).
- **Pedidos recurrentes:** dos modalidades — semana a semana sin compromiso a precio normal, o mes completo pagado por adelantado con un 5 % de descuento. Sin permanencia en ninguna.
- **Chimichurri:** no se incluye en los pedidos entregados.
- Maquetación: ninguna sección puede quedar partida entre dos páginas; si no cabe, pasa entera a la siguiente.
- Ejemplos de sabores: variados y repartidos (no repetir carne suave y carne a cuchillo, que son casi iguales; incluir atún y otros), al final del documento y como orientativos.

- Numeración: el último presupuesto que consta es el **027** (Mas Vidrier, 3/11/2026); antes, 025 (THEKER, 30/10) y 026 (Ca n'Ayxelà, 3/11). Compruébalo en Drive («06 Comercial y clientes» → Presupuestos) antes de numerar el siguiente. Plantilla: Presupuesto_Fundacio_Eina.docx (nº 022).

## Leads

- El estado de cada lead está en el **Pipeline** (ver «Seguimiento comercial»). Aquí no se duplica.
- Notas antiguas de este chat (22–29/10/2026), ya superadas por el Pipeline: `historico-leads-oct-2026.md`.
- Calculadora de Serunion UAB, para enseñársela a Carmen o a Freddy: https://claude.ai/artifact/EUwZyx6LdMUQCmg7unr5MA
