---
name: angulos-de-camara
description: Entiende, identifica y elige ángulos de cámara (picado, contrapicado, cenital, nivel de ojos, holandés, ras de suelo) y los traduce a lo que se necesita después, prompt en inglés para un generador de video con IA (Higgsfield, Seedance, Kling, Veo), parámetros de cámara en Blender, o un shot list. Úsala SIEMPRE que el usuario quiera analizar un plano, un frame, un clip o una película; planear tomas o un storyboard; escribir el prompt de cámara de un video con IA; colocar la cámara de una escena de Blender; o cuando aparezcan palabras como ángulo, picado, contrapicado, cenital, high angle, low angle, bird's eye, dutch angle, encuadre, "desde arriba", "desde abajo" o "cómo se ve más poderoso / más vulnerable", aunque no diga "ángulo de cámara".
---

# Ángulos de cámara

El ángulo es **dónde está la cámara respecto a los ojos del sujeto y hacia dónde apunta**. No es decoración: cambia lo que el espectador siente por el personaje y cuánto entiende del espacio. Un ángulo sin intención es el error más común (StudioBinder lo dice explícito: se usa "porque se ve cool").

Por eso el orden de trabajo es siempre **intención → ángulo → construcción → traducción**.

## 1. Intención: qué tiene que sentir o entender el espectador

| Si quieres que el espectador… | Ángulo | Fuente |
|---|---|---|
| entienda la geografía, la escala, cuánta gente hay | Picado **narrativo**: alto, inclinación leve, plano general | video ✔ |
| sienta vértigo, peligro físico, caída | Picado **visceral**: muy alto, inclinación fuerte o cenital | video ✔ |
| vea al personaje débil, atrapado, a merced de algo | Picado **de personaje**: un poco arriba de los ojos, mirando abajo | video ✔ |
| sienta suspenso: el peligro ya está ahí y el personaje no lo sabe | Picado + personaje expuesto en el cuadro (método Hitchcock) | video ✔ |
| vea al personaje poderoso, amenazante, heroico | Contrapicado (low angle) | general · pendiente de video |
| se identifique con el personaje como igual, sin juicio | Nivel de ojos (eye level) | general · pendiente de video |
| sienta que algo está mal, inestable, desquiciado | Holandés (dutch / canted) | general · pendiente de video |
| vea el patrón, el mapa, la coreografía desde Dios | Cenital (overhead / bird's eye, 90°) | video ✔ (como extremo del picado) |
| sienta al sujeto gigante o el suelo como protagonista | Ras de suelo / gusano (ground level / worm's eye) | general · pendiente de video |

"video ✔" = está en un análisis visto por Gemini, en `references/`. "pendiente de video" = conocimiento general de cine; trátalo como base razonable, no como lo que enseñó un video. Cuando el usuario analice el video de ese ángulo, se sustituye.

## 2. Construcción: los tres ejes

Todo ángulo se describe con tres números. Escríbelos siempre, porque son lo que se traduce a Blender o a un prompt sin ambigüedad:

1. **Altura de cámara respecto a la línea de ojos** del sujeto (adulto de pie ≈ 1.6 m; sentado ≈ 1.2 m).
2. **Inclinación vertical (tilt)**: 0° = horizontal; negativo = mira hacia abajo (picado); positivo = hacia arriba (contrapicado); −90° = cenital.
3. **Giro sobre el eje del lente (roll)**: 0° normal; 10–30° = holandés.

Rangos de referencia (general, ajústalos a la escena):

| Ángulo | Altura vs. ojos | Tilt | Roll |
|---|---|---|---|
| Nivel de ojos | = | 0° | 0° |
| Picado leve / narrativo | +0.5 a +3 m (o mucho más en un general) | −10° a −25° | 0° |
| Picado fuerte / de personaje | +0.3 a +1 m, cerca del sujeto | −30° a −60° | 0° |
| Cenital | muy arriba, sobre la vertical | −90° | libre |
| Contrapicado | −0.3 a −1 m | +10° a +45° | 0° |
| Ras de suelo / gusano | a centímetros del suelo | +20° a +80° | 0° |
| Holandés | cualquiera | cualquiera | ±10° a ±30° |

El ángulo se combina con **tamaño de plano, lente y movimiento**, y la combinación es lo que da el efecto. Picado + plano general + gran angular = soledad y escala. Picado + primer plano = opresión. Grúa que sube de nivel de ojos a picado = revelar el contexto.

## 3. Traducción

### Prompt para video con IA (en inglés, que es como los modelos lo entienden mejor)

Pon el ángulo **al principio** del prompt de cámara, con su tamaño de plano y su lente, y luego el movimiento. Un ángulo por toma: dos ángulos en el mismo prompt confunden al modelo.

- Nivel de ojos: `eye-level shot, medium shot, 50mm`
- Picado narrativo: `high-angle wide establishing shot, camera slightly above, shallow downward tilt, wide lens`
- Picado de personaje: `high-angle close-up looking down at the subject, subject small in the lower third of the frame`
- Picado visceral / cenital: `extreme top-down bird's-eye view, camera directly overhead looking straight down, vertigo`
- Contrapicado: `low-angle shot looking up at the subject, subject towering in frame`
- Ras de suelo: `worm's-eye view from ground level, extreme low angle`
- Holandés: `Dutch angle, canted frame tilted 20 degrees`

### Cámara en Blender (Z arriba, metros, radianes)

La forma robusta: coloca la cámara en la altura del eje 1, apúntala al sujeto con un constraint **Track To** (o calcula el look-at) y comprueba el tilt resultante. Si la pones a mano con Euler XYZ y Z=0: `rotation_euler.x = radians(90 + tilt)` (tilt −30° → 60°; cenital → 0°), y el roll holandés va en `rotation_euler.y`. Relee el valor después de ponerlo: un ángulo mal escrito no da error, solo se ve mal.

## 4. Analizar un plano, un frame o un video

- **Imagen o frame:** míralo directo y responde con la plantilla de abajo.
- **Video local o link de YouTube:** pásalo a Gemini con el MCP `gemini` (`ask_gemini`, con el archivo o el link en `files`). Claude no ve video. Solo se manda a Gemini lo que el usuario indique; nunca escojas archivos suyos para probar.
- Cuando Gemini diga algo que no se ve (inventa detalles con facilidad, sobre todo Flash), márcalo como "según Gemini".

Plantilla de respuesta por toma:

```
Toma: <marca de tiempo o descripción>
Ángulo: <nombre ES (EN)> · altura vs. ojos <x> · tilt <x°> · roll <x°>
Tamaño de plano / lente / movimiento: <…>
Intención: <qué siente o entiende el espectador, y por qué este ángulo lo logra>
Prompt EN: <línea lista para pegar>
```

## Referencias

- `references/picado.md`, el picado a fondo: sus tres tipos, el método Hitchcock, ejemplos con marca de tiempo. Léelo cuando la toma sea un picado o un cenital, o cuando haya que justificar un picado frente a otra opción.
- Para una pieza completa, del mercado a la toma, `direccion-creativa` usa esta skill en los pasos 8 (imagen) y 9 (shot list).
