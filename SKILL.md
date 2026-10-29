---
name: canvas-osterwalder
description: "Plantear el negocio de un proyecto actual o futuro siguiendo el método de Alex Osterwalder (Strategyzer): Business Model Canvas (9 bloques), Value Proposition Canvas por segmento de cliente, historia de usuario del caso principal, competencia directa e indirecta, documento de beneficios traducible (i18n), hipótesis y una explicación en lenguaje natural de cómo funciona el producto; todo junto en un documento completo de lógica de negocio. Usar cuando pidan canvas, lienzo, modelo de negocio, Business Model Canvas, propuesta de valor, Value Proposition Canvas, historia de usuario o caso de uso del negocio, competencia, beneficios del producto, cómo funciona el producto explicado en lenguaje común, o el planteo de negocio de un proyecto nuevo o existente."
---
# Canvas Osterwalder: modelo de negocio, propuesta de valor y beneficios

Plantear el negocio de $ARGUMENTS con el método de Alex Osterwalder. El resultado por defecto es un **documento completo de lógica de negocio**, con estas piezas encadenadas:

1. **Cómo funciona, en lenguaje natural** → el propósito en una frase, quiénes participan, el recorrido de punta a punta y qué es real y qué es demo, sin jerga; es la puerta de entrada.
2. **Historia de usuario** del caso de uso principal → el negocio contado como un día del cliente.
3. **Value Proposition Canvas** (uno por segmento de cliente) → qué valor creamos y para quién.
4. **Business Model Canvas** (9 bloques), con quién usa, decide y paga dentro del cliente → cómo ese valor se entrega, se cobra y se sostiene.
5. **Competencia** directa e indirecta, con el diferencial.
6. **Documento de beneficios traducible** → el mismo valor comunicado a cada destinatario, listo para traducir.
7. **Hipótesis** riesgosas y experimentos.

Todas las piezas comparten los mismos segmentos, términos y códigos (D1, AL1, CR1…): lo que se escribe en una no puede contradecir a las otras.

## Modos

Detectá qué pide el usuario y hacé solo eso, salvo que pida el planteo completo:

| Pedido | Qué entregar | Guía |
|---|---|---|
| "canvas", "modelo de negocio", "planteo completo", "documento completo" | Todas las piezas, en orden, más la versión visual si se acepta | todas |
| "historia de usuario", "caso de uso" | Historias de usuario del negocio | `references/historias-de-usuario.md` |
| "cómo funciona", "explicalo en simple", "propósito" | Explicación en lenguaje natural (`.md` y PDF) | `references/como-funciona.md` |
| "propuesta de valor" | Value Proposition Canvas por segmento | `references/value-proposition-canvas.md` |
| "Business Model Canvas", "lienzo" | Los 9 bloques (con VPC resumido si no existe) | `references/business-model-canvas.md` |
| "beneficios", "documento de beneficios" | Documento traducible (deriva del VPC) | `references/documento-beneficios.md` |
| "versión visual", "HTML", "PDF", "slides" del canvas | Visual generado desde los `.md` existentes | `references/version-visual.md` |

Leé la guía correspondiente **antes** de escribir.

## Flujo

1. **Contexto.** Si estás en un repositorio, leé README, `docs/`, pitch, glosario y planes. Usá datos reales (números, usuarios, fuentes, precios). Si es un proyecto futuro sin código, preguntá como máximo 3 cosas clave (quién es el cliente, qué problema, cómo se gana dinero) y avanzá con supuestos.
2. **Segmentos primero.** Listá los segmentos de cliente. Si hay más de un tipo de cliente que interactúa a través del producto (p. ej. compradores y vendedores), es una **plataforma multilateral**: cada lado lleva su propio VPC y su propia propuesta de valor en el BMC.
3. **VPC por segmento** → **BMC** (con competencia) → **beneficios**, en ese orden.
4. **Historia de usuario.** Con el VPC y el BMC hechos, escribí la historia del caso de uso principal y marcá en cada paso los códigos del canvas que aparecen (ver `references/historias-de-usuario.md`). Si la historia no se puede contar con lo que el producto hace hoy, eso es un hallazgo: decilo.
5. **Cómo funciona.** Con todo lo anterior, escribí la explicación en lenguaje natural (ver `references/como-funciona.md`). Si hay código, verificá cada afirmación contra el código y separá lo real de lo de demostración.
6. **Hipótesis.** Al terminar, marcá las 3–5 hipótesis más riesgosas del modelo (las que, si son falsas, lo derrumban) y proponé el experimento más barato para validar cada una (ver la sección "Validar" de `references/business-model-canvas.md`).
7. **Coherencia.** Verificá con el checklist de abajo antes de entregar.
8. **Versión visual.** Al terminar, ofrecé (no generes sin preguntar) una versión visual de lo que se escribió: **HTML**, **PDF** o **diapositivas**, uno o varios. Si el usuario acepta, seguí `references/version-visual.md` y partí **siempre** de `assets/plantilla-documento.html` (no dibujes el canvas desde cero); no entregues sin que su chequeo diga `ok`. Si el usuario pide directamente "versión visual", "HTML", "PDF" o "slides" del canvas, generala a partir de los `.md` existentes sin rehacer el contenido.

## Dónde guardar los resultados

- **Si hay un proyecto abierto** (repositorio o carpeta de trabajo), guardar en `docs/negocio/` dentro del proyecto:

  ```
  docs/negocio/
  ├── como-funciona.md             propósito y recorrido en lenguaje natural (+ .pdf)
  ├── historias-de-usuario.md      caso de uso principal (y otros si se piden)
  ├── propuesta-de-valor.md        VPC de todos los segmentos
  ├── business-model-canvas.md     los 9 bloques, competencia y patrones
  ├── hipotesis.md                 hipótesis riesgosas y experimentos
  ├── beneficios.<idioma>.md       uno por idioma (es, en, pt-BR…)
  ├── beneficios.<idioma>.json     opcional, solo si se pide para la app
  └── visual/                      opcional: canvas.html, canvas.pdf, diapositivas.html
  ```

  Crear solo los archivos de lo que se pidió (p. ej. en modo "propuesta de valor", solo `propuesta-de-valor.md`).
- **Si no hay proyecto**, preguntar dónde guardar antes de crear archivos.
- **Si los archivos ya existen**, leerlos y actualizarlos en lugar de crear copias; al terminar, resumir qué cambió respecto de la versión anterior.
- En el chat, entregar un resumen breve y la lista de archivos creados o actualizados, no el contenido completo.

## Reglas comunes

- Escribí en el idioma del usuario (por defecto español neutro).
- Cada ítem del canvas es una frase corta y concreta (como un post-it), no un párrafo.
- Distinguí **dato** (con fuente), **estimación** (con la cuenta) y **supuesto** (marcado `(supuesto)`).
- No inventes clientes, testimonios, cifras de mercado ni competidores. Si no hay dato, decilo y proponé cómo conseguirlo.
- Para la competencia o alternativas, separá **directa** e **indirecta** y nombrá lo que el cliente usa hoy (incluido "Excel", "no hacer nada", "hacerlo a mano").
- Si el producto podría mover dinero (pagos, comisiones), preguntá si se quiere; no lo asumas como fuente de ingreso.
- Preferí tablas para presentar los canvas en texto. Lo visual se genera aparte (paso 8 del flujo).

## Checklist de coherencia

- [ ] Cada segmento del BMC tiene su VPC y al menos una propuesta de valor.
- [ ] Cada propuesta de valor del BMC responde a frustraciones o alegrías concretas del VPC.
- [ ] Cada fuente de ingreso dice **quién paga, por qué y cuánto** (aunque sea estimado).
- [ ] Cada actividad y recurso clave está al servicio de alguna propuesta de valor; si no, sobra.
- [ ] Los costos cubren las actividades y recursos clave listados.
- [ ] Cada beneficio del documento sale de un aliviador de frustraciones o creador de alegrías del VPC.
- [ ] Los mismos nombres de segmentos y términos en todas las piezas.
- [ ] Cada paso de la historia de usuario apunta a ítems reales del VPC, y lo que es roadmap está marcado.
- [ ] La explicación en lenguaje natural no contradice al canvas, no usa jerga sin explicarla y separa lo real de lo de demostración.
- [ ] La competencia está separada en directa e indirecta, y el diferencial no es algo que el cliente ya tiene.

## Crédito

Business Model Canvas y Value Proposition Canvas: Alexander Osterwalder y Strategyzer (strategyzer.com), publicados bajo licencia CC BY-SA 3.0. Libros de referencia: *Business Model Generation* (2010), *Value Proposition Design* (2014), *Testing Business Ideas* (2019).
