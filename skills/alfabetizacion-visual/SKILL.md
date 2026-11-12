---
name: alfabetizacion-visual
description: Lee y construye imágenes con método, el cómo (técnica) y el porqué (historia), el encuadre como base, composición en tres capas de profundidad (primer término, término medio, fondo) frente al plano de sujeto, y la luz al servicio de la composición, y lo traduce a un prompt en inglés para video o imagen con IA, a una escena de Blender o a notas de dirección. Úsala SIEMPRE que el usuario quiera entender por qué una imagen "se ve de cine" o "se ve plana", analizar un plano o una película, componer un frame, un anuncio o una escena de Blender con profundidad, decidir cuántos close-ups usar, o cuando aparezcan palabras como alfabetización visual, visual literacy, lenguaje visual, profundidad, capas, foreground, background, "se ve plano", "se ve barato" o "más cinematográfico", aunque no lo diga así.
---

# Alfabetización visual

**Parcial:** sale de los primeros 6 minutos (de 17:58) de «Understanding Visual Literacy» de
Avery Dohrmann.

Alfabetización visual es saber desarmar el lenguaje visual de una película. Tiene dos fases:

- **El cómo:** la técnica. Entender cómo está hecho el pastel: profundidad, composición, luz.
- **El porqué:** por qué esta decisión, aquí. Es la fase que nunca se termina de dominar, y la
  que hace que una imagen pegue en lugar de solo verse bonita.

Toda decisión técnica tiene que poder contestar un porqué de historia. Si no lo contesta, sobra.

## 1. El orden de construcción: el pastel antes que el betún

> "Everything comes from the frame… They are the frosting." (≈02:33, según Gemini)

1. **Encuadre:** qué bordes cortan la escena y qué cae dentro.
2. **Composición en capas** (abajo).
3. **Luz** al servicio de esas capas.
4. **Color, vestuario y textura:** el betún.

Si el encuadre no tiene intención, ni la luz ni la corrección de color lo rescatan. Es el
error que el video muestra en pantalla como *Flat :(*: un actor contra una pared plana.

## 2. Composición = tres capas de profundidad

| Capa | Qué va | Para qué |
|---|---|---|
| **Primer término (F)** | un elemento muy cerca de cámara: reja, marco, hombro, objeto | mete al espectador en el espacio y da escala |
| **Término medio (M)** | el sujeto y la acción | lo que importa |
| **Fondo (B)** | entorno con fuga o actividad | contexto y profundidad |

Ejemplo del video (~03:01): mirada a través de los barrotes de una ventana. F = la reja oscura,
M = el marco de la ventana, B = la cocina iluminada donde discuten tres personajes.

### Plano de sujeto: la salsa picante

El **plano de sujeto** (close-up, medio cerrado, detalle) aísla a alguien o algo y deja el
entorno fuera. Pega fuerte, pero:

> Las composiciones son la comida y los planos de sujeto son la salsa picante. No se hace una
> comida solo con salsa, pero sin ella todo sabe insípido. (≈03:30, parafraseado)

Regla: la base de una secuencia son composiciones con capas, y los planos de sujeto se usan de
condimento, en los momentos de énfasis. Una secuencia que es puro close-up cansa y no ubica.

## 3. La luz es función de la composición

> "Lighting is, and always will be, a function of composition." (≈03:51, según Gemini)

- La composición es lo que hace cinematográfica una imagen; la luz no. Primero se pone la cámara
  y a los sujetos para que haya volumen y fuga; después se ilumina.
- Luz por capa (≈05:10):
  - **F y B:** relleno, o su **ausencia**, para dar forma a la profundidad.
  - **M:** la **clave** define al sujeto.
  - **Contraluz o recorte** (backlight, rim) para despegar al sujeto del fondo.
- **La luz no se tiene que notar:** La luz apoya la imagen, no se luce. Si se ve la luz antes que la historia, se rompe la ilusión.

El detalle de clave y relleno (lado inteligente, ratio, motivación) está en
`iluminacion-cinematografica`.

## 4. Cómo leer una imagen (el método del video)

1. **Encuadre:** ¿es una composición con capas o un plano de sujeto?
2. **Capas:** ¿qué hay en F, en M y en B?
3. **Luz por capa:** ¿dónde están la clave, el relleno (o su ausencia) y el recorte? ¿La luz
   apoya la profundidad o maquilla un encuadre plano?
4. **El porqué:** ¿por qué aquí, por qué esta composición, por qué esta forma de hacer
   profundidad, por qué este lente, por qué los actores están puestos así?

Plantilla:

```
Toma: <marca de tiempo o descripción>
Tipo: composición en capas | plano de sujeto
F: <…> · M: <…> · B: <…>
Luz: F/B <relleno o ausencia> · M <clave> · recorte <sí/no>
Porqué: <qué decisión de historia justifica cada elección>
Prompt EN: <línea lista para pegar>
```

## 5. Traducción

### Prompt para video o imagen con IA (en inglés)

Describe las tres capas en orden, de cerca a lejos. Los modelos aplanan la imagen si no se lo
pides.

- `layered composition: dark window bars in the foreground, a window frame in the midground, a warmly lit kitchen with three people arguing in the background`
- `deep staging, out-of-focus shoulder in the foreground, subject in the midground, busy street receding in the background`
- Luz por capa: `key light on the subject in the midground, foreground and background left dark, thin rim light separating the subject from the background`
- Plano de sujeto, cuando toque: `tight close-up, background fully out of focus`

### Blender

Acomoda los objetos en tres distancias a la cámara y verifica en la vista de cámara que se lean
las tres. Ilumina por capa: clave sobre el sujeto (M), poca o nada de luz en F, recorte detrás
del sujeto, y el fondo con su propia fuente motivada. Prueba con un render, no con el viewport.

## Límites

- Cubre solo los primeros minutos del video; el resto no está analizado.
- Los ejemplos de película vienen de un análisis automático de video y pueden estar mal
  atribuidos. Los nombres de película van «según Gemini»: compruébalos antes de citarlos.

## Referencias

- Se combina con `dirigir-la-mirada` (a dónde va el ojo), `iluminacion-cinematografica` (cómo
  se hace cada luz) y `angulos-de-camara` (desde dónde).
- Para una pieza completa, del mercado a la toma, `direccion-creativa` usa esta skill en los pasos 8 (imagen) y 9 (shot list).
