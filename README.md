# Índice de Exposición Ocupacional a la IA

Visualización interactiva del **Anthropic Economic Index** (Massenkoff & McCrory, 2026) — exposición de ocupaciones al uso real de modelos de lenguaje, basada en datos de conversaciones de Claude.

🔗 [Ver paper](https://www.anthropic.com/research/labor-market-impacts) · [Dataset en HuggingFace](https://huggingface.co/datasets/Anthropic/EconomicIndex)

---

## Descripción

La app permite explorar la exposición observada y teórica a la IA para 756 ocupaciones SOC (Standard Occupational Classification · BLS), organizadas en tres vistas:

- **Ranking** — listado de ocupaciones ordenado por exposición observada, con filtros por sector y búsqueda
- **Por Sector** — agrupación sectorial con exposición promedio observada y teórica (β)
- **Teórico vs Real** — gráfico de radar comparando ambas métricas por sector, con tabla de brecha en pp

## Métricas

**Exposición Observada** (`observed_exposure`): fracción de tareas de cada ocupación que aparece en conversaciones reales de trabajo con Claude. Para que una tarea cuente debe superar un umbral mínimo de tráfico (≥100 conversaciones laborales), ser teóricamente realizable con un LLM (β ≥ 0.5), y se pondera según qué proporción del uso es automativo vs. augmentativo. El índice ocupacional es el promedio ponderado por fracción de tiempo de cada tarea.

**Exposición Teórica (β)**: índice de Eloundou et al. (2023) — proporción de tareas donde un LLM puede acelerar la ejecución al menos al doble, según evaluación de expertos sobre tareas O\*NET. Mide potencial tecnológico, no adopción efectiva.

## Datos

| Archivo | Descripción |
|---|---|
| `job_exposure.csv` | 756 ocupaciones con `occ_code`, `title`, `observed_exposure` |
| `task_penetration.csv` | 17.998 tareas con nivel de penetración en Claude |

Fuente: [Anthropic/EconomicIndex](https://huggingface.co/datasets/Anthropic/EconomicIndex) en HuggingFace.

## Stack técnico

- HTML/CSS/JS vanilla — sin frameworks, sin dependencias externas
- Datos embebidos directamente en el HTML (arrays JS)
- SVG nativo para el gráfico de radar (D3 no requerido)
- Fuentes: Playfair Display, DM Mono, DM Sans (Google Fonts)
- Deploy: sitio estático, compatible con Vercel / GitHub Pages

## Deploy

El proyecto es un único archivo `index.html` autocontenido.

```bash
# Clonar
git clone https://github.com/tu-usuario/tu-repo.git

# No requiere build — abrir directamente en browser
open index.html
```

Para Vercel: conectar el repo y hacer deploy como sitio estático. No requiere `vercel.json`.

## Estructura del repo

```
.
├── index.html     # App completa (datos + lógica + estilos)
└── README.md
```

## Referencia

Massenkoff, M. & McCrory, E. (2026). *Labor market impacts of AI: A new measure and early evidence*. Anthropic.

---

Desarrollado por [Verónica Teilletchea](https://www.linkedin.com/in/verónica-teilletchea)
