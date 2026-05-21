---
name: prompt-rctf
description: Crea y mejora prompts usando la plantilla RCTF (Rol, Contexto, Tarea, Formato). Usa esta skill siempre que el usuario pida armar un prompt, mejorar un prompt, estructurar instrucciones para ChatGPT, Claude o Gemini, convertir una idea vaga en un prompt reutilizable, o mencione contexto, tarea, formato, briefing, prompt maestro, prompt template o una necesidad similar, aunque no diga "RCTF" explícitamente.
metadata:
  author: OventLabs
  version: "1.0.0"
---

# Prompt RCTF

Convierte solicitudes vagas en prompts claros, útiles y reutilizables.

La meta no es solo "escribir bonito", sino ayudar al usuario a pensar mejor lo que necesita antes de pedirlo a una IA. Por eso esta skill primero reúne la información mínima y luego entrega un prompt listo para usar.

## Cuándo usar esta skill

Úsala cuando el usuario:

- quiera crear un prompt desde cero
- tenga una idea suelta y quiera estructurarla
- pida mejorar un prompt que ya existe
- necesite una plantilla para ChatGPT, Claude o Gemini
- mencione que quiere dar mejor contexto, definir formato o pedir una tarea con claridad

## Flujo de trabajo

### 1. Detecta qué información ya existe

Antes de preguntar, revisa si el usuario ya dio alguna de estas piezas:

- `rol`
- `contexto`
- `tarea`
- `formato`
- `información básica`

No repitas preguntas innecesarias.

### 2. Pide solo lo que falte

Si faltan datos, haz una solicitud breve y clara. Prioriza estas piezas:

1. `contexto`
2. `tarea`
3. `formato`
4. `información básica`

`rol` es recomendable, pero si el usuario no lo define puedes inferir uno razonable a partir del contexto y la tarea. Si la inferencia pudiera cambiar mucho el resultado, dilo explícitamente.

Usa preguntas simples, en español, sin tecnicismos. Idealmente en bloque corto como este:

```text
Para armártelo bien, pásame esto:
- Contexto: ¿para qué negocio, equipo o situación es?
- Tarea: ¿qué quieres que haga exactamente la IA?
- Formato: ¿cómo quieres la respuesta? (tabla, bullets, correo, resumen, etc.)
- Información básica: pega aquí notas, texto, datos o ejemplos.
```

Si el usuario ya dio casi todo, pide solo el faltante.

### 3. Construye el prompt final

Cuando ya tengas suficiente contexto, entrega un prompt final listo para copiar y usar.

Usa esta estructura:

```text
Eres [ROL].

Contexto:
- [contexto útil y concreto]

Tarea:
- [acción principal]
- [aclaraciones importantes]

Formato:
- [estructura de salida]
- [tono, longitud o restricciones si aplican]

Información base:
[contenido fuente del usuario]
```

### 4. Mejora el prompt, no solo lo rellenes

Al redactar:

- vuelve específico lo que venga ambiguo
- ordena la información para que la IA entienda rápido
- conserva la intención real del usuario
- evita adornos innecesarios
- agrega una instrucción de control de calidad cuando ayude

Ejemplos de mejoras útiles:

- "si falta información, indícalo al final"
- "no inventes datos"
- "si hay varias opciones, prioriza la más viable"
- "usa un tono ejecutivo y directo"

### 5. Entrega con formato consistente

Tu respuesta debe seguir esta estructura:

## Prompt final

```text
[prompt completo]
```

## Variables clave

- Rol: ...
- Contexto: ...
- Tarea: ...
- Formato: ...

## Sugerencia opcional

Da una sola sugerencia breve para mejorarlo aún más si el usuario quiere iterar.

Si el usuario pidió únicamente "dame el prompt", puedes omitir la explicación y entregar solo el bloque `Prompt final`.

## Reglas de comportamiento

- No conviertas la interacción en un cuestionario largo.
- No pidas información que no afecte el resultado.
- Si el usuario escribe con errores o informal, responde con calidez y claridad.
- Si falta información crítica, dilo de frente y pide solo lo indispensable.
- Si el usuario no tiene información base todavía, entrega una versión con placeholders claros para completar.
- Si el usuario trae un prompt ya escrito, primero diagnostica qué le falta dentro de RCTF y luego propón una versión mejorada.

## Ejemplos

**Ejemplo 1:**

Input:
"Quiero un prompt para hacer un acta de reunión con IA."

Output esperado:
- Pide `contexto`, `tarea`, `formato` e `información básica` si faltan.
- Si el usuario responde, arma un prompt final para convertir notas en acta formal.

**Ejemplo 2:**

Input:
"Tengo estas notas de una junta y quiero que Claude me saque acuerdos y responsables."

Output esperado:
- Reutiliza las notas como `información básica`.
- Si falta, pregunta el formato deseado.
- Entrega un prompt final orientado a resumen ejecutivo + tabla de acuerdos.

**Ejemplo 3:**

Input:
"Mejorame este prompt: redacta un correo para un cliente."

Output esperado:
- Detecta que faltan contexto, tono y objetivo.
- Pide solo esos faltantes.
- Devuelve un prompt mucho más específico y reusable.
