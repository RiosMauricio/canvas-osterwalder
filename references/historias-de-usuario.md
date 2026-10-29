# Historias de usuario del negocio

La historia de usuario cuenta el negocio como **un día del cliente**. Es la
pieza que se entiende sin conocer el método: va primero en el documento
completo y sirve de puerta de entrada al canvas.

Se escribe **después** del VPC y del BMC, porque cada paso tiene que apuntar a
ítems reales del canvas.

## Cuántas

- **Una obligatoria**: el caso de uso principal del segmento que paga.
- Otras solo si se piden o si cubren un paso clave que hoy no existe (p. ej.
  cómo entran los datos del cliente). Marcarlas **[roadmap]** si no existen.
- Un segmento que hoy no usa el producto (p. ej. un lado pasivo de una
  plataforma) no lleva historia hasta validar su hipótesis; decirlo en una
  línea.

## Formato de cada historia

Guardar en `docs/negocio/historias-de-usuario.md`, con `HU1`, `HU2`… como
títulos.

1. **La historia contada.** 3–5 momentos con cuándo ("Lunes, 8:00"), quién
   (nombre de ejemplo y su **área real** dentro del cliente: Almacenes,
   Compras, Gerencia…) y qué pasa. Usar datos reales del proyecto (seed,
   demo, pitch); si son ilustrativos, decirlo. Cerrar con lo que el producto
   **no** hace, si eso aclara su alcance.
2. **Formato.**
   > **Como** [rol], **quiero** [acción], **para** [resultado].
3. **Criterios de aceptación.** 4–6 puntos verificables, en "Dado… cuando…
   entonces…" cuando haya una condición.
4. **Estado.** Tabla paso → **[hoy]** / **[roadmap]**, con la hipótesis que
   valida lo que falta.

## Reglas

- Las personas son de ejemplo: aclararlo en la introducción. No inventar
  clientes reales como si lo fueran.
- Cada paso de la historia debe corresponder a un aliviador o creador del VPC
  (códigos AL, CR…). Un paso sin código es una función que el canvas no
  explica: agregarla al canvas o sacarla de la historia.
- Si la historia solo se puede contar con funciones de roadmap, el producto
  todavía no resuelve el caso principal: decirlo como hallazgo.
- Lenguaje común, frases cortas. Nada de nombres técnicos (tablas, funciones)
  en la historia contada; pueden ir en los criterios si ayudan.
