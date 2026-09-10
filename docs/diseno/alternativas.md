# Alternativas de diseño — TP3

**Equipo:** Arcade · **Producto:** UNLaMigo
**Fecha:** 09/09/2026
**Origen:** generadas con Claude Chat (claude.ai) a partir del brief v3 como prompt inicial. Ver `docs/prompts.md`.

Se pidieron tres estructuras distintas para el mismo flujo principal, cada una privilegiando un atributo de usabilidad diferente. Las tres son diseños válidos: ninguna es correcta en abstracto, son decisiones de compromiso.

---

## Alternativa A — Facilidad de aprendizaje

*Más pasos, cada uno simple y evidente, con acompañamiento.*

**Pantallas:** Login → Home con guía inicial → Publicar trayecto en dos pasos (ubicación / horario y cupos) → Resumen previo → Confirmación → Solicitud a pantalla completa → Iniciar viaje → Llegada → Finalizar.

**Diferencia estructural:** cada acción es una pantalla propia, nada se agrupa, para que nunca haya más de una decisión por vez.

---

## Alternativa B — Eficiencia

*Menos pasos, mayor densidad de información, atajos.*

**Pantallas:** Login → Home única (mapa, publicar y trayectos activos juntos) → Publicar en un formulario compacto → Confirmación flotante → Solicitud como notificación con acciones rápidas → Finalización automática al detectar llegada.

**Diferencia estructural:** se colapsan pantallas y se sacan pasos intermedios; la información se agrupa en vez de secuenciarse.

---

## Alternativa C — Satisfacción

*Foco en refuerzo emocional y señales de confianza visibles, no en cantidad de pasos.*

**Pantallas:** Login → Home con bienvenida y señal de confianza ("3 alumnos validados cerca tuyo") → Publicar con vista previa de lo que ve el pasajero → Confirmación con tono cercano → Solicitud con foto grande y sello "Alumno validado UNLaM" → Refuerzo tras aceptar → Cierre con agradecimiento.

**Diferencia estructural:** el flujo tiene la misma cantidad de pasos que una versión estándar, pero cada pantalla suma contenido de refuerzo y confianza en vez de sólo información funcional.

---

## Comparación

| Alternativa | Atributo | Qué gana | Qué resigna |
|---|---|---|---|
| A | Facilidad de aprendizaje | Ningún paso resulta confuso para un usuario primerizo | Velocidad: más pantallas alargan cada uso |
| B | Eficiencia | Encaja con las ventanas de uso cortas | Contexto y claridad: más carga cognitiva por pantalla |
| C | Satisfacción | Refuerza la confianza en cada pantalla clave | Densidad y pasos de refuerzo que no aportan velocidad |

La alternativa elegida y su fundamentación están en `propuesta-final.md`.
