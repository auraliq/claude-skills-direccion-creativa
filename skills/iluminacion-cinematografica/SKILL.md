---
name: iluminacion-cinematografica
description: Entiende, identifica y diseña la iluminación de una toma, luz clave, relleno, contraste, ratio, lado inteligente / lado tonto, motivación y luces prácticas, y la traduce a un prompt en inglés para video con IA (Higgsfield, Seedance, Kling, Veo), a luces de Blender, o a un plano de luces. Úsala SIEMPRE que el usuario quiera analizar la luz de un frame, clip o película; decidir cómo iluminar una escena o un personaje; escribir la parte de luz de un prompt de video o imagen con IA; iluminar una escena en Blender; o cuando aparezcan palabras como luz, iluminación, sombras, contraste, key light, fill, relleno, contraluz, rim, chiaroscuro, "look cinematográfico", "se ve plano", "más dramático" o "más cálido", aunque no diga "iluminación".
---

# Iluminación cinematográfica

La luz decide qué ve el espectador de una cara y qué siente de la escena. StudioBinder lo
plantea así: la iluminación cambia cómo percibimos al personaje y su estado mental. La
herramienta más fina para eso no es la luz principal, es **cuánto relleno le pones**.

El orden de trabajo es siempre **intención → contraste → construcción → traducción**, igual que
en `angulos-de-camara`, con la que se combina: el lado inteligente depende de dónde está la
cámara.

## 1. Intención: qué tiene que sentir el espectador

| Si la escena pide… | Contraste / relleno | Fuente |
|---|---|---|
| claridad, calma, algo amable, informativo o aséptico | **Bajo contraste**: relleno fuerte, casi sin sombras (*Her*, *Blade Runner 2049* cuarto blanco) | video ✔ |
| drama, misterio, tensión, amenaza, un personaje roto | **Alto contraste**: relleno mínimo o nulo, medio rostro en penumbra (*No Country for Old Men*) | video ✔ |
| realismo: que la luz "exista" en el mundo de la película | Luz **motivada** por una fuente lógica (ventana, lámpara, práctica en cuadro) | video ✔ |
| volumen y profundidad en la cara | Clave en el **lado inteligente**, relleno en el lado tonto | video ✔ |
| separar al sujeto del fondo | Contraluz / recorte (back light, rim) | video ✔ (Avery Dohrmann, ver `alfabetizacion-visual`) |
| sombras todavía más profundas que "sin relleno" | Relleno negativo (negative fill): tela negra del lado de sombra | nota de Gemini, fuera del video |

"video ✔" = está en un análisis visto por Gemini, en `references/`. Lo demás es conocimiento
general marcado como tal: úsalo como base razonable, no como lo que enseñó un video.

## 2. Contraste y ratio

**Exposición = clave + relleno** (así lo resume el video). La intensidad del relleno respecto a
la clave define el ratio de contraste (02:46). El video **no da números**; los que siguen son los de
uso común (general):

| Ratio (lado luz : lado sombra) | Diferencia | Se siente |
|---|---|---|
| 2:1 | 1 stop | suave, comercial, amable |
| 4:1 | 2 stops | dramático pero legible, el estándar del cine |
| 8:1 o más | 3+ stops | noir, chiaroscuro, amenaza |
| sin relleno |, | silueta parcial; el lado de sombra se pierde |

Decide el ratio por **el estado mental del personaje o el tono de la escena**, no por gusto.

## 3. Construcción

- **Clave (key):** la luz principal y más fuerte. Va en el **lado inteligente** (smart side):
  el lado de la cara que se aleja de la cámara. Según el video, lo
  tradicional es poner ahí la clave (02:17).
  Altura y ángulo de partida (general): ~45° hacia un lado y ~30–45° arriba de los ojos.
- **Relleno (fill):** va en el **lado tonto** (dumb side), el que mira a la cámara, porque ahí cae
  la sombra de la clave (02:27). Siempre más débil o igual que la clave; más
  grande y suave que la clave para no hacer sombras dobles (nota de Gemini, fuera del video).
- **Motivación:** antes de poner una luz, pregunta de dónde vendría en el mundo de la escena.
  El director de fotografía establece la fuente motivada (02:04). Si hay prácticas en cuadro (lámparas), la
  clave y el relleno toman su color, como el ámbar de *Skyfall*.
- **Contraluz / recorte:** detrás del sujeto, opuesta a la cámara, para dibujar el borde y
  separarlo del fondo. Por capas (video de Avery Dohrmann, ≈05:10): clave en el término medio,
  relleno o su ausencia en primer término y fondo, recorte para despegar al sujeto. Que no se
  note: la luz apoya la imagen, no se luce.

Si el encuadre es plano (actor contra una pared), la luz no lo salva: primero composición en
capas, luego luz (`alfabetizacion-visual`). Errores que marca el video de StudioBinder: relleno sin motivación (luz blanca en un cuarto de velas) y relleno
excesivo cuando la escena pide tensión, que aplana la imagen.

## 4. Traducción

### Prompt para video o imagen con IA (en inglés)

Escribe la luz como **fuente + lado + contraste + color**, en ese orden. Un esquema por toma.

- Bajo contraste: `soft low-contrast lighting, strong fill light, almost no shadows on the face, even and calm`
- Alto contraste: `high-contrast chiaroscuro lighting, no fill, half of the face falling into deep shadow`
- Clave en el lado inteligente: `short lighting, key light on the far side of the face away from camera, shadow side toward the lens`
- Motivada por prácticas: `motivated lighting from warm practical lamps in the background, amber tungsten tones`
- Recorte: `subtle rim light separating the subject from a dark background`

### Luces en Blender

- Clave: luz de área del lado de la cara que se aleja de la cámara. El **tamaño** de la luz de
  área controla la dureza: grande = suave.
- Relleno: luz de área más grande del lado de la cámara, con menos potencia. A la misma
  distancia, la razón de potencias (W) es aproximadamente el ratio; si las distancias son
  distintas, compensa con la ley del inverso del cuadrado.
- Relleno negativo: un plano negro del lado de sombra.
- Color de prácticas: ámbar, o un nodo Blackbody (~3200 K) en Cycles.
- Mide antes de dar por bueno: render de prueba y compara el lado de luz contra el de sombra.

## 5. Analizar la luz de un frame o un video

- **Imagen o frame:** míralo directo y llena la plantilla.
- **Video local o link de YouTube:** pásalo a Gemini con el MCP `gemini` (`ask_gemini`, archivo
  o link en `files`). Claude no ve video. Solo se manda lo que el usuario indique. Lo que Gemini
  diga y no se pueda comprobar va marcado "según Gemini".

```
Toma: <marca de tiempo o descripción>
Clave: <lado (inteligente/tonto) · altura · dura/suave · color>
Relleno: <nivel · ratio aprox. · de dónde viene>
Contraluz / prácticas: <…>
Motivación: <qué fuente del mundo justifica la luz>
Contraste y efecto: <bajo/alto · qué siente el espectador y por qué>
Prompt EN: <línea lista para pegar>
```

## Referencias

- `references/relleno.md`: la luz de relleno a fondo, con los ejemplos y las citas del video
  con marca de tiempo. Léelo cuando haya que justificar el nivel de relleno o la posición
  clave/relleno.
- Para una pieza completa, del mercado a la toma, `direccion-creativa` usa esta skill en los pasos 8 (imagen) y 9 (shot list).
