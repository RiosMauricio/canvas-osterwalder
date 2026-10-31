# Documento de beneficios traducible

El documento **se deriva del Value Proposition Canvas**: cada beneficio sale de un aliviador de frustraciones o creador de alegrías, y cada destinatario es un segmento del canvas. Si no hay VPC, hacelo primero (aunque sea resumido).

## Insumos

- VPC por segmento y BMC del proyecto.
- Glosario existente del proyecto (p. ej. `GLOSSARY.md`): reutilizar su terminología.
- Idioma fuente y destinos. Por defecto: fuente `es`, destinos `en` y `pt-BR`. Preguntar si no está claro.

## Contenido

1. **Resumen** (≤80 palabras): la declaración de propuesta de valor del VPC, en lenguaje del cliente.
2. **Beneficios por destinatario** (uno por segmento): 3–5 beneficios, cada uno con la cadena:

   | Característica (qué hace) | Ventaja (qué permite) | Beneficio (qué gana) | Frustración/alegría del VPC | Evidencia |
   |---|---|---|---|---|

   La evidencia es un número con fuente, una estimación con su cuenta, o `(supuesto)`.
3. **Beneficios por tipo**: económicos, operativos, de riesgo/cumplimiento, ESG/sociales, estratégicos.
4. **Antes / después**: tabla de la situación actual (trabajos y frustraciones del VPC) vs. con el producto.
5. **Prueba**: casos, datos de demo, testimonios reales. Nunca inventados.
6. **Llamado a la acción**: distinto por destinatario.

## Reglas para que sea traducible

- Oraciones cortas (≤25 palabras), voz activa, un concepto por oración.
- Sin modismos, juegos de palabras, metáforas culturales ni ironía.
- No construir frases concatenando fragmentos; cada texto es una unidad completa.
- Números, monedas, fechas y unidades explícitos (`USD 1.200`, `2026-10-28`, `t`, `km`); anotar que el formato se localiza por idioma.
- Siglas expandidas la primera vez.
- Cada bloque con un **ID estable** en kebab-case, prefijado por segmento: `benefit.<segmento>.<beneficio>` (p. ej. `benefit.minera.menos-riesgo-compra`).
- **Glosario** al final: término, definición, "traducir / no traducir" (nombres de producto, marcas, normas).
- Notas para traductores donde haya ambigüedad: `<!-- nota-traduccion: ... -->`.

## Formato de salida

Ubicación: `docs/negocio/` del proyecto (ver "Dónde guardar los resultados" en `SKILL.md`).

- `beneficios.<idioma>.md`: documento legible.
- Opcional, para integrarlo en una app: `beneficios.<idioma>.json` con claves planas (`"benefit.minera.menos-riesgo-compra.title"`, `"...body"`), las mismas en todos los idiomas. Si el proyecto ya usa una librería i18n (next-intl, i18next, etc.), seguir su formato y ubicación.
- Al traducir: mismos IDs y estructura; verificar que todas las claves existan en cada idioma.
