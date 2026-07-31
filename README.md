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

## Matriz de costos y optimización de IA

Para estimar el consumo se considera un volumen de 1.000 tickets, con un promedio de 500 tokens de entrada y 250 tokens de salida por ticket.

| Modelo | Uso propuesto | Costo entrada por 1M tokens | Costo salida por 1M tokens | Costo estimado por 1.000 tickets | Decisión |
|---|---|---:|---:|---:|---|
| GPT-4o mini | Clasificación, prioridad, sentimiento y respuesta inicial | USD 0,15 | USD 0,60 | USD 0,23 | Modelo principal |
| GPT-4o | Casos complejos o escalados | USD 2,50 | USD 10,00 | USD 3,75 | Uso excepcional |

### Cálculo estimado

- Entrada: 1.000 × 500 tokens = 500.000 tokens.
- Salida: 1.000 × 250 tokens = 250.000 tokens.
- GPT-4o mini: `(0,5 × USD 0,15) + (0,25 × USD 0,60) = USD 0,225`.
- GPT-4o: `(0,5 × USD 2,50) + (0,25 × USD 10,00) = USD 3,75`.

La utilización de GPT-4o mini como modelo principal produce un ahorro estimado de USD 3,53 cada 1.000 tickets, equivalente aproximadamente al 94 % frente al procesamiento de todos los casos con GPT-4o.

### Estrategia de optimización

- Utilizar GPT-4o mini para el procesamiento habitual.
- Escalar a un modelo avanzado solamente los casos ambiguos o complejos.
- Limitar la extensión de las respuestas generadas.
- Enviar a la IA únicamente los campos necesarios.
- Evitar procesar nuevamente tickets ya clasificados.
- Mantener aprobación humana antes del envío.
- Registrar tokens y errores para controlar costos reales.

Los valores son estimativos y corresponden a las tarifas consideradas al elaborar el proyecto. Pueden variar si el proveedor actualiza sus precios.

## Dashboard de control

El panel permite supervisar el estado de los tickets, prioridades, categorías, aprobaciones, envíos y errores del sistema.

- [Ver dashboard público de RiDMi](https://airtable.com/appRTpcuXDpfXkOfd/shrnDzXuWCkt5vdyb)
- [Ver registros y métricas del sistema](https://airtable.com/appRTpcuXDpfXkOfd/shrLsjN2eNJ6SKEuj)

## Archivos del repositorio

- Informe final en PDF.
- Blueprint técnico del escenario de Make.
- Capturas de evidencia del sistema.

## Video demostrativo

[Ver video demo de RiDMi](https://drive.google.com/file/d/1JryK7pMXJeh9euJNeDUWyf4Y5nKcbfKz/view?usp=sharing)

## Autora

Valentina Morey — Proyecto final de Arquitectura de Flujos IA.
