# PLAN DE EJECUCIÓN — CLAUDE CODE (con control de gasto)
Jhon Rojas — @SoyJhonRojasS — Método Evergreen

## Principio rector — nunca se gasta sin verificar antes

Ninguna generación en Higgsfield se ejecuta directamente. Siempre pasa por esta
secuencia de 4 pasos, en este orden, sin excepción:

1. **Verificar saldo** — `higgsfield:balance` antes de cualquier tarea que use créditos.
2. **Cotizar antes de generar** — usar `get_cost: true` en la llamada específica
   (imagen, video o audio) para saber el costo exacto ANTES de ejecutarla de verdad.
3. **Comparar contra el presupuesto semanal** — ver tabla de topes abajo. Si la
   cotización lo supera, Code se detiene y pregunta, nunca decide solo.
4. **Ejecutar y registrar** — solo después de la confirmación, se genera de verdad,
   y el gasto se anota en el ledger (ver más abajo).

## Presupuesto semanal — con tus 575 créditos actuales

| Concepto | Tope semanal sugerido | Razonamiento |
|---|---|---|
| Video ancla (1/semana) | 60-90 créditos | Prioriza calidad — es tu pieza más importante |
| Shorts derivados (2-3/semana) | 30-45 créditos | Calidad estándar (720p), no 4K |
| Fondos de carrusel (7/semana) | 20-30 créditos | Nano Banana Pro, resolución estándar |
| **Total semanal** | **~110-165 créditos** | Con 575 créditos, cubre 3-4 semanas completas con margen |

Code debe avisar si el consumo acumulado del mes supera el 80% de este presupuesto,
para que decidas si compras un top-up o esperas al siguiente ciclo.

## Pipeline diario — lo que Code ejecuta paso a paso

1. **Lee contexto** — `CLAUDE.md`, `AVATAR.md`, y el calendario del día correspondiente.
2. **Identifica qué se produce hoy** — carrusel, Short, video ancla, o Story, según
   el calendario.
3. **Redacta el copy/guion primero, en texto** — esto no cuesta créditos de Higgsfield
   (es generación de texto normal de Claude). Nunca se genera nada visual antes de
   tener el texto final aprobado.
4. **Si la pieza necesita imagen o video:**
   - Revisa si hay ventana de generación gratuita/ilimitada activa (`models_explore`
     con `unlim: true`) — si existe y aplica, se usa primero, sin gastar créditos.
   - Si no hay ilimitado disponible, cotiza con `get_cost: true`.
   - Si la cotización cabe en el presupuesto del día, genera. Si no, se detiene y
     pregunta antes de continuar.
5. **Ensambla la pieza final** — igual que venimos haciendo en el chat: texto +
   elementos visuales sobre el sistema de marca fijo (paleta, tipografía).
6. **Exporta el archivo final** (PNG retina, o video en el formato de la plataforma).
7. **Registra en el ledger** — qué se generó, cuántos créditos costó, saldo restante.
8. **Documenta en Notion** — guion, assets usados, y el recurso final, en la página
   correspondiente del día.

## Ledger de créditos — registro obligatorio

Cada vez que Code gasta créditos reales, agrega una fila a una tabla (en Notion o en
un archivo local `ledger-creditos.md`) con este formato:

| Fecha | Pieza | Modelo usado | Créditos gastados | Saldo restante |
|---|---|---|---|---|

Esto te da trazabilidad completa — en cualquier momento puedes ver exactamente en qué
se fue cada crédito, sin sorpresas al final del mes.

## Reglas de aprobación — cuándo Code SIEMPRE debe preguntar antes de actuar

- Cualquier generación individual cotizada en más de **30 créditos**.
- Cualquier tarea que genere **más de 3 piezas visuales en una sola ejecución**
  (para evitar que un batch se dispare sin supervisión).
- Cualquier vez que el saldo total caiga por debajo de **50 créditos** — alerta
  temprana antes de quedarte sin margen.
- Cualquier uso de un modelo premium (Veo 3, Sora 2) en vez de los modelos estándar
  ya validados (Seedance, Kling, Nano Banana) — estos son mucho más caros por pieza.

## Checklist antes de correr el pipeline completo por primera vez

- [ ] `CLAUDE.md` y `AVATAR.md` creados y actualizados en la carpeta del proyecto
- [ ] Conector de Higgsfield autenticado dentro de Claude Code (no solo aquí en el chat)
- [ ] Conector de Notion autenticado dentro de Claude Code
- [ ] Presupuesto semanal de la tabla de arriba confirmado o ajustado por ti
- [ ] Primera corrida de prueba: pide UNA sola pieza (no el pipeline completo) para
      confirmar que el control de gasto funciona como se espera antes de automatizar
      la semana completa
