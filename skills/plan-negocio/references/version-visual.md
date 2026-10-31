# Versión visual: HTML, PDF y diapositivas

Los `.md` de `docs/negocio/` son la fuente. Lo visual se genera **desde ellos**,
nunca al revés: si el contenido cambia, se edita el `.md` y se regenera lo
visual. No agregar en lo visual nada que no esté en los `.md`.

Guardar todo en `docs/negocio/visual/` (el título de la página es
"<proyecto> · Modelo de negocio"):

```
docs/negocio/visual/
├── canvas.html          BMC + VPC, un solo archivo
├── canvas.pdf           exportado desde canvas.html
└── diapositivas.html    (o .pptx si se pide ese formato)
```

Generar solo los formatos que el usuario eligió. Si un archivo ya existe,
reemplazarlo con la versión regenerada.

## HTML (formato principal)

Un **solo archivo autocontenido**: CSS y JS inline, sin dependencias externas
salvo, como mucho, una fuente web. Tiene que abrirse con doble clic en
cualquier computadora.

### Partir siempre de la plantilla

**No dibujar el Value Proposition Canvas ni el BMC desde cero.** Copiar
`assets/plantilla-documento.html` (de esta skill) a
`docs/negocio/visual/canvas.html` y completar los campos `{{…}}`:

- Trae el CSS completo, la hoja del VPC (cuadrado + círculo partido en tres
  sectores) y la del BMC ya resueltas, más un script de ajuste y chequeo.
- **No tocar** el bloque de CSS "Círculo del perfil del cliente" ni las
  posiciones de las zonas: dentro del círculo todo se mide en `cqw` (relativo
  al ancho del círculo), así la proporción es la misma en pantalla, impresión
  y móvil. Dibujarlo a mano es lo que produce textos sobre las líneas y
  post-its fuera del círculo.
- Límites de texto (indicados en cada campo): trabajos 45 caracteres,
  frustraciones 48, alegrías 36, productos 60, aliviadores y creadores 50,
  bloques del BMC 60. Máximo 4 post-its por zona. Si algo no entra,
  **acortar el texto**; nunca agrandar zonas ni achicar la letra a mano.
- Un VPC por segmento: duplicar la `<section class="hoja vpc-a">` (cambiar
  la clase a `vpc-b`…, el color con `seg m`/`seg p` y los códigos).
- Las demás hojas (cómo funciona, caso de uso, beneficios, competencia,
  hipótesis) se arman con las clases que ya trae el CSS: `.hu`, `.roles`,
  `.recorrido`, `.linea`, `.hu-bandas`/`.banda`, `.ben`, `table`,
  `.declaracion`, `.nota`. El encabezado (`header.cabecera`) va en la hoja 1.
- Los ajustes de tamaño por hoja van por clase (`section.hoja.vpc-b …`) y con
  menos especificidad que el bloque del círculo; no pisar los tamaños de
  `.circulo`.

### Ajuste automático y chequeo

El script al final de la plantilla, al cargar y antes de imprimir:

1. **Ajusta**: si en una zona del círculo algo se sale del borde, cruza una
   línea divisoria o no entra, achica la letra de esa zona (variable
   `--escala`, mínimo 62 %).
2. **Chequea** y deja el resultado en el atributo `data-chequeo` de `<html>`:
   `"ok"` o la lista de problemas (también los marca en rojo, solo en
   pantalla). Detecta: post-its o títulos fuera del círculo o sobre las
   líneas, zonas desbordadas (también en el cuadrado y el BMC), letra
   achicada de más (< 74 %: hay que acortar textos), chips de encaje vacíos
   y campos `{{…}}` sin completar.

**No entregar sin `data-chequeo="ok"`** en dos anchos de pantalla:

```bash
C="<chrome o chromium>"   # en WSL: "/mnt/c/Program Files/Google/Chrome/Application/chrome.exe" con rutas de `wslpath -w`
for W in 1400 1000; do
  "$C" --headless --disable-gpu --virtual-time-budget=8000 --window-size=$W,1000 \
    --user-data-dir="<carpeta temporal>" --dump-dom canvas.html \
    | grep -o 'data-chequeo="[^"]*"'
done
```

Si no dice `ok`, corregir lo que lista (casi siempre: acortar textos) y
volver a correr. Después exportar el PDF y mirarlo (ver "PDF").

Es el **documento completo de lógica de negocio**: una hoja por pieza, en este
orden (de lo más fácil de leer a lo más técnico):

1. **Encabezado + cómo funciona**: nombre del proyecto, fecha, leyendas de
   segmentos y de marcas. Debajo, el propósito en una frase destacada, una
   fila de "quiénes participan" y el recorrido de punta a punta en 4–7 pasos
   numerados (una línea cada uno). Cerrar con dos bandas: qué no hace el
   producto y qué es real / qué es demo. El texto largo queda en
   `como-funciona.md` y su PDF; la hoja remite a ellos.
2. **Caso de uso**: la historia de usuario principal: la frase "Como… quiero… para…" y una línea de tiempo de
   3–5 pasos (cuándo, quién con su área, qué pasa) con los códigos del canvas
   como chips. Cerrar con tres bandas: qué funciona hoy, qué no hace el
   producto y qué es roadmap.
3. **Beneficios**: tarjetas por segmento (título corto, frase, código del
   canvas), tabla "Antes / Con <producto>", y bandas de prueba, lo que todavía
   no hay y próximo paso. Remite al `.md` traducible.
4. **Value Proposition Canvas**, uno por segmento:
   - Derecha, un **círculo** (perfil del cliente) dividido en tres: trabajos,
     frustraciones, alegrías.
   - Izquierda, un **cuadrado** (mapa de valor) dividido en tres: productos y
     servicios, aliviadores de frustraciones, creadores de alegrías.
   - Cada zona con título en lenguaje común y el término oficial como
     subtítulo chico en otra línea (ver "Nombres de las zonas" en
     `value-proposition-canvas.md`). En el círculo, las etiquetas van fuera
     de los post-its, sin ícono, y no deben cortarse contra el borde.
   - Debajo, la declaración de propuesta de valor.
5. **Business Model Canvas** con la grilla original de Osterwalder:
   - Fila superior de 5 columnas: socios clave · actividades clave / recursos
     clave (apiladas) · propuesta de valor · relación con clientes / canales
     (apiladas) · segmentos de clientes.
   - Fila inferior de 2 columnas: estructura de costos · fuentes de ingreso.
   - Cada ítem como un "post-it" breve, coloreado según su segmento.
6. **Competencia**: tabla tipo (directa/indirecta) · alternativa · qué cubre ·
   qué no cubre, y el diferencial destacado debajo. Al lado o debajo, las 5
   fuerzas como fila de 5 chips (baja / media / alta) y la barrera principal.
7. **Hipótesis**: tabla compacta (hipótesis, tipo, experimento, criterio).
8. **Diagnóstico**: el veredicto (🟢 / 🟡 / 🔴) grande arriba, el semáforo
   como tabla compacta (pregunta · estado · porqué) y las 3 alertas con su
   acción de esta semana. Es la hoja que más se mira: no esconderla al final
   si el usuario la quiere primero.

Calidad visual: el resultado se muestra a jurados e inversores, así que tiene
que verse diseñado, no como una tabla con colores. Lo que funcionó:

- Tomar la identidad visual del proyecto (tipografía y paleta del deck o la
  landing) para que combine con el pitch.
- Cada sección como una "hoja" (tarjeta) con título, número de hoja (1/4) e
  íconos SVG inline en los encabezados de cada bloque.
- Post-its con fondo **claramente tintado** por segmento (no solo un borde
  fino) y chips de la leyenda con exactamente los mismos colores. Verificar
  la especificidad CSS: una regla tipo `ul.post li` pisa a `li.m`; usar
  `ul.post li.m`.
- Post-its alineados arriba con espacio uniforme (4–6 px); nunca repartirlos
  con `justify-content: space-between`, que deja huecos desparejos.
- Un conector "encaje" entre el cuadrado y el círculo del VPC.
- En el VPC, color por **tipo de zona**, no por segmento (cada hoja ya es de
  un segmento): frustraciones y aliviadores en rojo/terracota, alegrías y creadores
  en verde, trabajos y productos en neutro. Así el encaje se ve a simple vista.
- Máximo 4 post-its por zona del VPC (los primeros por importancia); la lista
  completa queda en el `.md`, y la nota al pie lo dice.
- Cada ítem lleva su código (D1, A1, AL1, CR1…) y los aliviadores/creadores un
  chip "→ D3" con lo que responden, tomado de las tablas de encaje del `.md`.
  Una frustración o alegría mostrada sin remedio se marca como hueco (borde punteado
  + "sin respuesta"). Antes de marcar un hueco, verificar que no sea una
  omisión del `.md`.
- El círculo del perfil es un círculo SVG real partido en tres sectores
  (trabajos a la derecha, alegrías arriba a la izquierda, frustraciones abajo
  a la izquierda), con las etiquetas dentro de cada sector, sin tocar los
  divisores. Ya viene resuelto en la plantilla.
- Orden de lectura marcado sin invertir el lienzo (el estándar es cuadrado a
  la izquierda, círculo a la derecha): números ① "Empezá acá · Perfil del
  cliente" sobre el círculo y ② "Mapa de valor · lo que hace <proyecto>" sobre
  el cuadrado, más una línea "Cómo leer esta hoja" en 3 pasos (empezá por el
  círculo; buscá la respuesta en el cuadrado con el chip → D2; lo que queda
  sin respuesta es un hueco). En impresión, si no entra arriba, va en la nota
  al pie. En móvil, el círculo se muestra antes que el cuadrado.
- En móvil, las tablas pasan a tarjetas.

Diseño técnico:

- Colores definidos como variables CSS; contraste legible en modo claro y
  oscuro (`prefers-color-scheme`).
- Responsive: en pantallas angostas, la grilla del BMC se apila en una columna.
  La media query va con `screen` (`@media screen and (max-width: 900px)`):
  sin `screen`, Chrome aplica la vista apilada también al imprimir.
- `@media print`: página A4 apaisada, fondo blanco, sin sombras ni elementos
  interactivos. Una sección por hoja con
  `section + section { break-before: page }`. No usar `break-before` en la
  primera sección, porque deja el encabezado solo en la hoja 1. En impresión,
  usar un encabezado compacto en una línea y achicar también las etiquetas
  chicas (supuesto, roadmap), no solo el texto de los post-its.
- Si la hoja del VPC no entra en una página, reducir espacios fuera del
  círculo (encabezado, nota, declaración); el círculo no se toca.
- Pie con el crédito: "Business Model Canvas y Value Proposition Canvas:
  Strategyzer, CC BY-SA 3.0".

## PDF

Exportar `canvas.html` con lo que haya disponible, en este orden:

1. Chrome/Chromium headless, si está instalado:
   `<chrome|chromium> --headless --no-pdf-header-footer --print-to-pdf=canvas.pdf canvas.html`
2. Playwright, si el proyecto ya lo tiene instalado en `node_modules` (no
   instalarlo solo para esto): `page.pdf({ format: 'A4', landscape: true, printBackground: true, preferCSSPageSize: true })`.
   El Chromium de `~/.cache/ms-playwright` puede no arrancar en Linux por
   librerías del sistema faltantes (p. ej. `libnspr4.so`); en ese caso pasar
   a la opción siguiente.
3. En WSL, el Chrome o Edge de Windows
   (`/mnt/c/Program Files/Google/Chrome/Application/chrome.exe`,
   `/mnt/c/Program Files (x86)/Microsoft/Edge/Application/msedge.exe`) con
   rutas convertidas por `wslpath -w` y `--user-data-dir` en una carpeta
   temporal.
4. Si nada funciona, no instalar herramientas sin preguntar. Decirle al
   usuario: "Abrí `canvas.html` en el navegador y usá Imprimir → Guardar como
   PDF (horizontal, con gráficos de fondo)".

Después de exportar, verificar:

- Que el PDF exista y tenga **una hoja por sección** (cómo funciona, caso de uso,
  beneficios, VPC por segmento, BMC, competencia, hipótesis, diagnóstico). Más hojas
  indican desbordes o la vista móvil aplicada al imprimir.
- Los ajustes de impresión por hoja van por clase (`section.hoja.bmc`), no
  por posición (`nth-of-type`): al agregar o reordenar hojas, los selectores
  por posición apuntan a la hoja equivocada.
- Que `data-chequeo` diga `ok` (ver "Ajuste automático y chequeo").
- Si hay forma de rasterizar el PDF (PyMuPDF, `pdftoppm`), mirar las hojas.
- Para ver la vista móvil, no confiar en `--window-size` chico: Chrome tiene
  un ancho mínimo de ventana. Capturar un marco con un `<iframe>` de 375 px.

## Diapositivas

- Si el proyecto ya tiene un deck (buscar `slide-deck`, `slides`, `deck`,
  `*.pptx` en el repo), **seguir su estilo**: colores, tipografía y formato.
- Si no hay deck, generar `diapositivas.html`: autocontenido, láminas 16:9,
  navegación con flechas del teclado.
- Generar `.pptx` solo si el usuario lo pide.
- Contenido, 4 láminas como máximo, una idea por lámina:
  1. Propuesta de valor (declaraciones por segmento).
  2. Business Model Canvas (versión resumida: 1–3 ítems por bloque).
  3. Competencia y diferencial (si existe la sección en el BMC).
  4. Hipótesis y próximos pasos.
- Texto grande y poco: si un bloque no entra, resumirlo, no achicar la letra.
