# Ecosistema de Automatización IA para RiDMi

Proyecto final de automatización IA para la gestión de tickets de soporte de RiDMi.

## Descripción

Sistema de atención automatizada para consultas estudiantiles de RiDMi. El ecosistema recibe tickets desde Airtable, los procesa mediante inteligencia artificial en Make y prepara respuestas que deben ser aprobadas por una persona antes de enviarse por Gmail.

## Tecnologías utilizadas

- Make: orquestación y automatización.
- Airtable: base de datos, memoria y dashboard.
- OpenAI: clasificación y generación de respuestas.
- Gmail: canal de salida.

## Funcionamiento

1. Airtable registra un ticket con estado Pendiente.
2. Make detecta el registro.
3. OpenAI clasifica la consulta y genera una respuesta propuesta.
4. Airtable almacena la categoría, prioridad, sentimiento y respuesta.
5. El ticket queda en Esperando aprobación.
6. Una persona revisa y aprueba la respuesta.
7. Gmail envía el mensaje.
8. Airtable registra la fecha, el Thread ID y el estado Enviado.

## Seguridad y resiliencia

- Validación humana antes del envío.
- Filtros para evitar reprocesamientos y envíos duplicados.
- Registro de errores técnicos.
- Cambio automático del ticket al estado Error.
- Directiva Break para detener ejecuciones inseguras.
- Variables dinámicas y minimización de datos personales.

## Archivos del repositorio

- Informe final en PDF.
- Blueprint técnico del escenario de Make.
- Capturas de evidencia del sistema.

## Video demostrativo

[Ver video demo de RiDMi](https://drive.google.com/file/d/1JryK7pMXJeh9euJNeDUWyf4Y5nKcbfKz/view?usp=sharing)

## Autora

Valentina Morey— Proyecto final de Arquitectura de Flujos IA.
