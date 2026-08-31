# Brief de Producto — UNLaMigo

**Equipo:** Arcade  
**Versión:** 1.1  
**Repositorio:** https://github.com/gadsii-unlam/gadsii-arcade  
**Fecha:** 29/08/2026

> **Registro de cambios (v1 → v1.1):** todos los cambios de esta versión responden a la devolución del TP1. Se agrega la sección "Acceso a los usuarios", que no estaba en la v1, con la identificación de U1, U2 y U3 —los tres cumplen el rol de Conductor— y la confirmación de su disponibilidad para el relevamiento del TP2 y la prueba del MVP del TP5. Se afina la definición del segmento, que pasa de "cualquier instancia de la carrera" y "asistencia periódica" a "de segundo año en adelante" y "dos o más días por semana", y se suma una estimación aproximada de su tamaño. Se define un único usuario primario, Conductor, en lugar de los dos grupos en conjunto que figuraban antes, para poder enfocar las tres entrevistas del TP2. Y se define el mecanismo de confirmación de solicitud, que en la v1 quedaba explícitamente sin resolver.

---

## Segmento elegido de la comunidad UNLaM y por qué ese

**Segmento:** Estudiantes de la UNLaM que se encuentren activos, cursando una carrera de grado y/o pregrado de cualquier departamento, de segundo año en adelante, y que asistan presencialmente a la universidad dos o más días por semana.

**Por qué ese segmento:** el carpooling solo tiene sentido si existen patrones de traslado repetidos que puedan matchearse entre conductores y pasajeros. Por eso se acota a estudiantes activos y cursando (se descartan docentes, personal y aspirantes, que no comparten esa necesidad de traslado académico) y que asistan presencialmente dos o más días por semana (se descartan quienes cursan de forma virtual o asisten de manera esporádica, como para rendir un final, ya que no generan un trayecto recurrente que otro usuario pueda encontrar o planificar con anticipación). Se acota además a estudiantes de segundo año en adelante, cuya cursada ya está estabilizada y cuyo recorrido resulta más predecible, y que además cuentan con una trayectoria previa en la universidad —un factor que puede incidir en la confianza al compartir viaje con desconocidos.

---

### Tamaño aproximado del segmento

El dato público más reciente disponible indica una matrícula de aproximadamente 79.000 estudiantes (La Nación, octubre de 2024); no se encontró información posterior, por lo que la cifra real hoy podría ser algo mayor. Aplicando los filtros del segmento —solo grado y pregrado (~80-85%), activos y cursando (~60-70%), de segundo año en adelante (~75-80%) y con asistencia presencial de dos o más días por semana (~70-75%)— la estimación resultante es de **20.000 a 30.000 estudiantes**.

Las proporciones son estimaciones propias del equipo, no datos oficiales, y se ajustarán con el relevamiento del TP2.

---

## Acceso a los usuarios

Los tres usuarios reales identificados dentro del segmento cumplen el rol de **Conductor**:

| Usuario | Nombre | Rol | Cómo se llegó | Relación previa con el equipo |
|---|---|---|---|---|
| **U1** | Iglesias Facundo | Conductor | Familiar de un integrante del equipo | Sin relación previa |
| **U2** | Castillo Alexis | Conductor | Conocido de un integrante | Sin relación previa |
| **U3** | Guardati Francisco | Conductor | Compañero de trabajo de un integrante | Fue integrante del equipo en una materia anterior |

**Disponibilidad confirmada:** los tres usuarios confirmaron su participación en las dos instancias previstas — el relevamiento del TP2 (última semana de agosto) y la prueba del MVP del TP5 (última semana de septiembre). La confirmación se obtuvo el 29/08/2026 por contacto directo de integrantes del equipo con cada uno de ellos.

---

## Producto: nombre, problema, a quién le resuelve

**Nombre:** UNLaMigo

**Problema y a quién le resuelve:**

Una porción significativa de la comunidad universitaria se traslada diariamente al campus en vehículo propio, en la gran mayoría de los casos con un único ocupante. En paralelo, otra porción se traslada en transporte público realizando combinaciones largas.

La propuesta es construir una herramienta que conecte a ambos grupos, de modo que quienes asisten en vehículo propio no modifiquen sus recorridos habituales y puedan ofrecer las plazas disponibles, mientras que quienes se postulan como pasajeros encuentren opciones cercanas a su punto geográfico de partida.

Además de estos dos grupos, otro beneficiario es la propia institución universitaria, ya que disminuye la necesidad de gestionar grandes volúmenes de vehículos en las playas de estacionamiento, sobre todo en los horarios pico.

---

## Funcionalidades core

1. **Publicación de trayectos (conductor):** el conductor carga su trayecto indicando día (puntual o repetido durante la semana), horario y cantidad de cupos/asientos disponibles.
2. **Búsqueda de trayectos cercanos (pasajero):** el pasajero visualiza los trayectos publicados dentro de un radio aproximado de 5 a 10 cuadras de su zona.
3. **Solicitud para unirse a un trayecto (pasajero):** el pasajero envía una solicitud al conductor para formar parte de un trayecto publicado.
4. **Confirmación de la solicitud para incorporarse al trayecto (conductor):** el conductor aprueba o rechaza manualmente cada solicitud, viendo el perfil del pasajero con su condición de alumno regular ya validada. El cupo se descuenta al aceptar; si no responde antes del horario de salida, la solicitud caduca.

---

## Integraciones previstas

- **Mapa con geolocalización en tiempo real:** integración con una API de mapas (ej. Google Maps) para mostrar en tiempo real la ubicación del conductor durante el trayecto, permitiendo al pasajero seguir el viaje.
- **Validación de condición de alumno regular:** el usuario carga su certificado de alumno regular (foto o PDF) al registrarse; el rol Validador revisa y aprueba manualmente la documentación antes de habilitar la cuenta.
- **Validación del vehículo del conductor:** lectura del código QR presente en la cédula verde/azul para autocompletar los datos del vehículo, con revisión y confirmación manual por parte del Validador.

---

## Grupos de usuarios y usuario primario elegido

**Grupos identificados:**
- Conductor
- Pasajero
- Validador

**Usuario primario elegido:** Conductor

**Justificación:** UNLaMigo es un producto de dos lados y ambos roles son interdependientes, pero el conductor es el lado escaso: dispone del recurso —el vehículo y el viaje ya planeado— y hay que convencerlo de compartirlo, mientras que la demanda de pasajeros tiende a aparecer con más facilidad una vez que existe oferta disponible en una zona y horario. Sin conductores publicando trayectos no hay producto, aunque sobren pasajeros interesados. Por eso se elige al Conductor como único usuario primario y el análisis del TP2 se enfoca en él.

Esto no excluye al Pasajero como grupo de usuarios central del sistema: sólo define a quién se prioriza relevar. Los tres usuarios identificados (U1, U2 y U3) pertenecen a este grupo primario.

> ⚠️ La selección del usuario primario es una decisión de diseño y, por ahora, es hipotética: todavía no se validó con usuarios reales. El TP2 confirmará si fue acertada.

---

## Lista de supuestos

1. **Asumimos que los estudiantes tienen acceso a celulares para utilizar la aplicación.**
   *Evidencia:* encuesta breve al segmento relevado, preguntando si posee smartphone propio y sistema operativo.

2. **Asumimos que dispondrán de internet antes, durante y después de concluir el viaje en UNLaMigo.**
   *Evidencia:* encuesta al segmento sobre disponibilidad de datos móviles o Wi-Fi durante el trayecto habitual a la universidad.

3. **Asumimos que los pasajeros potenciales utilizan hoy el transporte público para llegar a la universidad.**
   *Evidencia:* relevamiento (TP2) preguntando el medio de transporte habitual utilizado para llegar al campus.

4. **Asumimos que les resulta incómoda la frecuencia y/o el espacio disponible en ese transporte público.**
   *Evidencia:* entrevistas del TP2 indagando el nivel de satisfacción con el transporte público actual y los motivos de insatisfacción.

5. **Asumimos que los estudiantes están dispuestos a viajar con compañeros que no conocen previamente, siempre que pertenezcan a la comunidad UNLaM.**
   *Evidencia:* pregunta directa en el relevamiento sobre disposición a compartir viaje con otro estudiante de la UNLaM sin conocerlo previamente.

6. **Asumimos que una ganancia económica por combustible es un incentivo suficiente para que el conductor quiera realizar viajes compartidos.**
   *Evidencia:* entrevistas a los conductores identificados (U1, U2 y U3) consultando si aceptarían compartir su viaje a cambio de una compensación por combustible.

7. **Asumimos que existe una coincidencia suficiente de recorridos y horarios entre conductores y pasajeros dentro del mismo segmento como para poder armar viajes compartidos.**
   *Evidencia:* relevamiento de puntos de partida y horarios de ingreso/egreso a la facultad de una muestra del segmento, para verificar superposición geográfica y horaria.

**Supuesto crítico:** el número 7 (coincidencia de recorridos y horarios). Si no existe suficiente superposición geográfica y horaria entre conductores y pasajeros, no hay viajes que armar y el producto pierde su razón de ser, independientemente de que el resto de los supuestos se cumplan.
