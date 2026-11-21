# UNLaMigo — Equipo Arcade

Gestión Aplicada al Desarrollo de Software II (3665) — Ingeniería Informática, UNLaM — 2° cuatrimestre 2026

**Integrantes:** Apollaro Dasha, Clivio Lucas, Fuduli Tomas, Iglesias Agustín, Portillo Jonathan

| | |
|---|---|
| MVP funcionando | https://gadsunlamigo.vercel.app/ |
| Código del MVP | [`src/`](src/) (v1.0.0) |
| Brief vigente | [`docs/brief.md`](docs/brief.md) (versión 5) |

## Qué es

UNLaMigo busca que un estudiante con auto se anime a compartirlo con otro estudiante de la UNLaM.

- **Segmento:** estudiantes activos de grado o pregrado, de segundo año en adelante, que cursan presencialmente dos o más días por semana.
- **Usuario primario:** el Conductor, que suele ir solo.
- **Problema:** no es la plata ni la logística. Es la **confianza**: sin una señal más fuerte que el sello de alumno regular, el conductor no sube a un desconocido.
- **Hipótesis:** mostrar un perfil del pasajero validado alcanza para que el conductor acepte.

**Estado al cierre (TPI):** la prueba del TP5 dio un resultado **no concluyente**. Dos de tres conductores aceptaron, y dos de tres pidieron un dato que falta: la foto. La decisión fue perseverar con un ciclo de ajuste.

El detalle está en la sección "Resultados del TP5" del brief.

## Qué está construido, qué está simulado y qué quedó diferido

| Construido (MVP 1.0.0) | Simulado | Diferido |
|---|---|---|
| Publicar un trayecto | Solicitud entrante: 4 perfiles ficticios | Lado pasajero: búsqueda y reserva |
| Aceptar o rechazar una solicitud | Validación de alumno regular: sello fijo | Registro con OCR y Validador |
| Detección de llegada (600 m) | Ingreso: acepta cualquier clave | Foto y nombre completo |
| Perfil del pasajero en pantalla | Indicador "3 alumnos validados cerca tuyo" | Editar o borrar trayectos |
| | | Backend y datos compartidos |

El MVP es una aplicación de una sola página y solo recorre el flujo del conductor. No tiene backend: el estado vive en el `localStorage` del navegador, bajo la clave `unlamigo:v1`.

## Cómo se ejecuta

El código está en `src/`. Es React 19, TypeScript y Vite.

```bash
git clone https://github.com/gadsii-unlam/gadsii-arcade.git
cd gadsii-arcade/src
npm install
npm run dev -- --host   # --host para abrirla desde el celular en la misma red
npm run build           # build de producción en dist/
```

- Para entrar alcanza con cualquier usuario y contraseña: se usa el perfil demo de `src/data.ts`.
- Los botones "Demo: …" simulan los eventos que en la versión real vendrían de otro usuario o del GPS.
- "Verificar llegada" usa la geolocalización del navegador, así que necesita HTTPS o localhost.

El código se trajo del repositorio `agustiniglesias99/GADS` (carpeta `UnlamigoMVP/UNLaMigo`). El deploy de https://gadsunlamigo.vercel.app/ todavía se publica desde ese repositorio.

## Estructura del repositorio

```
src/                             Código del MVP v1.0.0 (React, TypeScript y Vite)
docs/
├── brief.md                     Brief del producto (v5); el registro de cambios v1→v5 está arriba de todo
├── prompts.md                   Registro de trabajo con IA
├── diseno/                      TP3: alternativas, propuesta final y wireframe navegable
├── evaluacion/                  TP4: evaluación heurística (informe TP4A, evaluación IA, perfil evaluado)
├── evidencia/
│   ├── tp2/entrevistas.md       Relevamiento con U1, U2 y U3
│   └── tp5/                     Prueba del MVP: notas por usuario y transcripción de las sesiones
└── arquitectura/                TP6: diagramas de arquitectura
```

## Líneas base

Cada entrega está congelada en un tag. Para ver el estado del proyecto en una entrega: `git checkout <tag>`.

| Tag | Entrega |
|---|---|
| `tp1-entrega` | Brief v1 |
| `tp2-entrega` | Relevamiento y brief v2 |
| `tp3-entrega` | Diseño y brief v3 |
| `tp4-entrega` | Versión congelada para la evaluación cruzada |
| `tp5-entrega` | Prueba del MVP y brief v4 |
| `tp6-entrega` | Arquitectura y brief v5 |
| `tpi-entrega` | Trabajo Práctico Integrador |

## Cómo se continúa

**1. Ciclo de ajuste**, definido en el TP5:
1. Completar el perfil que ve el conductor con foto y nombre completo.
2. Quitar el indicador fijo "3 alumnos validados cerca tuyo" y los botones Demo, y hacer que la solicitud llegue sola.
3. Repetir la prueba con tres conductores **reales** nuevos, con los mismos umbrales del criterio de éxito.
4. Construir el lado pasajero solo si ese ciclo confirma la hipótesis. Recién ahí se puede probar la coincidencia de recorridos y horarios (supuesto 7, el crítico).

Si el segundo ciclo da 1 de 3 aceptaciones o menos con el perfil completo, corresponde un pivote de necesidad del consumidor.

**2. Para salir a producción**, hay que reemplazar lo simulado:

| Hoy | Para producción |
|---|---|
| Ingreso con cualquier clave y sello fijo | Registro real, OCR autoalojado, cola del Validador y almacenamiento privado (el certificado tiene el DNI: ley 25.326) |
| Datos en `localStorage` | PostgreSQL con PostGIS gestionado (por ejemplo, Supabase) |
| Solicitud con botón Demo | Solicitudes entre personas y notificaciones push (en iOS, con la PWA instalada) |
| Lado pasajero inexistente | Búsqueda en un radio de 5 a 10 cuadras y reserva con un día de antelación |
| Perfil con iniciales | Foto y nombre completo, en almacenamiento privado |
| Botones Demo visibles | Sacarlos de la versión de producción |

**3. Primer riesgo a resolver:** la ubicación en el navegador. Es el único componente que depende del mundo físico, y los navegadores la frenan con la pantalla bloqueada, sobre todo en iOS. Para mitigarlo: probar en dispositivos reales, tener una confirmación manual de respaldo y decidir entre PWA y app nativa.

La arquitectura objetivo y el componente más riesgoso están en la sección "Arquitectura del sistema (TP6)" del brief.

## Límites conocidos

- No se relevaron pasajeros, así que los supuestos 3, 4 y 7 no tienen evidencia.
- El TP2 son tres conductores de cursada nocturna, todos conocidos del equipo.
- La prueba del TP5 no confirma ni refuta la hipótesis.
- M2 admite dos lecturas, y según cuál se use cambia el veredicto.
- No se probaron la ubicación ni las notificaciones push en dispositivos reales.
- El registro de prompts está resumido y le faltan sesiones.
