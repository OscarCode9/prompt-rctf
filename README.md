# 🤖 Prompt RCTF Skill

[![GitHub license](https://img.shields.io/github/license/OscarCode9/prompt-rctf?style=flat-square)](LICENSE)
[![GitHub stars](https://img.shields.io/github/stars/OscarCode9/prompt-rctf?style=flat-square)](https://github.com/OscarCode9/prompt-rctf/stargazers)
[![GitHub issues](https://img.shields.io/github/issues/OscarCode9/prompt-rctf?style=flat-square)](https://github.com/OscarCode9/prompt-rctf/issues)

Una herramienta inteligente para diseñar, estructurar y optimizar prompts para Modelos de Lenguaje (LLMs) como ChatGPT, Claude y Gemini utilizando el framework **RCTF** (Rol, Contexto, Tarea, Formato).

---

## 🚀 ¿Qué es el Framework RCTF?

El método **RCTF** organiza las instrucciones para que la Inteligencia Artificial entienda con precisión qué hacer y bajo qué condiciones.

| Componente | Descripción |
| :--- | :--- |
| **👤 Rol** | Define la identidad, tono y expertise que debe asumir la IA. |
| **📝 Contexto** | Explica la situación de fondo, el público objetivo y la información necesaria. |
| **🎯 Tarea** | Indica la acción concreta y los pasos específicos que debe realizar. |
| **📊 Formato** | Detalla la estructura del entregable (tablas, listas, longitud, tono, etc.). |

---

## 🛠️ ¿Cómo funciona esta Skill?

Esta skill guía al usuario de manera conversacional, amigable y eficiente:

1. **Analiza el input:** Detecta qué información del framework ya se proporcionó en el mensaje inicial del usuario.
2. **Pregunta lo que falta:** Realiza preguntas cortas y directas para completar el framework sin sobrecargar al usuario.
3. **Optimiza el Prompt:** Refina el prompt agregando instrucciones implícitas de control de calidad, restricción de alucinaciones y tono.
4. **Formato Consistente:** Entrega el prompt definitivo listo para copiar y usar.

---

## 💡 Ejemplos de Uso

### Entrada (Input)
> *"Quiero un prompt para que Claude convierta unas notas sueltas en un acta de reunión formal con responsables y fechas. Todavía no sé bien cómo pedírselo."*

### Salida Esperada (Output)
La skill interactúa para recopilar detalles y entrega un resultado como este:

```text
Eres un Asistente Ejecutivo de Operaciones de Alto Rendimiento.

Contexto:
- Necesito redactar un acta de reunión formal de equipo a partir de notas desordenadas y rápidas tomadas durante la sesión.

Tarea:
- Analiza las notas proporcionadas en la sección "Información base".
- Extrae los acuerdos clave acordados durante la junta.
- Identifica a los responsables y las fechas de entrega de cada tarea asignada.
- Si falta información crítica para un acuerdo, indícalo claramente como un punto pendiente.

Formato:
- Resumen ejecutivo breve en un párrafo de las conclusiones principales.
- Tabla Markdown con las columnas: [Tema, Acuerdo/Acción, Responsable, Fecha Límite].
- Tono profesional, directo y formal.

Información base:
[Notas del usuario]
```

---

## 📂 Estructura del Proyecto

```bash
prompt-rctf/
├── SKILL.md          # Definición de la skill y las reglas de comportamiento.
├── evals/
│   └── evals.json    # Casos de prueba para evaluar la precisión de la skill.
└── README.md         # Documentación del proyecto.
```

---

## 👥 Contribuciones

Las contribuciones son bienvenidas. Si tienes sugerencias para mejorar las plantillas o agregar nuevas evaluaciones, por favor abre un *Issue* o envía un *Pull Request*.

---

Desarrollado con ❤️ por [OscarCode9](https://github.com/OscarCode9).
