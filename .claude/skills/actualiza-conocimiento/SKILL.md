---
name: actualiza-conocimiento
description: Sincroniza el conocimiento diario entre tu PC y GitHub (git status, fetch, push/pull) y opcionalmente refresca contenido desde NotebookLM si el PC está conectado. Invócala manualmente cada mañana con "actualiza el conocimiento" o "/actualiza-conocimiento".
disable-model-invocation: true
allowed-tools: Bash(git status *) Bash(git fetch *) Bash(git add *) Bash(git commit *) Bash(git push *) Bash(git pull *) Bash(git diff *) Bash(git log *) Read
---

# Sincronización diaria de conocimiento — PC ↔ GitHub

Ejecuta esta tarea de corrido, sin pedir confirmación paso a paso. Solo te
detienes y alertas al usuario en dos casos: un conflicto real de git, o un
error que impida completar un paso. En todo lo demás, ejecuta directo.

## Paso 0 — NotebookLM (solo si el usuario lo pidió explícitamente hoy)

Si el usuario pidió actualizar conocimiento desde NotebookLM, invoca la
skill `notebooklm/` primero. Esa skill puede requerir su propia aprobación
de navegador — eso es normal y no lo puedes saltar, no está cubierto por
`allowed-tools` de esta skill. Si el usuario no lo pidió, omite este paso y
trabaja solo con lo que ya existe.

## Paso 1 — Diagnóstico (siempre, sin preguntar)

En cada repo relevante (`jhon-rojas-sistema` y, si existe, el repo separado
del resto de `Propiedades-digitales`):

```
git status --short
git fetch
git log HEAD..origin/main --oneline
git log origin/main..HEAD --oneline
```

Con esto identificas:
- Qué archivos locales no están subidos.
- Qué hay en GitHub que no está bajado localmente.
- Si hay commits en ambos lados que diverjan (posible conflicto).

## Paso 2 — Verificación de seguridad (siempre, antes de subir nada)

Confirma que ninguno de estos patrones aparece en `git status --short`:
- `.venv/`
- `data/browser_state/`
- Cualquier archivo dentro de una carpeta llamada `notebooklm` que no sea
  `SKILL.md` o texto de referencia.

Si algo de eso aparece como "por subir", detente y alerta — no lo subas
bajo ninguna circunstancia, aunque el resto del flujo esté limpio.

## Paso 3 — Sin conflictos: sincroniza directo

Si no hay divergencia real entre local y remoto:
- `git add` de los archivos nuevos/modificados legítimos.
- `git commit` con un mensaje descriptivo automático (ej. "Sync diario —
  [fecha] — [resumen corto de qué cambió]").
- `git push`.
- `git pull` para traer lo que faltaba localmente.

## Paso 4 — Con conflictos: NO decidas tú

Si detectas que el mismo archivo cambió de forma distinta en local y en
remoto, no selecciones versión automáticamente. Detente y muéstrale al
usuario exactamente qué archivo(s) y qué diferencia, y espera su decisión.

## Paso 5 — Reporte final (una sola línea, sin relleno)

Termina siempre con una de estas dos:
- ✅ Hecho — PC y GitHub sincronizados. [resumen de 1 línea de qué se subió/bajó]
- ⚠️ Hay un problema: [descripción concreta y qué necesitas del usuario]

No expliques el proceso paso a paso al usuario a menos que haya un problema
— el reporte final debe ser corto.
