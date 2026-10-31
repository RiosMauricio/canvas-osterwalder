# Entrevista de negocio

Antes de escribir el canvas, entrevistar al equipo sobre el negocio del
proyecto. El código dice **qué hace** el producto; no dice para quién, quién
paga ni por qué lo elegirían. Eso solo lo sabe el equipo, o descubre en la
entrevista que no lo sabe, y eso también es un resultado.

Guardar las respuestas en `docs/negocio/entrevista.md`. Las demás piezas
citan de ahí, y el diagnóstico usa los "no sé".

## Cuándo

- **Planteo completo:** siempre, después de leer el repositorio y antes del
  VPC. Si ya existe `entrevista.md`, leerla y preguntar solo lo nuevo o lo que
  cambió.
- **Modo entrevista** ("entrevistame", "haceme preguntas", "grill"): solo la
  entrevista y su resumen, sin canvas.
- **Modos parciales** (solo VPC, solo beneficios…): solo las preguntas de esa
  pieza que el repositorio no responde, como máximo 3.
- Si el usuario dice "seguí con supuestos" o "no tengo tiempo", parar, marcar
  lo que falta como `(supuesto)` y avanzar.

## Antes de preguntar: hacer la tarea

1. Leer el repositorio (README, docs, pitch, código, datos de ejemplo) y
   armar **para cada pregunta una hipótesis propia** con lo encontrado.
2. **No preguntar lo que el repositorio ya responde.** Confirmarlo en bloque
   al principio: "Por lo que leí: es una app para X que hace Y y Z. ¿Es así?".
3. Elegir las preguntas que **más riesgo** tienen para este proyecto en
   particular. No es un formulario: una app de turnos para peluquerías y una
   plataforma que une productores con compradores necesitan preguntas
   distintas.

## Cómo preguntar

- **Una pregunta por vez.** Esperar la respuesta antes de la siguiente; la
  respuesta decide qué se pregunta después.
- **Cada pregunta con tu hipótesis**: "¿Quién paga? Por el código, parece que
  el dueño del local (tiene el panel de administración). ¿Es así, o paga otro?".
  Si la herramienta de preguntas con opciones está disponible, usarla con 2–4
  opciones concretas y la recomendada primero.
- **Lenguaje simple.** El equipo puede no saber de negocios: nada de
  "segmento", "propuesta de valor" ni "canales" sin explicar. Preguntar "¿quién
  es la persona que usaría esto un martes a la mañana?", no "¿cuál es tu
  segmento?".
- **Repreguntar lo vago.** Si la respuesta es "pymes", "todos", "estudiantes",
  "lo vamos a vender por redes", pedir un ejemplo concreto: "nombrame una
  persona o empresa real que lo usaría".
- **Pedir hechos, no opiniones** (método *The Mom Test*). "¿A alguien le
  gustaría?" no sirve: cualquiera dice que sí. Preguntar por el pasado:
  "¿hablaste con alguien que tenga este problema? ¿Qué usa hoy? ¿Cuánto le
  cuesta?".
- **"No sé" es una respuesta válida.** Anotarla, no insistir, y seguir. Se
  convierte en alerta del diagnóstico y en hipótesis a validar.
- **Contar el avance**: "pregunta 4, quedan unas 5".

## Banco de preguntas

Elegir de acá según el proyecto (entre 6 y 12 en total, empezando por las del
bloque 1). Las marcadas ★ casi nunca se saltean.

**1. Problema y cliente**
- ★ ¿Qué problema resuelve, contado como le pasa a alguien concreto?
- ★ ¿Quién tiene ese problema? Nombrar a alguien real (persona, negocio, área).
- ¿Cómo lo resuelve hoy, sin el producto? ¿Qué le molesta de eso?
- ¿Hablaron con alguien que tenga el problema? ¿Qué dijo, con sus palabras?
- ¿Cada cuánto le pasa? ¿Cuánto le cuesta (tiempo, plata, errores)?

**2. Dinero**
- ★ ¿Quién pagaría? ¿Es el mismo que lo usa?
- ¿Cuánto pagaría y cómo (por mes, por uso, una vez, comisión)? ¿En qué lo
  comparan para decidir ese precio?
- ¿Hay alguien que ya pague por algo parecido?
- ¿Cuánto les cuesta a ustedes mantenerlo (servidores, APIs, horas)?

**3. Competencia y diferencial**
- ★ ¿Qué existe hoy que haga algo parecido, aunque sea a mano o con Excel?
- ¿Por qué alguien dejaría eso para usar lo de ustedes?
- ¿Qué impide que otro equipo lo copie en un mes?
- ¿Dependen de alguien (una API, una plataforma, un permiso) que pueda
  cortarles el acceso?

**4. Llegar al cliente**
- ★ ¿Quién sería el primer cliente y cómo llegarían a él?
- ¿Tienen acceso o contactos en ese rubro?
- ¿Quién decide la compra? ¿Hay que convencer a otra persona además del usuario?

**5. Equipo y objetivo**
- ¿Qué buscan con el proyecto: aprobar una materia, un concurso, un primer
  ingreso, una empresa? (Cambia cuánto rigor tiene sentido exigir.)
- ¿Cuánto tiempo pueden dedicarle en los próximos meses?
- ¿Hay algo que el producto necesite y el equipo no tenga (datos, contactos,
  capital, permisos)?

**Plataformas (dos o más lados):** repetir las de los bloques 1 y 2 para cada
lado y agregar: ¿qué lado se consigue primero y cómo? ¿Qué gana el primer
usuario cuando todavía no hay nadie del otro lado?

## Cuándo parar

- Cuando las ★ tengan respuesta (o un "no sé" anotado) y las demás no
  cambiarían el canvas.
- A las 12 preguntas como máximo. Si quedan dudas, van como supuestos.
- Si el equipo responde "no sé" a las tres primeras ★, parar y decirlo: el
  proyecto todavía no tiene un cliente definido. Ofrecer seguir igual con
  supuestos o pasar directo al diagnóstico.

## Formato de `entrevista.md`

1. **Fecha y quién respondió.**
2. **Lo que se confirmó del repositorio** (lista corta).
3. **Preguntas y respuestas**, en orden: pregunta, respuesta (con las palabras
   del equipo) y tipo: **dato** (con fuente), **opinión del equipo** o **no
   sé**.
4. **Pendientes**: los "no sé" y las respuestas vagas, cada uno con cómo
   averiguarlo. Pasan a `hipotesis.md` y al diagnóstico.

Una respuesta del equipo es **opinión del equipo**, no dato, salvo que diga de
dónde sale ("lo dijeron 3 encargados que entrevistamos"). En el canvas se
marca `(supuesto)` igual que cualquier otro supuesto.
