# Exposición Laboral a la IA

Visualización interactiva del **Anthropic Economic Index** (Massenkoff & McCrory, 2026) — exposición de ocupaciones al uso real de modelos de lenguaje, basada en datos de conversaciones de Claude.

🔗 [Paper](https://www.anthropic.com/research/labor-market-impacts) · [Dataset en HuggingFace](https://huggingface.co/datasets/Anthropic/EconomicIndex)

---

## Qué muestra

756 ocupaciones SOC (BLS) organizadas por sector, con su exposición observada a la IA y el detalle de tareas cuando está disponible. La búsqueda permite explorar por ocupación o por tarea específica.

## Métricas

**Exposición observada** — fracción del tiempo laboral correspondiente a tareas donde la IA ya opera: aparecen en uso real de Claude y son teóricamente ejecutables por un LLM. Un valor de 0,45 significa que el 45 % del tiempo de esa ocupación ya está tocado por la IA.

**Penetración de tarea** — frecuencia con que una tarea específica aparece en conversaciones profesionales reales con Claude. No indica reemplazo total, sino intervención habitual.

> **Nota:** 86 ocupaciones no tienen detalle de tareas por diferencia entre SOC 2022 (ocupaciones) y O*NET 2019 (tareas). Muestran exposición agregada pero no el desglose.

## Stack

- HTML/CSS/JS vanilla — sin frameworks ni dependencias externas
- Datos embebidos en el HTML
- Fuentes: Playfair Display, DM Mono (Google Fonts)
- Deploy: sitio estático en Vercel

## Deploy

Proyecto de un único archivo `index.html` autocontenido. Para Vercel: conectar el repo y hacer deploy como sitio estático.

## Referencia

Massenkoff, M. & McCrory, E. (2026). *Labor market impacts of AI: A new measure and early evidence*. Anthropic.

---

Desarrollado por [Verónica Teilletchea](https://www.linkedin.com/in/verónica-teilletchea) · Construido con Claude
