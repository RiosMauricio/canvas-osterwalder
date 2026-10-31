# Business Model Canvas (Osterwalder)

Nueve bloques. Orden recomendado para completarlo: lado derecho (cliente y valor) → centro → lado izquierdo (operación) → abajo (dinero).

```
┌──────────────┬──────────────┬──────────────┬──────────────┬──────────────┐
│ 8. Socios    │ 7. Activi-   │ 2. Propuesta │ 4. Relación  │ 1. Segmentos │
│    clave     │    dades     │    de valor  │    con       │    de        │
│              │    clave     │              │    clientes  │    clientes  │
│              ├──────────────┤              ├──────────────┤              │
│              │ 6. Recursos  │              │ 3. Canales   │              │
│              │    clave     │              │              │              │
├──────────────┴──────────────┴──────┬───────┴──────────────┴──────────────┤
│ 9. Estructura de costos            │ 5. Fuentes de ingreso               │
└────────────────────────────────────┴─────────────────────────────────────┘
```

## Los 9 bloques

1. **Segmentos de clientes**: para quién creamos valor. Tipo de mercado: masivo, nicho, segmentado, diversificado o **plataforma multilateral** (dos o más grupos interdependientes; cada uno es un segmento). Indicar cuál segmento paga. En B2B, nombrar dentro de cada cliente **quién usa, quién decide y quién paga** (área o gerencia, p. ej. Almacenes pide, Compras compra, Gerencia de Supply Chain aprueba); si es conocimiento general y no dato, marcarlo para validar.
2. **Propuesta de valor**: por qué nos eligen. Una por segmento, tomada de su VPC. Fuentes típicas de valor: novedad, desempeño, personalización, "hacer el trabajo", diseño, marca, precio, reducción de costos, reducción de riesgos, accesibilidad, conveniencia.
3. **Canales**: cómo llegamos al cliente en cada fase: conocimiento → evaluación → compra → entrega → posventa. Propios o de socios, directos o indirectos.
4. **Relación con clientes**: asistencia personal, asistencia dedicada, autoservicio, servicio automatizado, comunidades, co-creación. Para qué: captar, retener o vender más.
5. **Fuentes de ingreso**: quién paga, por qué, cuánto y cómo. Tipos: venta, cuota de uso, suscripción, alquiler/licencia, comisión/intermediación, publicidad. Precio fijo o dinámico. Si hay plataforma multilateral, decir qué lado subsidia a cuál.
6. **Recursos clave**: físicos, intelectuales (datos, marca, software, patentes), humanos, financieros.
7. **Actividades clave**: producción, resolución de problemas, plataforma/red (mantener y hacer crecer la plataforma).
8. **Socios clave**: alianzas estratégicas, coopetencia, joint ventures, proveedores. Motivo: economía de escala, reducir riesgo, conseguir recursos o actividades.
9. **Estructura de costos**: costos fijos y variables principales. ¿El modelo es impulsado por costos (lo más barato posible) o por valor (premium)? Economías de escala o de alcance.

## Competencia

Separar en una tabla con columna **Tipo**:

- **Directa**: resuelve el mismo problema para el mismo cliente.
- **Indirecta**: resuelve una parte, o es lo que el cliente usa en lugar del
  producto (sistemas que ya tiene, como su ERP; listados públicos; Excel;
  hacerlo a mano).

Columnas: tipo · alternativa · qué cubre · qué no cubre. Cerrar con el
**diferencial**: revisar qué funciones ya hace lo que el cliente tiene (p. ej.
un ERP ya avisa por punto de reorden) y no presentarlas como diferencial.

### Qué tan defendible es (5 fuerzas de Porter, resumidas)

Después de la tabla, responder estas cinco preguntas en una línea cada una,
con la fuerza como **baja / media / alta** (alta = mala para el proyecto) y el
porqué. No hace falta el análisis completo de Porter: alcanza con esto.

| Fuerza | Pregunta | Es alta cuando… |
|---|---|---|
| Nuevos entrantes | ¿Qué impide que alguien lo copie en un mes? | Basta con saber programar: no hay datos propios, red de usuarios, licencias ni contratos |
| Proveedores | ¿De quién dependemos? | Una sola API, plataforma o fuente de datos puede subir el precio, cambiar reglas o cortar el acceso |
| Clientes | ¿El cliente puede imponer precio o irse sin costo? | Son pocos y grandes, o cambiarse a otra cosa no les cuesta nada |
| Sustitutos | ¿Qué usa hoy en su lugar? | Excel, hacerlo a mano o "no hacer nada" le alcanzan |
| Rivalidad | ¿Cuántos hacen lo mismo y cómo compiten? | Muchos, y se compite por precio o gratis |

Cerrar con **la barrera principal**: lo que hace difícil copiar el proyecto
(datos acumulados, efecto red, integración con el cliente, conocimiento del
rubro, contratos). Si no hay ninguna, decirlo: es un hallazgo para el
diagnóstico, no algo para disimular. Cada fuerza **alta** pasa como alerta a
`references/diagnostico.md`.

## Patrones de modelo de negocio

Si aplica, indicá qué patrón(es) de *Business Model Generation* sigue el proyecto y qué implica:
- **Plataforma multilateral**: el valor crece con la cantidad de participantes de cada lado; el reto es el "huevo o la gallina" (qué lado se consigue primero).
- **Gratis / freemium**: un segmento no paga y otro financia.
- **Long tail**: muchos productos de nicho, cada uno con poco volumen.
- **Desagregación**: separar relación con clientes, innovación de producto e infraestructura.
- **Abierto**: crear valor colaborando con terceros.

## Presentación

Entregá el canvas como tabla de 9 filas (bloque → contenido en viñetas cortas). Si hay varios segmentos, asigná a cada uno un color o una etiqueta (p. ej. `[M]` minera, `[P]` proveedor) y marcá con ella los ítems que le corresponden en todos los bloques.

## Validar (Testing Business Ideas)

Para cada hipótesis riesgosa indicá:

| Hipótesis | Tipo | Experimento | Métrica | Criterio de éxito |
|---|---|---|---|---|

- **Tipo**: deseabilidad (¿lo quieren?), factibilidad (¿podemos hacerlo?), viabilidad (¿deja dinero?).
- Experimentos baratos primero: entrevistas, landing page, prototipo en papel, preventa, "mago de Oz" (servicio manual simulando el producto), piloto con un cliente.
