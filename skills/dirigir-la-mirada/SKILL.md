---
name: dirigir-la-mirada
description: Decide y controla a dónde mira el espectador dentro del cuadro y en qué orden, encuadre (centro, tercios, proporción áurea), bloqueo y líneas de mirada, foco y profundidad de campo, movimiento de cámara, color y vestuario, líneas guía, cuadro dentro del cuadro, luz y sonido, y lo traduce a un prompt en inglés para video con IA, a cámara y foco en Blender, o a notas de dirección. Úsala SIEMPRE que el usuario quiera que algo "se note", que el ojo vaya a un producto, un personaje o un detalle; analizar por qué un plano funciona o se ve confuso; componer un frame, un anuncio, un storyboard o una escena de Blender; o cuando aparezcan palabras como composición, encuadre, punto focal, regla de tercios, foco, desenfoque, rack focus, "que resalte", "no se ve qué es lo importante" o "a dónde mira la gente", aunque no diga "dirigir la mirada".
---

# Dirigir la mirada

Un buen plano decide **qué ve primero el espectador, qué después y qué ignora**, sin necesidad
de cortar. StudioBinder lo divide por departamentos: encuadre, diseño de producción,
iluminación y sonido, y cierra con que dirigir la mirada es trabajo de todos a la vez (*The
Grand Budapest Hotel*, ~11:00).

El orden de trabajo es **jerarquía → herramientas → revisar que no compitan → traducción**.
Se combina con `angulos-de-camara` (desde dónde) y con `iluminacion-cinematografica` (lo más
brillante manda).

## 1. Jerarquía: decide el recorrido del ojo antes de componer

Escribe en una línea: **1.º el ojo va a ___, 2.º a ___, ignora ___.** Si no lo puedes escribir,
el cuadro todavía no tiene intención. Un solo punto principal por momento; el resto se apaga.

## 2. Las herramientas (todas del video ✔)

| Herramienta | Cómo atrae el ojo | Ejemplo del video |
|---|---|---|
| **Centro** | el ojo va primero al eje medio | *Nosferatu* (2024) ~0:45 |
| **Tercios** | sujeto en una intersección de la cuadrícula 3×3 | *Zero Dark Thirty* ~1:00 |
| **Proporción áurea** | una espiral que lleva del fondo al sujeto | *The Fall* ~1:18 |
| **Líneas de mirada (eyelines)** | miramos a donde miran los personajes | *High and Low* ~2:00 |
| **Bloqueo** | el único rostro que vemos gana, aunque esté lejos | *Twin Peaks* (2017) ~2:18 |
| **Foco / profundidad de campo** | el ojo se ancla en lo nítido e ignora lo borroso, aunque sea enorme | *Man on Fire* ~2:44 |
| **Rack focus** | cambiar el foco a mitad de toma mueve la atención sin cortar | *Eddington* ~2:53 |
| **Avance de cámara (push in)** | acercarse a alguien lo vuelve el centro | *Titanic* ~3:15 |
| **Dolly + paneo** | el movimiento pasa el protagonismo de un personaje a otro | *The Sixth Sense* ~3:33 |
| **Color de vestuario** | el color distinto o saturado salta antes que la forma | *Schindler's List* ~4:09 · *Once Upon a Time… in Hollywood* ~4:23 |
| **Líneas guía (leading lines)** | la arquitectura apunta al sujeto como flecha | *High Noon* ~5:01 |
| **Cuadro dentro del cuadro** | una puerta, ventana o lámpara vuelve a enmarcar al sujeto | *A.I.* ~5:42 |
| **Luz** | lo más iluminado manda | *The Parallax View* ~6:07 · *John Wick 4* ~7:38 (siluetas contra el sol) |
| **Sonido** | lo más fuerte manda; aislar un sonido mete al espectador en un detalle; un sonido fuera de cuadro hace buscar | *The Hurt Locker* ~8:34 · *All That Jazz* ~9:11 |

Ideas del narrador (parafraseadas, según Gemini): lo que está en el centro atrae primero el ojo
(0:45); si todos los personajes miran a uno, la atención del público va ahí (1:47); lo más
iluminado del cuadro atrae la mirada (6:01).

## 3. Revisa que no compitan

- Recorre el cuadro buscando **todo lo que atrae**: lo más brillante, lo más nítido, el color
  distinto, lo que se mueve, las caras, hacia dónde apuntan las líneas y las miradas. Todo eso
  tiene que señalar al mismo punto, o al siguiente de la jerarquía.
- **Error principal:** demasiados puntos brillantes o saturados; el ojo no sabe a dónde ir.
  Se usa **a propósito** solo cuando la escena quiere estrés o caos (*Punch-Drunk Love* ~9:33,
  con el sonido).
- **Error de fondo:** algo nítido o brillante atrás roba un diálogo importante adelante.
- Cuál gana cuando dos chocan no lo dice el video con una regla. Gemini sugiere que movimiento y
  foco suelen ganarle al color; tómalo como hipótesis y compruébalo en el frame.

## 4. Traducción

### Prompt para video o imagen con IA (en inglés)

Nombra el punto de atención y **qué lo hace destacar**; los modelos obedecen mejor
"X sharp, background blurred" que "focus on X".

- Foco: `shallow depth of field, the woman in the background is in sharp focus, the man in the foreground is a soft blur`
- Rack focus: `rack focus from the sheriff in the foreground to the man in the background`
- Color: `a girl in a bright red coat in a crowd dressed in grey and black, muted desaturated palette`
- Luz: `only the subject is lit by a warm spotlight, the rest of the room falls into darkness`
- Composición: `symmetrical centered composition` · `subject on the left third, negative space on the right` · `converging leading lines pointing at the subject` · `framed through a doorway`
- Movimiento: `slow push-in toward her face`
- Sonido (modelos con audio o montaje): `ambient noise drops away, only the ticking clock is heard`

### Blender

- Cámara → **Depth of Field**: Focus Object en el sujeto y F-Stop bajo (1.4–2.8) para separar.
  Rack focus = keyframes del Focus Distance o del Focus Object.
- Cámara → Viewport Display → **Composition Guides**: centro, tercios, proporción áurea.
- Luz y color con `iluminacion-cinematografica`: el sujeto debe ser lo más brillante o lo de
  color distinto. Comprueba con un render de prueba, no en el viewport.

## 5. Analizar un frame o un video

- **Frame:** míralo y llena la plantilla.
- **Video local o link de YouTube:** pásalo a Gemini con el MCP `gemini` (`ask_gemini`, archivo o
  link en `files`). Claude no ve video. Solo se manda lo que el usuario indique; lo que no se pueda
  comprobar va marcado "según Gemini".

```
Toma: <marca de tiempo o descripción>
Recorrido del ojo: 1.º <…> · 2.º <…> · ignora <…>
Qué lo hace destacar: <centro/tercios/áurea · mirada · foco · movimiento · color · líneas · marco · luz · sonido>
Qué compite y cómo se resuelve: <…>
Prompt EN: <línea lista para pegar>
```

## Referencias

- `references/donde-mirar.md`: cada técnica con lo que se ve en pantalla, los gráficos que dibuja
  el video y las citas con marca de tiempo. Léelo cuando haya que justificar una decisión de
  composición o buscar un ejemplo de película.
- Para una pieza completa, del mercado a la toma, `direccion-creativa` usa esta skill en los pasos 8 (imagen) y 9 (shot list).
