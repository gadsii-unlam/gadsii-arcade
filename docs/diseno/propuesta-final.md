# Propuesta final de diseño — TP3

**Equipo:** Arcade · **Producto:** UNLaMigo
**Fecha:** 09/09/2026
**Alternativa elegida:** C — Satisfacción

---

## Por qué C

La hipótesis de valor del TP2 no busca sólo que el conductor complete el flujo de aceptar una solicitud: busca que acepte a alguien que no conocía y sostenga esa decisión de forma recurrente. Eso es un problema de confianza, no de velocidad ni de curva de aprendizaje.

U2 y U3 fueron explícitos en que no subirían a un desconocido bajo ninguna condición administrativa, y ninguno de los tres mencionó el tiempo o la complejidad de uso como fricción. Por eso la Alternativa C, que refuerza señales de confianza en cada pantalla clave —perfil visible, sello de validación, mensajes de refuerzo—, es la que ataca la barrera real detectada en el relevamiento.

## Qué cuesta la elección

El flujo no es el más rápido ni el más simple de aprender: hay más contenido por pantalla del que estrictamente se necesita para completar la tarea. Es un riesgo real, porque las ventanas de uso son cortas (U1 la usaría el mismo día antes de salir; U2, mientras merienda).

Conviene vigilarlo en la prueba del TP5: si el refuerzo empieza a sentirse como fricción en vez de ayuda, habrá que recortarlo sin perder las señales de confianza que sostienen la hipótesis.

## Qué se descartó de las propuestas recibidas

| Propuesta | Hallazgo del TP2 que la contradice | Reemplazo |
|---|---|---|
| Chat entre conductor y pasajero previo a la aceptación | U2 fue terminante: "solo lo haría si fuera un amigo". Un chat no convierte a un desconocido en amigo y suma una conversación antes de cada viaje. La barrera es de seguridad percibida, no de canal. | Perfil con carrera y antigüedad, visible al decidir |
| Historial de viajes y calificaciones como mecanismo principal de confianza | Un MVP recién lanzado no tiene uso acumulado: el historial estaría vacío o cargado a mano, y el conductor decidiría sobre información inventada. | Antigüedad como alumno regular, verificable desde el primer día |

## Decisión no anclada en el relevamiento

Los mensajes de refuerzo de la Alternativa C —el texto de cierre tras aceptar una solicitud y el mensaje al iniciar el viaje— no surgen de ningún dato del TP2. Ningún usuario pidió acompañamiento ni mencionó el tono de la aplicación. Se incorporaron por coherencia con el atributo priorizado, asumiendo que reforzar la decisión reduce el arrepentimiento posterior. Es una suposición del equipo y se declara como tal.

---

El desarrollo de esta alternativa como wireframe navegable está en `wireframe/index.html`.
