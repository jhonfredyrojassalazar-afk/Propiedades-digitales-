# WORKFLOW — Edición Completa de Video (Fredy + voz clonada)
Jhon Rojas — @SoyJhonRojasS — Método Evergreen

Pipeline completo para producir un video terminado (YouTube o Instagram) a partir de
un guion ya escrito, usando el avatar entrenado "Fredy" y la voz clonada de Jhon,
con control de gasto integrado en cada paso.

## Principio rector

Se cotiza **cada paso individual** antes de generar nada, se suma el **costo total
estimado del video completo**, y se presenta ese total a Jhon para aprobación —
antes de gastar el primer crédito. Nunca se generan clips "a ver cuánto sale" y se
descubre el costo al final. Esto extiende el principio rector de
`plan-ejecucion.md` ("nunca se gasta sin verificar antes") a nivel de pieza
completa, no solo de generación individual.

## Entradas requeridas

1. **Guion final**, dividido en bloques: Hook, Cuerpo (uno o más sub-bloques),
   CTA — entregado por `youtube-creador-evergreen` (formato largo) o por
   `carrusel-evergreen`/`generador-ideas-evergreen` adaptado a Reel (formato corto).
2. **Formato**: `largo` (YouTube, 16:9, 8-15 min) o `corto` (Instagram/Shorts, 9:16,
   15-90s). El formato determina qué skill de edición aplica al final (paso 4).

## Pipeline — 6 pasos

### Paso 1 — Recibir el guion y confirmar bloques

Recibe el guion ya dividido en Hook / Cuerpo / CTA. Si llega sin dividir, sepáralo
tú mismo respetando la estructura de 7 bloques de `estrategia-evergreen` (video
largo) o la estructura corta de `editor-instagram-evergreen`. Nunca inventes
contenido de guion — si falta un bloque, pregunta antes de continuar.

### Paso 2 — Generar cada clip: Fredy + voz clonada

Por cada bloque del guion:

1. Cotiza el clip con `generate_video` (`get_cost: true`) usando el modelo de
   avatar hablante correspondiente (identidad de Fredy vía `soul_id`, voz clonada
   vía `voice_id` de `list_voices`/`create_voice`). Si el caso lo amerita, usa
   `get_workflow_instructions` para cargar el workflow de video "hablado"
   (explainer/UGC/podcast) antes de generar, según indique el catálogo.
2. Guarda la cotización de cada bloque — no generes todavía (ver "Aprobación
   consolidada" abajo).
3. Verifica saldo con `higgsfield:balance` antes de la primera cotización de la
   sesión, igual que indica el plan de ejecución.

### Paso 3 — Ensamblar los clips en orden, con subtítulos automáticos

Une los clips generados, en el orden del guion, usando el ensamblador de
Higgsfield: el script del workflow bundle correspondiente
(`get_workflow_bundle_file`), ejecutado en la terminal en la nube
(`sandbox_exec`, que ya trae `ffmpeg`/`ffprobe` y `faster-whisper` preinstalados
para generar y quemar subtítulos automáticos). Fuente de subtítulos: la
tipografía del sistema de marca (Big Shoulders/Anton para énfasis, Inter/
Instrument Sans para el cuerpo del subtítulo), nunca una fuente genérica del
sandbox por defecto.

### Paso 4 — Revisión de ritmo según formato

- **Formato largo (YouTube):** aplica el checklist de `editor-youtube-evergreen`
  — cambio de estímulo cada 30-45s, estructura de corte de 7 bloques, capítulos/
  timestamps, consistencia con la miniatura.
- **Formato corto (Instagram):** aplica el checklist de `editor-instagram-evergreen`
  — corte cada 1-2s, hook resuelto en los primeros 1-3s, zonas seguras, cierre
  corto.

Si el ensamblado no cumple el checklist correspondiente, ajusta antes de pasar al
paso 5 — no entregues una pieza que no pasa su propio checklist de edición.

### Paso 5 — Pulido final "de autor" (opcional, solo si se pide)

Cuando Jhon pida algo más específico de marca — animaciones puntuales,
transiciones con estilo propio, música de fondo con ducking, b-roll insertado —
usa `sandbox_exec` con FFmpeg directamente para ese ajuste fino sobre el
ensamblado del paso 3. Este paso no es obligatorio en cada video; solo se activa
cuando el resultado del ensamblador automático no es suficiente.

### Paso 6 — Registrar el gasto en el ledger

Al cerrar la pieza, agrega una fila por cada generación real (no por cotización)
al ledger de créditos (`ledger-creditos.md` o Notion, según `plan-ejecucion.md`):
fecha, pieza, modelo usado, créditos gastados, saldo restante. Suma también una
fila de "Total video" con el costo agregado de todos los clips + ensamblaje, para
poder comparar después contra la cotización que se aprobó al inicio.

## Aprobación consolidada — antes de generar el primer clip real

1. Cotiza los clips de **todos** los bloques del guion (paso 2.1) sin generar
   nada.
2. Suma el costo total estimado del video completo (todos los clips + cualquier
   costo de ensamblaje/pulido que tenga créditos asociados).
3. Compara ese total contra el presupuesto semanal de `plan-ejecucion.md` y
   contra la regla de aprobación de más de 30 créditos por generación individual
   — si algún clip o el total lo supera, Code se detiene y pregunta, nunca decide
   solo.
4. Presenta a Jhon una tabla: bloque → créditos estimados, más el total. Solo
   después de la aprobación explícita se generan los clips de verdad (paso 2.2 en
   adelante).

## Relación con otros skills

Recibe el guion de `youtube-creador-evergreen` (formato largo) o de
`carrusel-evergreen`/`generador-ideas-evergreen` (formato corto). Aplica las
reglas de corte de `editor-youtube-evergreen` o `editor-instagram-evergreen`
según el formato. Sigue el principio de control de gasto y el formato de ledger
de `plan-ejecucion.md`, sin redefinirlos aquí.
