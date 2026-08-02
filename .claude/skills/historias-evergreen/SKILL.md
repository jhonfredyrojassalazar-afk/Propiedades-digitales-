---
name: historias-evergreen
description: >
  Especialista en Historias (Stories) de Instagram/Facebook para la marca de Jhon Rojas
  (@SoyJhonRojasS) — Diseñador de Patrimonios Digitales, Método Evergreen. Activa este
  skill SIEMPRE que se trabaje en secuencias diarias de historias: combinar la foto
  personal de Jhon con escenarios/fondos, definir el texto específico de cada historia,
  o diseñar el arco de una tanda diaria. No reemplaza a `carrusel-evergreen` (feed) ni a
  `youtube-creador-evergreen` — las historias son el canal de contacto diario de más baja
  fricción, pensado para frecuencia, no para profundidad.
---

# HISTORIAS EVERGREEN — Skill de Jhon Rojas

Las historias son el punto de contacto más frecuente y de menor fricción del embudo —
existen para acumular puntos de contacto (regla 7-11-4) y sostener cercanía diaria,
no para enseñar en profundidad (eso vive en el carrusel y en YouTube).

## Especificaciones técnicas fijas

- Formato 1080×1920 (9:16), siempre vertical.
- **Zonas seguras:** nunca colocar texto o elementos críticos en los primeros ~250px
  superiores (los cubre el header de usuario/reloj) ni en los últimos ~250px
  inferiores (los cubre la barra de respuesta/sticker de reacción).
- Texto principal por historia: máximo 1-2 líneas cortas — una historia comunica una
  sola idea, nunca un párrafo.
- Paleta: negro `#0A0A0A` + acento variable del día (el mismo color extraído de la
  portada del carrusel de ese día — coherencia total entre feed e historias).
- Tipografía: la misma familia de marca (Big Shoulders/Anton para texto de impacto,
  Instrument Sans para texto de apoyo).

## Flujo de trabajo (foto + escenario → historia)

1. Jhon aporta: una foto personal (rostro/plano medio) y uno o más escenarios/fondos.
2. Claude compone: ubica la foto personal respetando las zonas seguras, aplica
   tratamiento de color coherente con el acento del día (duotono o ajuste de
   temperatura si el escenario no combina de forma natural), y superpone el texto
   específico de esa historia según su rol en la secuencia (ver abajo).
3. Cada historia de la tanda diaria lleva un texto distinto — nunca se repite copy
   entre historias del mismo día, cada una avanza la secuencia.

## Clasificación por función — cada historia cumple UN objetivo, nunca varios a la vez

Antes de escribir cualquier historia, decide a cuál de estas 4 funciones pertenece —
esto determina su tono, su CTA (si tiene) y a qué Destacado se archiva:

| Función | Objetivo | Tono | Ejemplo de contenido |
|---|---|---|---|
| **Tráfico** | Captar audiencia nueva, alcance amplio | Curiosidad, gancho fuerte | Fragmento del carrusel/video del día, dato sorprendente |
| **Conexión** | Cercanía, humanización | Personal, sin venta | Detrás de cámara, proceso real, pregunta abierta |
| **Posicionamiento** | Autoridad, prueba | Seguro, con evidencia | Resultado mostrado, opinión con criterio, cifra real |
| **Ventas** | Conversión directa | Directo, CTA claro | Oferta, palabra clave, link, urgencia/escasez real |

Una tanda diaria de 4-6 historias normalmente mezcla 2-3 funciones distintas (ej.
tráfico al abrir, conexión o posicionamiento en medio, ventas al cierre) — nunca
fuerces las 4 en un solo día si no tiene sentido con el pilar correspondiente.

## Estructura diaria (secuencia de 4-6 historias, según el pilar del día)

Mismo pilar del carrusel del día — las historias son el "detrás de cámara" o el
recordatorio de contacto de ese mismo tema, no un tema distinto.

| # | Rol de la historia | Función | Texto tipo |
|---|---|---|---|
| 1 | **Gancho del día** | Anuncia el tema/dolor del día en una frase, genera curiosidad | "Hoy te cuento por qué [tema]" |
| 2 | **Fragmento de valor** | Un dato o idea suelta del carrusel/video del día, adelantado | Frase corta con la idea central |
| 3 | **Detrás de cámara** | Proceso real, sin pulir — refuerza cercanía y autenticidad | Mínimo texto, la imagen manda |
| 4 | **Interactiva** | Sticker de pregunta, encuesta o quiz relacionado al tema del día | Pregunta directa al avatar |
| 5 | **Puente al carrusel/video** | Aviso explícito de que el contenido completo ya está publicado | "Ya está el carrusel/video completo — desliza" + sticker de link |
| 6 (opcional, días de venta) | **CTA directo** | Refuerzo de la palabra clave del cierre del carrusel | "Comenta [PALABRA CLAVE]" |

### Uso de stickers interactivos (obligatorio, no decorativo)

- **Encuesta (poll):** los días de VALOR/AUTORIDAD — pregunta que valida un dolor o
  preferencia del avatar, alimenta datos reales para futuros carruseles.
- **Caja de preguntas:** los días de HUMANIZACIÓN — abre espacio real de conversación,
  motor directo de la relación de confianza (mismo objetivo que las secuencias de
  YouTube: confianza, autoridad con evidencia, comunidad).
- **Cuenta regresiva / link:** solo en días de VENTA SUAVE u OBJECIÓN, apuntando al
  recurso del cierre del carrusel del día.
- Nunca usar un sticker interactivo sin propósito — cada uno debe alimentar dato,
  conversación o conversión, no rellenar espacio.

## Embudo de nutrición ENTRE días (macro-secuencia, no solo dentro de una tanda)

La estructura diaria de arriba resuelve una tanda de 24 horas. Esta sección resuelve
la cadena entre días — el equivalente en historias a las playlists de YouTube y a los
Destacados del carrusel.

### Destacados como "playlists" fijas (comparten estructura con carrusel-evergreen)

Toda historia que valga la pena conservar más de 24 horas se archiva en el mismo
mapa de 4 categorías que usa `carrusel-evergreen` — así el perfil entero (feed +
historias) queda organizado bajo una sola arquitectura, no dos separadas:

| Destacado | Mindset de entrada | Tipo de historia que agrupa |
|---|---|---|
| **Empieza aquí** | Curioso/escéptico | Ganchos y fragmentos de valor de días de Alcance |
| **Cómo se hace** | Ya cree, no sabe el cómo | Detrás de cámara, proceso real |
| **Ya vi resultados** | Listo para comprar | CTAs directos, historias de días de Venta/Objeción |
| **Comunidad Evergreen** | Cliente o seguidor recurrente | Interactivas, preguntas, humanización |

### Encadenamiento diario (obligatorio)

- La historia 1 (gancho del día) debe, cuando exista continuidad temática, referenciar
  la tanda de ayer ("Ayer te pregunté X, hoy te cuento qué aprendí" / "Sigue de donde
  quedamos ayer"). Esto construye sesiones de varios días encadenadas, igual que un
  video de YouTube empuja a su secuela.
- Cuando una serie de historias se extiende más de un día (ej. un lanzamiento), numera
  visualmente ("Día 1 de 3...") para que quien llega a mitad de camino entienda que
  hay contexto previo disponible en Destacados.

### Sprint y consumo en sesión larga

- Ante un lanzamiento o tema nuevo, diseña la tanda como una mini-serie de 2-3 días
  encadenados antes de cambiar de tema — igual que el sprint mínimo de YouTube, para
  que alguien que descubre el perfil a mitad de camino pueda "maratonear" los
  Destacados y llegar nutrido al mismo punto que un seguidor diario.

### Contribución a la regla 7-11-4

Cada historia cuenta como punto de contacto individual — una tanda completa de 4-6
historias puede aportar varios de los 11 contactos necesarios en un solo día. Es el
formato más eficiente para acumular frecuencia de contacto rápido, aunque aporta poco
tiempo de exposición real (segundos, no minutos) — por eso nunca reemplaza al
carrusel o al video largo dentro del cómputo de las 7 horas totales, solo lo
complementa.

## Reglas de coherencia con el resto del sistema

- El color de acento del día en las historias **siempre** coincide con el de los
  slides de contenido del carrusel de ese mismo día — nunca un color distinto.
- La palabra clave mencionada en la historia 6 (si aplica) es la misma del cierre del
  carrusel — nunca se inventa una nueva.
- Las historias nunca reemplazan la profundidad del carrusel o el video — su función
  es avisar, humanizar y sumar puntos de contacto, no enseñar el contenido completo.

## Checklist antes de entregar una tanda diaria

1. ¿Cada historia respeta las zonas seguras (texto fuera de los 250px superior/inferior)?
2. ¿El color de acento coincide con el del carrusel del mismo día?
3. ¿Ninguna historia repite el texto de otra en la misma tanda?
4. ¿Hay al menos un sticker interactivo con propósito claro (no decorativo)?
5. ¿La historia puente menciona explícitamente el carrusel/video del día?
6. ¿La palabra clave (si aplica) coincide con la del cierre del carrusel?

## Relación con otros skills

Toma el pilar, tema, palabra clave y color de acento del día directamente de
`carrusel-evergreen` — nunca decide un tema propio distinto al del carrusel del día.
Si la secuencia de historias se va a reforzar con pauta paga (por ejemplo, historias
patrocinadas), entrega la pieza terminada a `ads-evergreen`.
