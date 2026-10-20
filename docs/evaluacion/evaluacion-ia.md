# Evaluación heurística de la IA — UNLaM WayFinder (Taiko)

> **Aclaración sobre este archivo:** el texto original de la respuesta de la IA no se conservó. Este archivo se reconstruyó a partir de la tabla de resultados incluida en el informe TP4A (Punto 3) y del prompt que figura allí. El contenido de la tabla es el mismo que el del informe; no incorpora comentarios ni clasificaciones del equipo. Si se recupera la conversación original, reemplazar esta reconstrucción por el texto literal.

## Datos de la consulta

- **Herramienta:** Claude (claude.ai) — versión: [completar]
- **Fecha de la consulta:** [completar]
- **Material entregado a la IA:** el brief v3 y el wireframe del MVP de UNLaM WayFinder (repositorio `gadsii-unlam/gadsii-taiko`).
- **Quién consultó:** Equipo Arcade (evaluador).

## Prompt entregado

> Actuá como evaluador experto en usabilidad y aplicá las 10 heurísticas de Nielsen al wireframe del MVP de UNLaM WayFinder. El usuario es un estudiante ingresante o de 1.º/2.º año de la UNLaM que no conoce el campus, usa la app desde el celular y con apuro. El equipo priorizó facilidad de aprendizaje y eficiencia. El MVP excluye GPS/pathfinding, login/SIU-Guaraní, favoritos/origen y transporte público. Devolvé una tabla con: #, heurística incumplida, descripción del problema, severidad (1-4) y mejora sugerida.

## Resultado de la IA

| # | Heur. | Descripción del problema | Sev. | Mejora sugerida |
|---|---|---|---|---|
| IA-1 | H9 | No hay ningún estado de error: si falla la carga de los datos no se comunica nada ni se ofrece reintentar. | 3 | Prever un mensaje de error con acción de reintento. |
| IA-2 | H1 | No hay estado de carga al abrir el plano ni al buscar; no se distingue ‘sin resultados’ de ‘todavía cargando’. | 2 | Indicadores de carga (skeleton / spinner). |
| IA-3 | H4 | El buscador no sugiere ni valida términos; el usuario puede escribir un aula inexistente. | 2 | Autocompletado con las entidades cargadas. |
| IA-4 | H1 | El plano no muestra la ubicación actual del usuario (‘estoy acá’). | 3 | Mostrar la posición del usuario sobre el plano. |
| IA-5 | H3 | Cambiar el día/hora no pide confirmación ni permite deshacer; se pierde el contexto. | 2 | Permitir deshacer o volver a ‘hoy/ahora’. |
| IA-6 | H10 | No hay ayuda ni documentación accesible desde la interfaz. | 2 | Ayuda contextual por pantalla. |
| IA-7 | H7 | No hay favoritos ni opción de repetir la última búsqueda. | 2 | Guardar últimas consultas o favoritos. |
| IA-8 | H4 | No hay login ni validación de identidad del estudiante (SIU-Guaraní). | 3 | Incorporar autenticación. |
| IA-9 | H5 | Inconsistencia: ‘Servicios’ usa la hora real del dispositivo mientras el resto usa el día simulado. | 1 | Unificar el criterio de tiempo o explicarlo. |
| IA-10 | H2 | La sigla ‘PAB’ y términos como ‘predio’ no coinciden con el lenguaje del usuario. | 3 | Usar el vocabulario del estudiante. |
| IA-11 | H1 | El panel lateral derecho de P1 se muestra vacío y no ofrece ninguna acción. | 1 | Usar el espacio para sugerencias o aclarar el estado. |
