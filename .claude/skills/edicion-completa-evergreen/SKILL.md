---
name: edicion-completa-evergreen
description: >
  Ejecuta el pipeline completo de producción de video (documentado en
  `workflows/edicion-completa.md`) para la marca de Jhon Rojas (@SoyJhonRojasS):
  genera cada bloque del guion con el avatar entrenado "Fredy" + voz clonada,
  ensambla los clips con subtítulos automáticos, aplica las reglas de
  `editor-youtube-evergreen` o `editor-instagram-evergreen` según el formato, y
  registra el gasto en el ledger. Activa este skill SIEMPRE que Jhon pida
  "produce el video completo", "genera el video con Fredy", o entregue un guion
  ya terminado (Hook/Cuerpo/CTA) pidiendo el video final, no solo el guion. Este
  es el "script" que corre el flujo end-to-end — pide únicamente el guion y el
  formato (largo/corto) como input.
---

# EDICIÓN COMPLETA EVERGREEN — Skill de Jhon Rojas

Este skill es el punto de entrada único del pipeline de producción de video.
Recibe **guion + formato** y ejecuta los 6 pasos de `workflows/edicion-completa.md`
sin que Jhon tenga que invocar cada herramienta por separado.

## Inputs obligatorios (pedir si faltan, nunca asumir)

1. **Guion**, dividido en Hook / Cuerpo (1+ sub-bloques) / CTA. Si llega sin
   dividir, divídelo tú mismo antes de continuar (ver Paso 1 de
   `workflows/edicion-completa.md`).
2. **Formato**: `largo` (YouTube) o `corto` (Instagram/Shorts). Si Jhon no lo
   especifica, pregúntalo — el formato determina aspect ratio, duración por
   clip, y qué skill de edición aplica al final.

No pidas nada más — todo lo demás (soul_id de Fredy, voice_id clonado, modelo,
presupuesto) se resuelve dentro del propio flujo.

## Ejecución — sigue exactamente `workflows/edicion-completa.md`

### Fase A — Cotización consolidada (nunca se salta)

1. Verifica saldo (`higgsfield:balance`).
2. Resuelve identidad y voz: `show_characters(action:'list', status:'ready')`
   para el `soul_id` de "Fredy", `list_voices` para el `voice_id` clonado de
   Jhon (si hay más de una voz guardada, confirma cuál usar).
3. Por cada bloque del guion (Hook, cada sub-bloque de Cuerpo, CTA), cotiza el
   clip con `generate_video` (`get_cost: true`), usando aspect ratio y duración
   según el formato:
   - `largo`: 16:9, clips más largos, tono de retención sostenida.
   - `corto`: 9:16, clips cortos, ritmo de impacto inmediato.
4. Suma el costo total estimado (todos los clips). Si el ensamblaje o el pulido
   previsto también tiene costo en créditos, cotízalo también e inclúyelo.
5. Presenta la tabla de cotización completa a Jhon:

   | Bloque | Modelo | Créditos estimados |
   |---|---|---|
   | Hook | ... | ... |
   | Cuerpo — bloque N | ... | ... |
   | CTA | ... | ... |
   | **Total estimado** | | **...** |

6. Compara el total y cada línea contra `plan-ejecucion.md` (tope de 30 créditos
   por generación individual, presupuesto semanal, alerta bajo 50 créditos de
   saldo). Si algo lo supera, dilo explícitamente en la tabla y espera
   aprobación — nunca generes en automático solo porque la cotización terminó.
7. **Detente y espera aprobación explícita de Jhon antes de generar el primer
   clip real.** Esto es una puerta de aprobación, no una sugerencia.

### Fase B — Generación (solo tras aprobación)

1. Genera cada clip real (`generate_video`, sin `get_cost`) en el orden del
   guion, con Fredy + voz clonada.
2. Ensambla los clips en orden con el workflow bundle de Higgsfield
   (`get_workflow_instructions` → `get_workflow_bundle_file` si aplica) vía
   `sandbox_exec`, con subtítulos automáticos quemados usando la tipografía de
   marca.
3. Aplica el checklist de edición según formato:
   - `largo` → checklist de `editor-youtube-evergreen`.
   - `corto` → checklist de `editor-instagram-evergreen`.
   Si algo no pasa el checklist, ajusta antes de continuar.
4. Si Jhon pidió pulido "de autor" (transiciones, música con ducking, b-roll),
   aplícalo ahora con `sandbox_exec` + FFmpeg directamente sobre el ensamblado.
5. Entrega el video final como propuesta — nunca como publicado. Espera
   aprobación de Jhon antes de considerar la pieza lista para subir (mismo
   principio que `carrusel-evergreen`: Code propone, Jhon aprueba).

### Fase C — Registro

1. Agrega una fila al ledger de créditos por cada generación real (fecha, pieza,
   modelo, créditos gastados, saldo restante).
2. Agrega una fila de "Total video" con el costo agregado real, y compárala
   contra el total estimado en la Fase A — si hay una desviación importante,
   avísale a Jhon (esto retroalimenta cotizaciones futuras).

## Reglas que hereda y nunca redefine

- El control de gasto (verificar → cotizar → comparar presupuesto → ejecutar y
  registrar) es el de `plan-ejecucion.md` — este skill no inventa un flujo de
  aprobación distinto, solo lo aplica a nivel de video completo.
- El ritmo de corte y la estructura de edición son los de
  `editor-youtube-evergreen`/`editor-instagram-evergreen` — este skill no
  redefine esas reglas, solo decide cuál aplica según el formato.
- El guion en sí no se redacta aquí — llega ya terminado desde
  `youtube-creador-evergreen`, `carrusel-evergreen` o `generador-ideas-evergreen`.

## Relación con otros skills

Consume: guion de `youtube-creador-evergreen`/`carrusel-evergreen`/
`generador-ideas-evergreen`. Aplica: checklist de `editor-youtube-evergreen` o
`editor-instagram-evergreen`. Sigue el control de gasto de `plan-ejecucion.md`.
No compite con ninguno de ellos — es la orquestación que los conecta en un solo
flujo de principio a fin.
