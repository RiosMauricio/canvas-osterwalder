# Cómo funciona, en lenguaje natural

Explica el producto a alguien que no conoce el método ni la tecnología: un
jurado, un inversor, un cliente o un integrante nuevo del equipo. Es la puerta
de entrada al documento completo: después de leerla, el canvas se entiende.

Guardar en `docs/negocio/como-funciona.md` y, si hay forma, exportar
`como-funciona.pdf` al lado (A4 vertical, mismo estilo que el resto; ver
`version-visual.md` para la exportación).

## Estructura

1. **En una frase.** Qué hace el producto, para quién y qué no hace. Ej.:
   "avisa cuando un insumo está por faltar, recomienda un proveedor que cumple
   los requisitos y entrega un informe que respalda la elección; la compra
   sigue en el sistema del cliente".
2. **Quiénes participan.** Cada segmento y cada rol, con su área real
   (Almacenes, Compras, Gerencia…), y quién da de alta las cuentas.
3. **El recorrido, paso a paso.** De punta a punta, como lo vive el cliente:
   entrar, qué ve primero, qué toca, qué recibe, qué pasa fuera del producto,
   y cómo se usa después (auditoría, renovación…). Un subtítulo por paso, con
   un ejemplo concreto tomado de los datos reales o de la demo.
4. **De dónde salen los datos.** Fuentes, cómo se calculan los puntajes o
   reglas, y qué pasa si una fuente falla.
5. **Qué no hace.** Los límites del producto, dichos sin rodeos.
6. **Qué es real y qué es demostración.** Tabla parte → estado (funciona,
   de prueba, simulado). Nunca presentar como real algo simulado.
7. **Lo que viene.** El roadmap en 3–5 líneas.

## Reglas

- Lenguaje común: sin nombres de tablas, funciones, frameworks ni siglas sin
  explicar. Si hace falta un término técnico ("scraping", "ERP"), explicarlo
  la primera vez entre paréntesis.
- Si hay código, **verificar cada afirmación contra el código** (qué botón
  existe, qué guarda, quién puede entrar) y no contra el pitch: el pitch puede
  estar desactualizado. Si encontrás diferencias, decirlas al usuario.
- Mismos nombres y términos que el canvas y la historia de usuario.
- Frases cortas, segunda o tercera persona, presente. Ejemplos concretos antes
  que definiciones.
- Largo: 2–4 páginas A4. Si crece más, se está explicando el código, no el
  producto.
