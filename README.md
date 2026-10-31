# plan-negocio

Skill para agentes de IA (Claude Code, Codex, Gemini CLI, Cursor, Antigravity y otros compatibles con el estándar abierto [Agent Skills](https://agentskills.io)) que plantea el negocio de un proyecto actual o futuro siguiendo el método de **Alex Osterwalder**. Pensada para equipos que construyen un proyecto (p. ej. estudiantes de programación) y necesitan saber si además es un negocio bien planteado.

Antes de escribir, **entrevista al equipo**: lee el repositorio y hace, de a una, las preguntas que el código no responde (para quién es, quién paga, por qué lo elegirían), elegidas según el proyecto.

1. **Cómo funciona, en lenguaje natural**: propósito, quiénes participan, recorrido de punta a punta y qué es real o demo.
2. **Historia de usuario** del caso de uso principal, contada como un día del cliente.
3. **Value Proposition Canvas**, uno por segmento de cliente.
4. **Business Model Canvas**, los 9 bloques, con quién usa, decide y paga.
5. **Competencia** directa e indirecta, con el diferencial y qué tan defendible es (5 fuerzas de Porter, resumidas).
6. **Documento de beneficios traducible**, derivado del Value Proposition Canvas y preparado para i18n.
7. **Hipótesis** más riesgosas del modelo y cómo validarlas.
8. **Diagnóstico** honesto: veredicto 🟢 / 🟡 / 🔴, semáforo de 9 preguntas y las 3 alertas principales con qué hacer esta semana.

Todas las piezas comparten segmentos, términos y códigos. Juntas forman un documento completo de lógica de negocio, que también se puede generar en HTML y PDF (una hoja por pieza).

## Instalación

Con [`skills`](https://github.com/vercel-labs/skills) (requiere Node.js), sin clonar nada:

```bash
npx skills add RiosMauricio/canvas-osterwalder
```

El instalador pregunta en qué herramienta instalarla (Claude Code, Codex, Gemini CLI, Cursor…) y si es para todos los proyectos o solo para el actual. Reiniciar la herramienta para que la detecte.

<details>
<summary>Instalación manual (sin npx)</summary>

Copiar la carpeta `skills/plan-negocio` en la carpeta de skills de la herramienta. La carpeta tiene que llamarse `plan-negocio` (igual que el `name` de `SKILL.md`).

| Herramienta | Para todos los proyectos | Solo para un proyecto |
|---|---|---|
| Claude Code | `~/.claude/skills/plan-negocio` | `<proyecto>/.claude/skills/plan-negocio` |
| Codex CLI, Gemini CLI | `~/.agents/skills/plan-negocio` | `<proyecto>/.agents/skills/plan-negocio` |
| Cursor | `~/.cursor/skills/plan-negocio` | `<proyecto>/.cursor/skills/plan-negocio` |
| Antigravity | — | `<proyecto>/.agents/skills/plan-negocio` |

```bash
git clone https://github.com/RiosMauricio/canvas-osterwalder.git /tmp/plan-negocio
cp -r /tmp/plan-negocio/skills/plan-negocio ~/.claude/skills/
```

Las rutas pueden variar entre versiones: si no aparece, revisar la documentación de skills de cada herramienta.

</details>

## Uso

```
/plan-negocio mi proyecto              → planteo completo (con entrevista y diagnóstico)
/plan-negocio entrevistame             → solo la entrevista de negocio
/plan-negocio diagnóstico              → ¿está bien planteado como negocio?
/plan-negocio propuesta de valor       → solo Value Proposition Canvas
/plan-negocio business model canvas    → solo los 9 bloques
/plan-negocio documento de beneficios  → solo beneficios traducibles
/plan-negocio versión visual           → HTML, PDF o diapositivas desde lo ya escrito
```

Al terminar un planteo, la skill ofrece una versión visual (HTML, PDF o diapositivas) que se guarda en `docs/negocio/visual/`. Los `.md` siguen siendo la fuente: lo visual se regenera a partir de ellos. El PDF se exporta con Chrome/Chromium o Playwright si están instalados; si no, la skill indica cómo guardarlo desde el navegador.

También se activa sola cuando se pide un canvas, un modelo de negocio, una propuesta de valor o un documento de beneficios.

Los resultados se guardan en `docs/negocio/` dentro del proyecto abierto (`entrevista.md`, `propuesta-de-valor.md`, `business-model-canvas.md`, `hipotesis.md`, `diagnostico.md`, `beneficios.<idioma>.md`). Si ya existen, se actualizan. Sin proyecto abierto, la skill pregunta dónde guardarlos.

## Estructura

```
skills/plan-negocio/
├── SKILL.md                               flujo, modos, reglas y checklist de coherencia
├── references/
│   ├── entrevista.md                      preguntas al equipo antes de escribir
│   ├── como-funciona.md                   propósito y recorrido en lenguaje natural
│   ├── historias-de-usuario.md            caso de uso contado y criterios de aceptación
│   ├── value-proposition-canvas.md        perfil del cliente, mapa de valor, encaje
│   ├── business-model-canvas.md           9 bloques, competencia, 5 fuerzas, patrones, validación
│   ├── documento-beneficios.md            beneficios por segmento, reglas i18n
│   ├── diagnostico.md                     veredicto, semáforo y alertas
│   └── version-visual.md                  HTML, PDF y diapositivas
└── assets/plantilla-documento.html        plantilla del VPC y el BMC, con ajuste automático y chequeo
```

La carpeta `skills/` permite sumar más skills al mismo repositorio; `npx skills add` las detecta todas.

## Créditos

Business Model Canvas y Value Proposition Canvas son de Alexander Osterwalder y Strategyzer ([strategyzer.com](https://www.strategyzer.com)), publicados bajo licencia CC BY-SA 3.0. Esta skill es una guía de uso independiente y no está afiliada a Strategyzer.

## Licencia

[CC BY-SA 4.0](LICENSE): podés usarla, adaptarla y compartirla, citando la
fuente y publicando tus cambios con la misma licencia.
