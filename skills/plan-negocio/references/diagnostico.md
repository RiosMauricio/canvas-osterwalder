# Diagnóstico del planteo

La última pieza del documento y la más importante. Las anteriores describen el
negocio; esta **lo juzga**. Responde, sin rodeos: ¿el proyecto está bien
planteado como negocio? ¿Qué falta, qué está flojo y qué hay que hacer antes
de seguir programando?

Guardar en `docs/negocio/diagnostico.md`. Se escribe **al final**, con todas
las piezas hechas, y se resume en la primera línea del chat al entregar.

## El riesgo que esta pieza corrige

La skill parte de un proyecto que ya existe. Un canvas siempre se puede
completar, aunque el negocio no exista: es fácil escribir "segmento: pymes" y
"ingreso: suscripción" sin que nadie pague. **Llenar los bloques no es lo mismo
que tener un negocio.** El diagnóstico no se ablanda para no desanimar al
equipo: un problema detectado ahora cuesta una charla; detectado después de
meses de código, cuesta el proyecto.

## Estructura

1. **Veredicto en una frase.** Uno de estos tres, sin matices intermedios:
   - 🟢 **Bien planteado**: hay problema real, cliente identificable que paga y
     un diferencial defendible. Falta validar, no replantear.
   - 🟡 **Planteado a medias**: hay algo, pero una o dos piezas clave están en
     el aire (quién paga, diferencial, cómo se llega al cliente).
   - 🔴 **No está planteado como negocio**: hoy es un proyecto técnico, un
     ejercicio o una solución que busca problema. Decirlo así.
2. **Semáforo por pregunta.** Tabla con estado 🟢 / 🟡 / 🔴, el porqué en una
   línea y de dónde sale (código del canvas, respuesta de la entrevista, dato):

   | # | Pregunta | Rojo cuando… |
   |---|---|---|
   | 1 | ¿El problema existe y duele? | No hay frustración del VPC respaldada por un dato, una entrevista o un caso conocido; solo "supuesto" |
   | 2 | ¿Se sabe quién es el cliente? | El segmento es genérico ("pymes", "estudiantes", "todos") y no se puede nombrar a 5 personas o empresas reales que lo sean |
   | 3 | ¿Alguien paga? | No hay fuente de ingreso con quién, por qué y cuánto; o el que usa no es el que paga y nadie habló con el que paga |
   | 4 | ¿Es mejor que lo que usa hoy? | El diferencial ya lo cubre la alternativa actual (Excel, a mano, otra app) |
   | 5 | ¿Es difícil de copiar? | Las 5 fuerzas no muestran ninguna barrera (ver `business-model-canvas.md`) |
   | 6 | ¿Se puede llegar al cliente? | Los canales son "redes sociales" o "boca a boca" sin un primer cliente concreto |
   | 7 | ¿Los números cierran? | Los costos (servidores, APIs, horas del equipo) superan lo que pagarían los primeros clientes y no hay camino para que eso cambie |
   | 8 | ¿El equipo puede hacerlo? | Depende de algo que el equipo no tiene: acceso a datos, contactos en el rubro, permisos o capital |
   | 9 | ¿El producto hace lo que dice el canvas? | La historia de usuario solo se puede contar con funciones de roadmap |

3. **Las 3 alertas principales.** Lo que más compromete al proyecto, en orden.
   Cada una con: qué pasa, por qué importa y **qué hacer esta semana** (una
   acción concreta y barata, no "investigar el mercado").
4. **Lo que está bien.** 2–3 puntos fuertes reales, para construir sobre ellos.
   No inventar elogios: si no hay, decir "todavía nada validado".
5. **Supuestos sin respaldo.** Lista de todo lo marcado `(supuesto)` en las
   piezas, ordenado por riesgo. Es la lista de preguntas para salir a validar.
6. **Si hubiera que replantear.** Solo con veredicto 🟡 o 🔴: 1–3 caminos
   alternativos que aprovechen lo ya construido (otro segmento que sí paga,
   otro problema que el mismo código resuelve, vender a empresas en vez de a
   personas, etc.). Marcarlos como ideas para validar, no como recomendación
   cerrada.

## Reglas

- **Honestidad antes que tono.** Directo y respetuoso: se critica el planteo,
  no al equipo. Nada de "excelente proyecto con gran potencial" sin evidencia.
- **Cada 🔴 y 🟡 con su porqué**, apuntando a la pieza o al código del canvas
  donde se ve. Un juicio sin fuente no vale.
- **Un supuesto no es un dato.** Si las respuestas a las preguntas 1–3 son
  supuestos, el máximo es 🟡 aunque suenen bien.
- **Que el código esté terminado no suma.** El diagnóstico es del negocio, no
  de la calidad técnica.
- **Respuestas de la entrevista:** si el equipo respondió "no sé" a algo clave
  durante la entrevista (`references/entrevista.md`), eso aparece acá como
  alerta, no se rellena con supuestos.
- Las acciones son para gente sin experiencia en negocios: concretas, con
  cantidades y plazos ("hablar con 5 encargados de almacén antes del viernes
  usando las preguntas de `hipotesis.md`"), no jerga.
