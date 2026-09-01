# Brief de Producto — UNLaMigo

**Equipo:** Arcade
**Versión:** 2
**Repositorio:** https://github.com/gadsii-unlam/gadsii-arcade
**Fecha:** 01/09/2026

## Registro de cambios

### v1 → v1.1 (29/08/2026 — devolución del TP1)
- Se agrega la sección "Acceso a los usuarios", inexistente en la v1, con la identificación de U1, U2 y U3 y la confirmación de que los tres cumplen el rol de Conductor.
- Se agrega la confirmación de disponibilidad de U1, U2 y U3 para el relevamiento del TP2 y para la prueba del MVP del TP5 (condición excluyente señalada por el corrector).
- Se afina la definición del segmento: pasa de "cualquier instancia de la carrera" y "asistencia periódica" a "de segundo año en adelante" y "dos o más días por semana".
- Se agrega una estimación aproximada del tamaño del segmento (20.000 a 30.000 estudiantes).
- Se redefine el usuario primario: pasa de "Conductor y Pasajero" en conjunto a un único usuario primario, Conductor, para poder enfocar las tres entrevistas del TP2.
- Se define el mecanismo de confirmación de la solicitud (funcionalidad core #4), que en la v1 quedaba explícitamente sin resolver.

### v1.1 → v2 (01/09/2026 — TP2)
- Se agrega el **perfil real** de U1, U2 y U3, reemplazando cualquier caracterización hipotética previa.
- Se agregan las **necesidades reales, problemas/frustraciones y contexto de uso** relevados en las entrevistas, organizados por usuario.
- Se agrega la **hipótesis de valor**, centrada en la barrera de seguridad/confianza detectada en las tres entrevistas.
- Se actualiza la **Lista de supuestos** con el estado real de cada uno (Confirmado, Sin evidencia, Mayormente refutado, Refutado como driver principal, o Parcialmente confirmado), reemplazando la "evidencia a relevar" de la v1.1 por la evidencia efectivamente obtenida.
- Se retira la advertencia de que el usuario primario era una decisión "hipotética": el TP2 confirmó que el Conductor es, en efecto, el lado más difícil de convencer.
- Se agregan dos requisitos nuevos a la funcionalidad core #4 (garantía ante cancelaciones y reserva con antelación) y una nota a la integración de validación de alumno regular (no alcanza por sí sola para generar confianza).
- Se agrega una advertencia sobre la estimación de tamaño del segmento: la baja frecuencia presencial de uno de los conductores relevados (U2) sugiere que podría estar sobreestimada.


---

## Segmento elegido de la comunidad UNLaM y por qué ese

**Segmento:** Estudiantes de la UNLaM que se encuentren activos, cursando una carrera de grado y/o pregrado de cualquier departamento, de segundo año en adelante, y que asistan presencialmente a la universidad dos o más días por semana.

**Por qué ese segmento:** el carpooling solo tiene sentido si existen patrones de traslado repetidos que puedan matchearse entre conductores y pasajeros. Por eso se acota a estudiantes activos y cursando (se descartan docentes, personal y aspirantes, que no comparten esa necesidad de traslado académico) y que asistan presencialmente dos o más días por semana (se descartan quienes cursan de forma virtual o asisten de manera esporádica, como para rendir un final, ya que no generan un trayecto recurrente que otro usuario pueda encontrar o planificar con anticipación). Se acota además a estudiantes de segundo año en adelante, cuya cursada ya está estabilizada y cuyo recorrido resulta más predecible, y que además cuentan con una trayectoria previa en la universidad —un factor que puede incidir en la confianza al compartir viaje con desconocidos.

*Sin cambios respecto de la v1.1.*

---

### Tamaño aproximado del segmento

El dato público más reciente disponible indica una matrícula de aproximadamente 79.000 estudiantes (La Nación, octubre de 2024); no se encontró información posterior, por lo que la cifra real hoy podría ser algo mayor. Aplicando los filtros del segmento —solo grado y pregrado (~80-85%), activos y cursando (~60-70%), de segundo año en adelante (~75-80%) y con asistencia presencial de dos o más días por semana (~70-75%)— la estimación resultante es de **20.000 a 30.000 estudiantes**.

Las proporciones son estimaciones propias del equipo, no datos oficiales.

> ⚠️ **Actualización TP2:** el relevamiento reveló que la frecuencia de cursada presencial no es uniforme incluso dentro del grupo Conductor: uno de los tres usuarios (U2) solo cursa presencial un día a la semana. Esto sugiere que la proporción de "asistencia dos o más días por semana" (~70-75%) podría estar sobreestimando la disponibilidad real de oferta, y conviene revisarla con una muestra más grande.

---

## Acceso a los usuarios

Los tres usuarios reales identificados dentro del segmento cumplen el rol de **Conductor**:

| Usuario | Nombre | Rol | Cómo se llegó | Relación previa con el equipo |
|---|---|---|---|---|
| **U1** | Iglesias Facundo | Conductor | Familiar de un integrante del equipo | Sin relación previa |
| **U2** | Castillo Alexis | Conductor | Conocido de un integrante | Sin relación previa |
| **U3** | Guardati Francisco | Conductor | Compañero de trabajo de un integrante | Fue integrante del equipo en una materia anterior |

**Disponibilidad confirmada:** los tres usuarios confirmaron su participación en las dos instancias previstas — el relevamiento del TP2 (última semana de agosto) y la prueba del MVP del TP5 (última semana de septiembre). La confirmación se obtuvo el 29/08/2026 por contacto directo de integrantes del equipo con cada uno de ellos.

**Estado:** relevamiento del TP2 completo con los tres (ver "Perfil real del usuario" más abajo).

---

## Producto: nombre, problema, a quién le resuelve

**Nombre:** UNLaMigo

**Problema y a quién le resuelve:**

Una porción significativa de la comunidad universitaria se traslada diariamente al campus en vehículo propio, en la gran mayoría de los casos con un único ocupante. En paralelo, otra porción se traslada en transporte público realizando combinaciones largas.

La propuesta es construir una herramienta que conecte a ambos grupos, de modo que quienes asisten en vehículo propio no modifiquen sus recorridos habituales y puedan ofrecer las plazas disponibles, mientras que quienes se postulan como pasajeros encuentren opciones cercanas a su punto geográfico de partida.

Además de estos dos grupos, otro beneficiario es la propia institución universitaria, ya que disminuye la necesidad de gestionar grandes volúmenes de vehículos en las playas de estacionamiento, sobre todo en los horarios pico.

*Sin cambios respecto de la v1.1. El TP2 matiza fuertemente a qué necesidad le resuelve el problema con más fuerza: ver "Necesidades reales" más abajo.*

---

## Funcionalidades core

1. **Publicación de trayectos (conductor):** el conductor carga su trayecto indicando día (puntual o repetido durante la semana), horario y cantidad de cupos/asientos disponibles.
2. **Búsqueda de trayectos cercanos (pasajero):** el pasajero visualiza los trayectos publicados dentro de un radio aproximado de 5 a 10 cuadras de su zona.
3. **Solicitud para unirse a un trayecto (pasajero):** el pasajero envía una solicitud al conductor para formar parte de un trayecto publicado.
4. **Confirmación de la solicitud para incorporarse al trayecto (conductor):** el conductor aprueba o rechaza manualmente cada solicitud, viendo el perfil del pasajero con su condición de alumno regular ya validada. El cupo se descuenta al aceptar; si no responde antes del horario de salida, la solicitud caduca.

> ⚠️ **Actualización TP2:** el relevamiento agregó dos requisitos no contemplados en esta funcionalidad:
> - **Garantía ante cancelaciones (U1):** qué pasa si el viaje coordinado no se concreta (el conductor o un pasajero cancela, o el vehículo se avería). U1 preguntó explícitamente si existe un método de reembolso.
> - **Reserva con antelación (U3):** a diferencia del uso "mismo día" que describe U1, U3 preferiría poder reservar el trayecto con anticipación.
>
> Ambos puntos quedan como insumo para el diseño de esta funcionalidad en el TP3.

---

## Integraciones previstas

- **Mapa con geolocalización en tiempo real:** integración con una API de mapas (ej. Google Maps) para mostrar en tiempo real la ubicación del conductor durante el trayecto, permitiendo al pasajero seguir el viaje.
- **Validación de condición de alumno regular:** el usuario carga su certificado de alumno regular (foto o PDF) al registrarse; el rol Validador revisa y aprueba manualmente la documentación antes de habilitar la cuenta.
- **Validación del vehículo del conductor:** lectura del código QR presente en la cédula verde/azul para autocompletar los datos del vehículo, con revisión y confirmación manual por parte del Validador.

> ⚠️ **Actualización TP2:** el hallazgo más importante del relevamiento es que la validación de alumno regular, por sí sola, **no alcanza** para destrabar la confianza del conductor. Dos de los tres conductores (U2 y U3) no aceptarían viajar con un desconocido bajo ninguna condición administrativa: solo confían en amigos (U2) o en personas con las que generen confianza charlando antes —nombre, carrera, dónde vive— (U3). Esto sugiere sumar mecanismos de confianza adicionales (perfil del pasajero, antigüedad como alumno, historial de viajes, calificaciones) a la integración de validación ya prevista.

---

## Grupos de usuarios y usuario primario elegido

**Grupos identificados:**
- Conductor
- Pasajero
- Validador

**Usuario primario elegido:** Conductor

**Justificación:** UNLaMigo es un producto de dos lados y ambos roles son interdependientes, pero el conductor es el lado escaso: dispone del recurso —el vehículo y el viaje ya planeado— y hay que convencerlo de compartirlo, mientras que la demanda de pasajeros tiende a aparecer con más facilidad una vez que existe oferta disponible en una zona y horario. Sin conductores publicando trayectos no hay producto, aunque sobren pasajeros interesados. Por eso se elige al Conductor como único usuario primario y el análisis del TP2 se enfoca en él.

Esto no excluye al Pasajero como grupo de usuarios central del sistema: sólo define a quién se prioriza relevar. Los tres usuarios identificados (U1, U2 y U3) pertenecen a este grupo primario.

> ✅ **Validado en el TP2:** la elección del Conductor como usuario primario queda confirmada por la evidencia. Dos de los tres conductores relevados rechazan explícitamente viajar con desconocidos por seguridad, y el tercero solo acepta bajo condiciones estrictas de validación — confirmando que es, en efecto, el lado del mercado más difícil de convencer.

---

## Perfil real del usuario (TP2)

- **U1:** cursa de noche (aprox. 19hs a 21:45hs), vive en Castelar Norte y se traslada en auto propio. Su horario y recorrido no son fijos: varían según su rutina semanal y la semipresencialidad de las materias que cursa. Tiene 3 asientos libres en su vehículo.
- **U2:** vive en Haedo, sale de su casa a las 18:20hs y regresa a las 22hs. Cursa presencial un solo día a la semana (jueves); el resto de los días es virtual. Suele viajar solo en el auto.
- **U3:** vive en Villa Madero, sale de su casa aprox. a las 17:30hs y cursa de 19 a 22hs. Su horario y recorrido se mantienen fijos durante la semana, salvo los días en que cursa de forma virtual. Suele venir con asientos libres.

Los tres tienen celular propio con datos móviles.

### Necesidades reales

**U1**
- **Certeza sobre quién viaja.** U1 acepta compartir el auto siempre que los pasajeros sean fijos, o que exista la certeza de que son alumnos regulares con antigüedad en la universidad. La validación de identidad no le alcanza por sí sola: pide continuidad o trayectoria.
- **Poder organizarse el mismo día.** U1 declara que usaría la aplicación el mismo día de cursada, desde su casa, para organizar el viaje.
- **Garantías de que el viaje se concreta.** U1 pregunta expresamente qué sucede si organiza una salida y el auto finalmente no sale, si no lo pasan a buscar o si el vehículo se avería, y si existe algún método de reembolso.

**U2**
- **Confianza basada en el vínculo, no en la validación.** U2 no viajaría con un desconocido bajo ninguna condición; solo aceptaría llevar a alguien si ya fuera su amigo, y en ese caso no le pediría nada a cambio.
- **Disponibilidad real acotada.** U2 cursa presencial un solo día a la semana (jueves); el resto de los días es virtual, lo que limita cuántas veces por semana podría ofrecer su auto.
- **Un momento de uso puntual.** U2 usaría la aplicación a la tarde, mientras merienda, antes de salir hacia la facultad.

**U3**
- **Confianza construida charlando, no solo con un perfil validado.** U3 no subiría a un desconocido; si aceptara, antes necesitaría saber su nombre, qué estudia y dónde vive, y que la conversación le genere confianza.
- **Poder reservar el viaje con antelación.** A diferencia de U1, U3 preferiría poder "reservar" el trayecto con anticipación en vez de organizarlo el mismo día.
- **La seguridad como preocupación central.** U3 señala explícitamente que la seguridad es lo que más le preocuparía de usar una aplicación de este tipo.

### Problemas y frustraciones concretas

- **U1:** le preocupa organizar una salida grupal y que "el auto no salga" — que él o algún pasajero cancele, no llegue a horario, o que el vehículo se averíe — sin que exista un mecanismo claro de garantía o reembolso ante ese escenario.
- **U2:** la seguridad de llevar a un desconocido es su principal freno; además, al cursar presencial un solo día a la semana, su disponibilidad real como oferta recurrente es baja.
- **U3:** la seguridad es, literalmente, lo que más le preocupa de una app de este tipo; no subiría a nadie que no conozca sin antes charlar y generar confianza.

### Contexto de uso

- **U1** usaría la aplicación el mismo día que va a cursar, desde su casa, como herramienta de organización antes de salir.
- **U2** la usaría a la tarde, antes de salir de su casa (mientras merienda).
- **U3** preferiría poder reservar el viaje con antelación, no organizarlo en el momento — un patrón de uso distinto al de U1.

---

## Hipótesis de valor (TP2)

**Creemos que** el estudiante Conductor de UNLaM que ya viaja en auto a cursar, con asientos disponibles en su vehículo,

**tiene el problema de** no estar dispuesto a compartir esos asientos con estudiantes desconocidos por temor a su seguridad personal — aceptando como mucho a amigos o conocidos — salvo que exista una forma de generar confianza mucho más fuerte que solo confirmar la condición de alumno regular.

**Nuestra solución es** una plataforma que, además de validar la condición de alumno regular, ayude a construir confianza mostrando el perfil del pasajero (carrera, antigüedad como alumno, viajes previos y calificaciones), permita reservar trayectos con antelación además de organizarlos el mismo día, y ofrezca un mecanismo de garantía ante cancelaciones.

**Sabremos que estamos en lo correcto cuando** conductores validados acepten solicitudes de pasajeros que no conocían previamente (no solo amigos) en una proporción relevante de los casos, y sostengan esos viajes de forma recurrente (ej.: un porcentaje relevante de las solicitudes de desconocidos termina aceptada, y esos trayectos se repiten en más de una ocasión).

*Nota: el hallazgo más consistente de las tres entrevistas es que la seguridad, y no la compensación económica, es la verdadera barrera para que un conductor comparta su auto. La solución original (validar alumno regular + compensación por combustible) ataca solo parte del problema; el mecanismo de generación de confianza entre desconocidos es el punto que el TP3 debería priorizar en el diseño.*

---

## Lista de supuestos — estado tras el TP2

1. **Los estudiantes tienen acceso a celulares para utilizar la aplicación.**
   **Estado: Confirmado.** U1, U2 y U3 confirmaron tener celular propio con datos móviles.

2. **Dispondrán de internet antes, durante y después de concluir el viaje en UNLaMigo.**
   **Estado: Confirmado.** Los tres declararon tener datos móviles disponibles.

3. **Los pasajeros potenciales utilizan hoy el transporte público para llegar a la universidad.**
   **Estado: Sin evidencia (no aplica a esta muestra).** La muestra del TP2 fue exclusivamente de Conductores (usuario primario único). Este supuesto solo puede evaluarse relevando pasajeros, algo que queda fuera del alcance de esta entrega.

4. **Les resulta incómoda la frecuencia y/o el espacio disponible en ese transporte público.**
   **Estado: Sin evidencia (no aplica a esta muestra).** Mismo motivo que el supuesto 3: no se relevaron pasajeros en esta instancia.

5. **Los estudiantes están dispuestos a viajar con compañeros que no conocen previamente, siempre que pertenezcan a la comunidad UNLaM.**
   **Estado: Mayormente refutado.** U2 y U3 fueron explícitos: no viajarían con un desconocido por seguridad, y solo aceptarían amigos (U2) o personas con las que generen confianza charlando antes (U3). U1 es el único que se abre a la idea, y solo si hay validación de alumno regular y preferentemente pasajeros fijos.

6. **Una ganancia económica por combustible es un incentivo suficiente para que el conductor quiera realizar viajes compartidos.**
   **Estado: Refutado como driver principal.** Ninguno de los tres mencionó el dinero como condición. U2 incluso aclaró que si llevara a un amigo no le pediría nada a cambio. El freno no es económico: es la confianza/seguridad.

7. **Existe una coincidencia suficiente de recorridos y horarios entre conductores y pasajeros dentro del mismo segmento como para poder armar viajes compartidos.**
   **Estado: Parcialmente confirmado, con matices.** Los tres cursan de noche en una franja horaria compatible (entrada 19hs aprox., salida entre 21:45 y 22hs). Pero U1 y U3 tienen horarios variables por semipresencialidad, y U2 solo cursa presencial un día a la semana, lo que reduce su disponibilidad real. Además, al ser una muestra 100% de conductores, no se pudo verificar la superposición real con pasajeros.

**Supuesto crítico (supuesto 7):** no se cayó del todo por el lado de los horarios, pero aparecen dos riesgos que lo debilitan: la variabilidad de horarios de dos de los tres conductores por semipresencialidad, y la baja frecuencia presencial de uno de ellos. Sigue sin poder confirmarse la superposición real con pasajeros — ese es el próximo paso necesario para dar por validado este supuesto.

**Hallazgos no previstos en los supuestos originales:**
1. **La confiabilidad operativa del viaje.** Ninguno de los siete supuestos contemplaba qué ocurre cuando el viaje acordado falla (auto que no sale, no pasan a buscar, avería); U1 preguntó si existe un método de reembolso.
2. **La preferencia por pasajeros recurrentes por sobre esporádicos.** U1 pide que sean fijos o con antigüedad como alumnos regulares; la validación puntual de identidad no cubre esa necesidad.
3. **La seguridad personal como barrera dominante, por encima de la validación.** U2 y U3 no aceptarían viajar con un desconocido ni con validación de alumno regular de por medio.
4. **Una disponibilidad y un modo de uso menos uniformes de lo asumido.** La baja frecuencia presencial de U2 y la preferencia de U3 por reservar con antelación muestran que el patrón de uso entre conductores no es homogéneo.

**Supuesto crítico:** el número 7 (coincidencia de recorridos y horarios). Si no existe suficiente superposición geográfica y horaria entre conductores y pasajeros, no hay viajes que armar y el producto pierde su razón de ser, independientemente de que el resto de los supuestos se cumplan.
