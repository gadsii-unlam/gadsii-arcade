# TP5 — Métricas y criterio de éxito

Hipótesis que se prueba: el Conductor acepta a un pasajero que no conoce cuando se le muestra un perfil de confianza, más allá de la validación de alumno regular (ver "Hipótesis de valor" en [`docs/brief.md`](../brief.md)).

## Métricas

- **M1. Aceptación de solicitudes de desconocidos.** 2 de 3 o más aceptan: se construye el lado pasajero. 1 de 3 o menos: se investiga qué condición de confianza falta.
- **M2. Información buscada antes de decidir.** Si 2 o más piden el mismo dato, entra primero al próximo ciclo.
- **Métrica vanidosa:** trayectos publicados. No dice si el conductor se anima a subir a un desconocido, por eso no se usa para decidir.

## Criterio de éxito

| Resultado | Condición |
|---|---|
| **Confirma** | 2 o más de 3 aceptan y como máximo 1 pide información extra |
| **Refuta** | 1 o menos acepta |
| **No concluyente** | 2 o más aceptan, pero 2 o más piden información adicional |

## Resultado

**No concluyente:** M1 dio 2 de 3 (U1 y U2 aceptan, U3 rechaza) y M2 dio 2 de 3 (U2 y U3 piden la foto). La lectura completa del resultado y la decisión de perseverar están en "Resultados del TP5" del brief (v4 en adelante) y la evidencia, en [`docs/evidencia/tp5/`](../evidencia/tp5/).

> Nota: este archivo se agregó al repositorio para el TPI (21/11/2026). Las métricas y los umbrales son los mismos que figuran en el brief desde la v4 (commit `d058fd0`, 10/11/2026), sin cambios.
