---
name: generador-ideas-evergreen
description: >
  Analiza contenido de referencia (videos de YouTube, Reels de Instagram subidos como
  archivo, texto, o notebooks de NotebookLM) que ya funcionó bien, extrae por qué
  funcionó, y lo adapta a la marca de Jhon Rojas (@SoyJhonRojasS) — Diseñador de
  Patrimonios Digitales, Método Evergreen. Activa este skill SIEMPRE que Jhon comparta
  un video/Reel/texto de referencia y pida "algo parecido mío", "adapta esto a mi
  contenido", o pida un guion nuevo basado en algo que vio funcionar. Nunca copia
  contenido literal — extrae el patrón estructural, no las palabras.
---

# GENERADOR DE IDEAS — Skill de Jhon Rojas

Tu trabajo tiene 3 fases, siempre en este orden: **analizar → extraer el patrón →
adaptar a la marca de Jhon.** Nunca te saltes la fase 2 para ir directo de referencia
a guion — el patrón es lo que se reutiliza, no el contenido original.

## Fase 1 — Analizar la referencia

Según el tipo de referencia que Jhon comparta:
- **YouTube (link):** usa la herramienta de análisis de video escena por escena de
  Higgsfield. Espera a que termine el procesamiento antes de continuar.
- **Instagram/Reel (archivo subido):** analiza el video directamente como archivo.
- **Texto:** léelo tal cual, identifica su estructura interna.
- **Carpeta de NotebookLM:** consulta el contenido relevante que Jhon señale.

## Fase 2 — Extraer el patrón (nunca el contenido literal)

Para cada referencia, documenta específicamente:

1. **Tipo de hook** — ¿pregunta directa? ¿dato/cifra? ¿tensión/contradicción?
   ¿resultado mostrado primero? Nombra el mecanismo, no copies la frase.
2. **Estructura del desarrollo** — ¿lista? ¿narrativa con giro? ¿problema→solución?
   ¿bucles abiertos? ¿cuántos bloques/beats tiene?
3. **Tipo de CTA** — ¿palabra clave en comentarios? ¿link directo? ¿pregunta abierta
   para generar comentarios? ¿en qué momento del video/pieza aparece?
4. **Por qué funcionó** — hipótesis concreta: ¿retención alta por ritmo?
   ¿identificación emocional? ¿autoridad demostrada con prueba? ¿curiosidad sin
   resolver hasta el final?

Guarda esto en `/conocimiento/patrones-adaptados.md`, organizado por referencia, con
formato: Fuente → Tipo de hook → Estructura → Tipo de CTA → Por qué funcionó.

**Regla de derechos de autor:** nunca reproduzcas frases textuales de la referencia
en la documentación ni en el guion final — describe el mecanismo con tus propias
palabras. Esto no es opcional.

## Fase 3 — Adaptar a la marca de Jhon

Con el patrón ya documentado, adapta al:
- **Avatar:** alguien que ya construyó herramientas con IA, no ha vendido todavía
- **Voz:** autoridad en construcción, frases cortas, sin promesas de resultado ajeno,
  sin emojis
- **Nicho:** construcción de propiedades digitales con IA, tramo cero-ventas-a-primera-venta
- **Tema/pilar del día** correspondiente en el calendario (Dolor/Valor/Autoridad/
  Objeción/Venta suave/Humanización)

## Salida esperada — formato de entrega

Siempre entrega el guion adaptado en esta estructura, listo para grabar o para pasar
al avatar clonado (Higgsfield):

```
HOOK (0-Xs): [texto exacto a decir o mostrar]
CUERPO: [desarrollo, en bloques numerados si aplica]
CTA: [palabra clave + beneficio, según el pilar del día]

Nota de adaptación: [en 1-2 líneas, qué patrón de la referencia se usó y por qué 
encaja con el tema/pilar de hoy]
```

## Para múltiples referencias — comparación

Si Jhon comparte 3-5 referencias a la vez, además del análisis individual, entrega un
resumen comparativo: qué tienen en común (posible principio universal a adoptar) y
qué es distinto entre ellas (para no mezclar mecanismos incompatibles en un mismo
guion).

## Relación con otros skills

Este skill alimenta a `youtube-creador-evergreen` (para guiones de video),
`carrusel-evergreen` (para estructura de carrusel) e `historias-evergreen` (para
Stories) — entrega el guion/estructura adaptada, y esos skills ejecutan el formato
específico. No decide estrategia de fondo (tema del día, pilar) — eso lo hereda de
`estrategia-evergreen` y el calendario.
