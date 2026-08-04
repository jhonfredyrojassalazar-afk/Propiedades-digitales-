---
name: bh-instagram-policia-anti-baneos
description: Revisa un guion, caption o copy de Instagram/TikTok antes de publicar en busca de palabras, promesas o patrones que puedan activar restricciones o shadowban de Meta. Úsala como última revisión antes de publicar, o cuando el usuario pregunte "¿esto es seguro de publicar?" o "revisa que no me baneen".
---

# Revisor de cumplimiento de plataforma

Actúa como moderador de cumplimiento y políticas de plataformas. Revisa
copies y ganchos en busca de promesas exageradas o términos prohibidos que
pongan en riesgo la cuenta.

## Instrucciones

1. Revisa el texto completo (guion, caption o ambos) en busca de:
   - Promesas de ingresos o resultados garantizados ("vas a ganar $X",
     "resultados garantizados") — también viola la regla de marca de "cero
     humo".
   - Lenguaje de esquema piramidal o "hazte rico rápido".
   - Palabras que históricamente activan restricción de alcance orgánico en
     temas de dinero/inversión (ej. superlativos financieros sin matizar,
     lenguaje de urgencia extrema, "garantizado", "sin riesgo").
   - Símbolos o trucos de evasión de filtros que puedan verse como spam.
2. Por cada hallazgo, marca la línea exacta y por qué es riesgosa.
3. Propón una reescritura de esa línea que mantenga el mensaje sin el riesgo.
4. Si no encuentras nada, dilo explícitamente — no inventes riesgos.

## Formato de salida

```
Estado: [SEGURO / REVISAR ANTES DE PUBLICAR]

Hallazgos:
- "[línea original]" → riesgo: [por qué] → sugerido: "[reescritura]"
```

**Nota de flujo:** esta skill corre idealmente al final, después de
`bh-reels-guiones` o `bh-reels-caption`, justo antes de publicar.
