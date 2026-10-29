# canvas-osterwalder

Skill para Claude Code que plantea el negocio de un proyecto actual o futuro siguiendo el método de **Alex Osterwalder**:

1. **Cómo funciona, en lenguaje natural**: propósito, quiénes participan, recorrido de punta a punta y qué es real o demo.
2. **Historia de usuario** del caso de uso principal, contada como un día del cliente.
3. **Value Proposition Canvas**, uno por segmento de cliente.
4. **Business Model Canvas**, los 9 bloques, con quién usa, decide y paga.
5. **Competencia** directa e indirecta, con el diferencial.
6. **Documento de beneficios traducible**, derivado del Value Proposition Canvas y preparado para i18n.
7. **Hipótesis** más riesgosas del modelo y cómo validarlas.

Todas las piezas comparten segmentos, términos y códigos. Juntas forman un documento completo de lógica de negocio, que también se puede generar en HTML y PDF (una hoja por pieza).

## Instalación

Copiar esta carpeta en la carpeta de skills de Claude Code:

```bash
# Para todos los proyectos (usuario)
git clone https://github.com/RiosMauricio/canvas-osterwalder.git ~/.claude/skills/canvas-osterwalder

# O solo para un proyecto
git clone https://github.com/RiosMauricio/canvas-osterwalder.git <proyecto>/.claude/skills/canvas-osterwalder
```

Reiniciar Claude Code para que la detecte.

## Uso

```
/canvas-osterwalder mi proyecto              → planteo completo
/canvas-osterwalder propuesta de valor       → solo Value Proposition Canvas
/canvas-osterwalder business model canvas    → solo los 9 bloques
/canvas-osterwalder documento de beneficios  → solo beneficios traducibles
/canvas-osterwalder versión visual           → HTML, PDF o diapositivas desde lo ya escrito
```

Al terminar un planteo, la skill ofrece una versión visual (HTML, PDF o diapositivas) que se guarda en `docs/negocio/visual/`. Los `.md` siguen siendo la fuente: lo visual se regenera a partir de ellos. El PDF se exporta con Chrome/Chromium o Playwright si están instalados; si no, la skill indica cómo guardarlo desde el navegador.

También se activa sola cuando se pide un canvas, un modelo de negocio, una propuesta de valor o un documento de beneficios.

Los resultados se guardan en `docs/negocio/` dentro del proyecto abierto (`propuesta-de-valor.md`, `business-model-canvas.md`, `hipotesis.md`, `beneficios.<idioma>.md`). Si ya existen, se actualizan. Sin proyecto abierto, la skill pregunta dónde guardarlos.

## Estructura

```
SKILL.md                                 flujo, modos, reglas y checklist de coherencia
references/como-funciona.md              propósito y recorrido del producto en lenguaje natural
references/historias-de-usuario.md       caso de uso contado, formato y criterios de aceptación
references/value-proposition-canvas.md   perfil del cliente, mapa de valor, encaje
references/business-model-canvas.md      9 bloques, competencia, patrones, validación de hipótesis
references/documento-beneficios.md       beneficios por segmento, reglas i18n, formato
references/version-visual.md             documento completo en HTML, exportación a PDF y diapositivas
```

## Créditos

Business Model Canvas y Value Proposition Canvas son de Alexander Osterwalder y Strategyzer ([strategyzer.com](https://www.strategyzer.com)), publicados bajo licencia CC BY-SA 3.0. Esta skill es una guía de uso independiente y no está afiliada a Strategyzer.

## Licencia

[CC BY-SA 4.0](LICENSE): podés usarla, adaptarla y compartirla, citando la
fuente y publicando tus cambios con la misma licencia.
