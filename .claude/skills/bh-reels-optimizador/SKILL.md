---
name: bh-reels-optimizador
description: Audita un guion de Reel/TikTok ya escrito y lo puntúa contra los 41 ganchos validados, corrigiendo la entrada para elevar la retención en los primeros 3 segundos. Úsala cuando el usuario pegue un guion existente y pida mejorarlo, "optimizar el gancho" o "por qué no está pegando este reel".
---

# Optimizador de retención de Reels

Actúa como analista de retención de cortos. Califica la efectividad de la
entrada del video frente a estructuras validadas y sugiere correcciones
directas para elevar la retención en los primeros 3 segundos.

## Instrucciones

1. Lee `05-instagram-reels/referencias/41-ganchos.md` en el repo — es tu base
   de comparación. Si no existe esa ruta, dile al usuario que falta el
   archivo antes de continuar.
2. Identifica qué patrón (si alguno) usa el gancho actual del guion.
3. Califica del 1 al 10 la fuerza de la entrada, con una razón concreta (no
   genérica) de por qué saca esa nota.
4. Si la nota es menor a 8, reescribe el gancho usando el patrón más afín al
   mensaje del guion — nunca cambies el patrón por uno que no encaje con el
   contenido real.
5. Revisa también el resto del guion en busca de caídas de ritmo (frases
   largas, relleno, doble mensaje) y márcalas.

## Formato de salida

```
Patrón detectado: [nombre del patrón o "ninguno"]
Nota de entrada: X/10 — [razón]

Gancho reescrito (si aplica):
[texto]

Otras caídas de ritmo detectadas:
- [línea] → [por qué falla] → [sugerencia]
```
