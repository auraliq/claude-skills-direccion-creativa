# claude-skills-direccion-creativa

A pack of six Claude Code skills for creative direction of ads and AI-generated video. The
skills are written in Spanish and built on named books and on cinematography craft: from "who
is the market and what do they believe" down to "what is in each shot and what does the camera
prompt say".

Author: Ricardo Delgado ([auraliq.io/ricardo](https://www.auraliq.io/ricardo) ·
[LinkedIn](https://www.linkedin.com/in/ricardo-delgado-0626642a7)) · ricardo@auraliq.io

## Why it exists

Ads fail upstream far more often than in production: nobody placed the market, the idea does
not fit in one sentence, or the story has nobody who wants something. A good-looking shot does
not fix that. I wrote these skills so Claude walks the same path a creative director would,
in order, and stops at the first broken layer instead of polishing the last one.

## What is inside

| Skill | What it does |
|---|---|
| `direccion-creativa` | The conductor. An 11-step path from market research to shot list and campaign testing (Schwartz, Ogilvy, Sullivan, Truby, Cron). Calls the other five at the right moment. |
| `publicidad` | Positioning, message, beliefs, channel and sharing, from five marketing books (Ries and Trout, Miller, Broas, Berger, Weinberg and Mares). Includes an ad brief and a diagnostic. |
| `alfabetizacion-visual` | Reading and building images: frame first, three depth layers, light in service of composition. |
| `dirigir-la-mirada` | Where the viewer looks: framing, eyelines, focus, color, light, sound. |
| `iluminacion-cinematografica` | Key, fill, ratio, motivation, translated to AI-video prompts and Blender lights. |
| `angulos-de-camara` | High, low, overhead, dutch and eye-level angles, with camera numbers and prompts. |

Layout:

```
skills/
  direccion-creativa/SKILL.md
  publicidad/SKILL.md + references/ (5 book summaries in my own words)
  alfabetizacion-visual/SKILL.md
  dirigir-la-mirada/SKILL.md + references/
  iluminacion-cinematografica/SKILL.md + references/
  angulos-de-camara/SKILL.md + references/
```

## Install

Copy the folders you want into your personal or project skills directory:

```bash
# personal (all projects)
cp -R skills/* ~/.claude/skills/

# or one project only
mkdir -p .claude/skills && cp -R skills/* .claude/skills/
```

Restart Claude Code. The skills trigger from their descriptions; you can also name one
directly (for example "use direccion-creativa").

## Example prompts

1. "Hazme un anuncio de 15 segundos para Reels de una app que agenda citas a dentistas."
   Claude walks the 11 steps and returns the market level, the one-sentence idea, the script
   by seconds and a shot list with English prompts for a video model.
2. "Esto no pega: revisa este guion de 30 s y dime qué capa está rota." Claude reviews from the
   top (market, idea, story, script, image), stops at the first broken layer, cites the book
   and rewrites the line.
3. "Hazme el prompt en inglés de un picado con la luz dura y el producto como lo más nítido."
   `angulos-de-camara`, `iluminacion-cinematografica` and `dirigir-la-mirada` combine into a
   single prompt, with camera height, tilt and light placement.

Example of the kind of output (shot list row):

```
| 3 | 4-6s | desire | she opens the empty calendar | eye-level, medium, 50mm | F: window frame · M: her · B: street | warm window key, low fill | the screen | "Lunes." | eye-level medium shot, layered composition, ... |
```

## Limits

- The skills are in Spanish; the generated prompts for video models are in English.
- The book material is summarized in my own words, with at most short paraphrases. It is a
  working method, not a replacement for reading the books.
- `alfabetizacion-visual` is partial (first minutes of one talk). Film examples come from
  automated video analysis and may be misattributed; check them before citing.
- Video-model prompts depend on the model you use; test and adjust.

## License

Content: CC BY 4.0. See `LICENSE`. Credit: Ricardo Delgado.

---

## Seccion en espanol

Un paquete de seis skills de Claude Code para dirigir anuncios y video con IA. Parten del
mercado (quien es, que cree, cuantas promesas iguales ya oyo) y bajan hasta cada toma: capas,
mirada, luz, angulo y el prompt en ingles para el generador de video.

**Instalacion:** copia `skills/*` a `~/.claude/skills/` (todos tus proyectos) o a
`.claude/skills/` de un proyecto y reinicia Claude Code.

**Como usarlo:** pide "hazme un anuncio de 15 segundos para...", "esto no pega, revisalo" o
"dale una vuelta a este guion". `direccion-creativa` lleva el orden y llama a las demas.

**Por que:** los anuncios casi siempre fallan arriba (mercado, idea, historia), no en la
produccion. Estas skills obligan a revisar de arriba abajo y detenerse en la primera capa rota.

**Limites:** los libros estan resumidos en mis palabras; leelos para el detalle. Los ejemplos
de pelicula vienen de analisis automatico y conviene comprobarlos.
