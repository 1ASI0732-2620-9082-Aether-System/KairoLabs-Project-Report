# Capítulo VIII: Experiment-Driven Development

> Plantilla de estructura para completar el capítulo VIII.

## 8.1. Experiment Planning

La planificación experimental de KairoLabs transforma las creencias de valor del producto en preguntas que puedan responderse mediante evidencia. El propósito es decidir qué necesitamos aprender antes de ampliar la solución, considerando a los dos segmentos objetivo: personal operativo de almacenes farmacéuticos y entidades de salud o gestores farmacéuticos. La unidad de planificación es la pregunta, no la funcionalidad que se desea implementar.

Se parte de las hipótesis Lean UX del capítulo I, las necesidades del capítulo II, las evidencias de implementación del capítulo V y las validaciones del capítulo VI. El proceso comprende cinco actividades: resumir el estado actual, identificar material bruto, formular preguntas experimentables, priorizar el aprendizaje y preparar las tarjetas de experimento. Las tarjetas se vinculan con las hipótesis y métricas de 8.2 para evitar criterios de éxito definidos después de observar los datos.

**Estado de esta planificación:** propuesta documental preparada el 23 de noviembre de 2026. Las prioridades, escalas iniciales y criterios de decisión son decisiones propuestas; no constituyen resultados ni actas de aprobación del equipo. Las ejecuciones técnicas de capítulos anteriores no se presentan como experimentos de impacto de negocio. Los pilotos de tres y seis meses se cuentan desde una futura fecha de inicio autorizada y no se consideran realizados dentro del plazo académico.

### 8.1.1. As-Is Summary

KairoLabs propone apoyar la conservación de productos termosensibles mediante el registro y consulta de condiciones ambientales, identificación de estados críticos y supervisión de establecimientos. El problema de partida es la dependencia de rondas, anotaciones y consolidaciones manuales que podrían demorar la identificación de desviaciones o la preparación de evidencia. Esta descripción proviene del planteamiento y de las entrevistas del proyecto; todavía no representa una línea base cuantificada en establecimientos reales.

| Dimensión | Estado documentado | Evidencia disponible | Incertidumbre que permanece |
| :--- | :--- | :--- | :--- |
| Usuarios y contexto | Se identificaron personal operativo y gestores con necesidades de monitoreo, trazabilidad y supervisión multisede. | Capítulos I y II; entrevistas de validación de 6.3.2. | Frecuencia de tareas, diferencias entre turnos y condiciones efectivas de adopción. |
| Producto | Se documentaron una aplicación web Vue, una API ASP.NET Core con MySQL y módulos de establecimientos, operadores, dispositivos, transportes y suscripciones. | Capítulo V y alcance de las suites de 6.1. | Qué funciones están disponibles en la versión y entorno que se utilizarán para experimentar. |
| Verificación técnica | Se reportaron 20 pruebas unitarias y 14 de integración aprobadas; se añadieron escenarios BDD y de sistema en escritorio y móvil emulado. | 6.1 y evidencias enlazadas del capítulo VI. | Los casos aprobados no demuestran ahorro de tiempo, reducción de pérdidas ni desempeño general en campo. |
| Necesidades observadas | Un participante operativo pidió avisos en el celular y registrar acciones; un gestor sugirió historial exportable y alertas por WhatsApp. | Resúmenes de entrevistas en 6.3.2. | Esas preferencias no prueban que un canal reduzca el tiempo de respuesta ni que una exportación mejore una auditoría. |
| Riesgos de uso | Se documentaron hallazgos de navegación, comprensión y accesibilidad en evaluaciones y auditorías. | 6.3.3 y 6.4. | Cuáles siguen presentes en la versión experimental y cuánto interfieren con las tareas. |
| Datos y operación | Se describieron lecturas, dispositivos, establecimientos y estados ambientales. | Capítulos V y VI. | Disponibilidad de registros longitudinales, identificadores comunes, relojes sincronizados, sensores e instrumentos de referencia. |
| Resultados de negocio | Se formularon metas sobre deterioro, respuesta, auditoría, precisión y supervisión. | 1.2.2.3 y 8.2.1–8.2.2. | No se dispone aquí de una línea base medida ni de resultados de los pilotos de tres o seis meses. |

El estado actual permite preparar pruebas de tareas y revisar la viabilidad de la captura de datos. La evaluación de deterioro o pérdidas requiere además acceso autorizado a establecimientos y registros operativos. El uso de datos sintéticos sirve para verificar el procedimiento de medición; no permite estimar incidentes ni pérdidas reales.

**Fuentes internas:** [hipótesis Lean UX](11-chapter-I-introduction.md#1223-lean-ux-hypothesis-statements), [necesidades de usuarios](21-chapter-II-requirements.md), [implementación](51-chapter-V-implementation.md), [verificación y validación](61-chapter-VI-Verification%26Validation.md) y [diseño experimental](#82-experiment-design).

### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims

El material bruto se clasifica según su naturaleza. Una **suposición** es una creencia todavía no contrastada; una **brecha** señala información ausente; una **idea** propone una intervención y debe descomponerse en sus premisas; una **afirmación** recoge una declaración del proyecto o de participantes. Las afirmaciones de entrevistas se presentan como paráfrasis, no como citas textuales ni como opiniones representativas de toda la población.

| ID | Tipo | Material bruto | Origen | Premisa o conocimiento que debe examinarse | Pregunta vinculada |
| :--- | :--- | :--- | :--- | :--- | :--- |
| RM-01 | Suposición | Consultar condiciones continuamente permitiría reducir deterioro frente a rondas manuales. | 1.2.2.3; hipótesis de monitoreo. | La detección oportuna conduce a acciones capaces de modificar los incidentes, y estos pueden atribuirse documentalmente al almacenamiento. | Q-01 |
| RM-02 | Idea | Incorporar avisos automáticos y un registro de atención. | Entrevista operativa de 6.3.2; propuesta de alertas. | El personal recibe un aviso útil, puede actuar y deja una marca temporal comparable. Se prueba esa premisa antes de elegir WhatsApp u otro canal. | Q-02 |
| RM-03 | Afirmación de participante | Un gestor sugirió un historial exportable para auditorías. | Entrevista del segmento 2 en 6.3.2. | Reunir evidencia completa mediante registros digitales toma menos tiempo que mediante registros manuales equivalentes. | Q-03 |
| RM-04 | Suposición | Automatizar lecturas reduce errores de transcripción y mejora su concordancia. | 1.2.2.3; integración IoT propuesta. | La lectura capturada concuerda con un instrumento de referencia, no solamente con lo que muestra la interfaz. | Q-04 |
| RM-05 | Afirmación del proyecto | La supervisión centralizada permitiría mayor eficiencia y menores pérdidas. | Hipótesis multisede de 1.2.2.3 y 8.2.1. | La información consolidada cambia decisiones y resultados; un menor tiempo de consulta no demuestra por sí solo menores pérdidas. | Q-05 |
| RM-06 | Brecha de conocimiento | No se ha medido la continuidad real de lecturas ni la completitud de los controles programados del piloto. | Diferencia entre pruebas técnicas de 6.1 y datos exigidos en 8.2.2. | Es necesario saber qué datos faltan y si existe exposición suficiente para interpretar los resultados. | Q-06 |
| RM-07 | Brecha de conocimiento | Se desconoce qué combinaciones de turno, conectividad y disponibilidad del responsable dificultan atender las alertas. | Límites de entrevistas y de pruebas con móvil emulado. | Una demora puede deberse al contexto y no a la interfaz o al canal elegido. | Q-07 |
| RM-08 | Brecha de conocimiento | No están establecidos los tiempos basales, la tasa de deterioro ni la variabilidad de las medidas para los establecimientos elegibles. | Insumos necesarios para 8.2.5. | Los umbrales y tamaños de muestra requieren datos basales; una meta no debe tratarse como observación. | Q-08 |

**Tratamiento del material:** se conserva el vínculo con su fuente; se separan observaciones, inferencias y propuestas; y se evita convertir cada solicitud de funcionalidad en una decisión de implementación inmediata. Por ejemplo, la propuesta de WhatsApp origina primero una pregunta sobre oportunidad y atención de avisos, no una conclusión favorable a ese canal.

### 8.1.3. Experiment-Ready Questions

Se formulan preguntas **impulsadas por creencias** (*belief-led*) cuando existe una expectativa contrastable y preguntas **exploratorias** cuando falta conocimiento para definir o interpretar una comparación. Las cinco preguntas principales conservan los objetivos de 8.2.1. Las exploratorias permiten comprobar si se puede ejecutar ese diseño.

| ID | Tipo | Pregunta preparada para investigación | Por qué necesitamos responderla | Evidencia que permitiría responder |
| :--- | :--- | :--- | :--- | :--- |
| Q-01 | Belief-led | En establecimientos elegibles, ¿el uso del monitoreo continuo se asocia con una reducción de al menos 30 % en MD-01 durante tres meses frente a una línea base comparable de tres meses? | Determinar si el beneficio esperado sobre deterioro tiene respaldo operativo. | Incidentes confirmados y lotes expuestos por sede y periodo; contexto de MD-07 y MD-08. |
| Q-02 | Belief-led | Para desviaciones comparables, ¿las notificaciones automáticas reducen al menos 25 % el tiempo mediano entre la primera lectura fuera de rango y la respuesta registrada durante tres meses? | Contrastar si la alerta modifica la atención y no solo produce una notificación. | MD-02 con marcas temporales vinculadas; contexto de MD-07 y MD-08. |
| Q-03 | Belief-led | Ante solicitudes equivalentes de una sede, dispositivo y periodo, ¿el historial digital reduce al menos 20 % el tiempo promedio necesario para entregar evidencia completa frente a la búsqueda manual? | Valorar la utilidad del historial para una tarea concreta de auditoría. | MD-03 en solicitudes completas de ambas condiciones durante el periodo de tres meses de 8.2.5. |
| Q-04 | Belief-led | En mediciones pareadas por variable, lugar y momento, ¿la captura con sensores aumenta al menos 25 % de forma relativa la proporción de lecturas dentro de tolerancia frente al método manual durante tres meses? | Comprobar la confiabilidad de los datos que sustentan las decisiones del producto. | MD-04, con instrumento de referencia y tolerancia predefinida por variable. |
| Q-05 | Belief-led | Durante seis meses, ¿la supervisión multisede reduce al menos 30 % MD-05 y al menos 20 % MD-06 frente al proceso habitual en sedes comparables? | Separar la eficiencia de consulta del impacto económico; se necesitan ambos resultados para respaldar la hipótesis conjunta. | MD-05 en tareas equivalentes y MD-06 en registros de inventario e incidentes; contexto de MD-07. |
| Q-06 | Exploratoria | Durante la preparación del piloto, ¿qué cobertura de establecimientos y qué controles completos y conformes podemos documentar, y en qué situaciones se interrumpe su registro? | Determinar si el sistema y los registros permiten observar lo que las hipótesis requieren. | MD-07 y MD-08, registros de última lectura y observaciones de las causas de ausencia. |
| Q-07 | Exploratoria | ¿Qué barreras de turno, conectividad y disponibilidad aparecen en la secuencia entre una desviación y su atención? | Identificar explicaciones alternativas para MD-02 y delimitar condiciones comparables. | Recorrido contextual de casos de MD-02 y notas de observación; sin crear un indicador de negocio adicional. |
| Q-08 | Exploratoria | ¿Cuáles son los valores basales y la variabilidad de MD-01 a MD-06 en los establecimientos elegibles antes de intervenir? | Calcular escala y factibilidad sin inventar un tamaño de muestra o un beneficio previo. | Registros basales autorizados, denominadores, tiempos y distribución por sede y periodo. |

**Uso de las cinco W y una H.** Para Q-02, **Who** es el personal operativo autorizado; **What**, la atención de desviaciones comparables; **Where**, los establecimientos incluidos; **When**, desde la primera lectura fuera de rango hasta la acción registrada durante el periodo del piloto; **Why**, aprender si las alertas aceleran la respuesta; y **How**, comparar MD-02 entre proceso habitual y proceso con notificación, registrando tipo, severidad y contexto. Este desglose hace explícitas premisas como la disponibilidad del responsable, la conectividad y la sincronización de relojes. Q-07 permite explorar esas premisas antes de atribuir una diferencia a la notificación.

### 8.1.4. Question Backlog

El backlog organiza preguntas de aprendizaje. Su puntuación es una estimación inicial propuesta para discusión del equipo; no proviene de una votación o medición ya realizada.

Se utiliza una escala de 1 a 5:

- **Confianza (C):** 1 significa evidencia pertinente muy limitada; 5, evidencia consistente para responder la pregunta. Las pruebas funcionales no elevan automáticamente la confianza en un beneficio de negocio.
- **Riesgo (R):** 1 representa un costo acotado si la premisa es incorrecta; 5, una consecuencia alta sobre conservación, decisiones o confiabilidad de datos.
- **Impacto (I):** 1 indica que la respuesta cambia una decisión menor; 5, que puede cambiar una decisión central del producto o del experimento.
- **Interés (T):** 1 expresa baja urgencia de aprendizaje y 5, alta urgencia para el siguiente paso del proyecto. Representa interés de investigación del equipo, no popularidad de la función.

La prioridad se calcula como **P = (6 − C) + R + I + T**. Invertir C da mayor prioridad a lo que todavía conocemos menos. Un valor mayor se investiga antes; en empate se elige primero el mayor riesgo. Si también coincide, se atiende la dependencia que desbloquea otras preguntas. La puntuación no reemplaza los requisitos de acceso, medición ni seguridad.

| Orden | Pregunta | C | R | I | T | P | Motivo de priorización y dependencia | Estado propuesto |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :--- | :--- |
| 1 | Q-04. Concordancia de lecturas | 2 | 5 | 5 | 5 | 19 | Una decisión basada en una lectura incorrecta compromete los demás experimentos. Requiere instrumento y tolerancia. | Deep: preparar EXP-04. |
| 2 | Q-02. Respuesta a alertas | 2 | 5 | 5 | 4 | 18 | Es central para el beneficio operativo. Requiere Q-06 y datos basales de Q-08. | Deep: preparar EXP-02; ejecución condicionada. |
| 3 | Q-06. Cobertura y controles | 1 | 4 | 5 | 4 | 18 | Desbloquea la captura para otras preguntas; queda detrás de Q-02 por el desempate de riesgo, pero se ejecuta antes como dependencia. | Deep: preparar EXP-06. |
| 4 | Q-01. Incidentes de deterioro | 1 | 5 | 5 | 2 | 17 | Alto valor y riesgo, pero necesita acceso a registros y seguimiento de tres meses. | Broad: tarjeta EXP-01 preparada; piloto pendiente. |
| 5 | Q-08. Línea base y variabilidad | 1 | 4 | 4 | 4 | 17 | Insumo de escala para todas las comparaciones. Requiere autorización de acceso y registros utilizables. | Deep: actividad basal de las tarjetas principales. |
| 6 | Q-03. Evidencia para auditoría | 2 | 3 | 4 | 5 | 16 | Permite una comparación de tareas acotada. Requiere historial consultable y solicitudes equivalentes. | Deep: preparar EXP-03; confirmar versión. |
| 7 | Q-05. Supervisión y pérdidas | 2 | 4 | 4 | 3 | 15 | Requiere varias sedes y seguimiento económico de seis meses; depende de Q-06 y Q-08. | Broad: tarjeta EXP-05 preparada; piloto pendiente. |
| 8 | Q-07. Barreras de atención | 1 | 3 | 4 | 3 | 15 | Ayuda a explicar diferencias de respuesta. Se explora al preparar EXP-02 y delimitar sus condiciones. | Broad: guía contextual, pendiente de detalle. |

**Broad backlog:** conserva las ocho preguntas y admite nuevas brechas. Q-01, Q-05 y Q-07 mantienen visible el aprendizaje de mayor alcance o menor preparación inmediata. **Deep backlog:** detalla Q-04, Q-02, Q-06, Q-08 y Q-03 hasta identificar responsables, fuentes, condiciones y restricciones. La tarjeta preparada de una pregunta broad no significa que su ejecución esté autorizada o lista.

**Secuencia propuesta:** revisar viabilidad de medición con EXP-06; recoger la línea base de Q-08 y preparar instrumento y tolerancias para EXP-04; ensayar los procedimientos de EXP-02 y EXP-03; y activar los pilotos principales solo cuando estén disponibles sus requisitos y escala. EXP-01 y EXP-05 necesitan compromisos de seguimiento que exceden una sesión de clase. Los ensayos con datos de prueba no sustituyen esos pilotos.

**Mantenimiento:** cada tarjeta tendrá un responsable asignado por el equipo y un revisor distinto antes de ejecutarse. Se conservarán versión del producto, fecha de decisión, protocolo y enlace a evidencia. Tras cada ejecución se actualizarán confianza, estado y prioridad en 8.4.2. La confianza solo aumenta con evidencia pertinente a la pregunta; una ejecución fallida o inconclusa también se registra.

### 8.1.5. Experiment Cards

Las tarjetas registran el diseño mínimo antes de ejecutar. El **frente** captura pregunta, por qué, hipótesis y la *Simplest Useful Thing* (SUT, la cosa más simple y útil). El **reverso** especifica medidas, condiciones y escala. Las cinco primeras se corresponden con las cinco hipótesis de 8.2.1; EXP-06 es exploratoria y comprueba la viabilidad de observarlas.

Se referencian exclusivamente las métricas **MD-01 a MD-08 de 8.2.2**. Los identificadores, las causas de ausencia y las verificaciones de completitud son datos o controles del protocolo, no métricas de negocio nuevas. La escala definitiva se calculará como indica 8.2.5; los periodos de observación no equivalen a tamaños de muestra suficientes.

#### EXP-01. Monitoreo continuo e incidentes de deterioro

| Lado | Campo | Contenido |
| :--- | :--- | :--- |
| Frente | Pregunta y trazabilidad | Q-01; RM-01; primera hipótesis de 8.2.1. |
| Frente | Por qué | Decidir si el monitoreo aporta evidencia de menor deterioro y si merece ampliar el piloto. |
| Frente | Hipótesis | H1: reducción de MD-01 de al menos 30 % frente a la línea base comparable. H0 operativa: reducción menor al 30 %. No alcanzar el umbral no demuestra ausencia de cualquier efecto. |
| Frente | SUT | Usar la consulta de lecturas y un registro controlado de lotes e incidentes en los establecimientos elegibles, antes de construir analítica adicional. |
| Reverso | Medidas | Principal: MD-01. Contexto: MD-07 y MD-08. Comparar tasas con sus denominadores por sede y periodo. |
| Reverso | Condiciones | Línea base del proceso habitual frente a uso de monitoreo continuo. Mantener criterios de incidente, lotes y comparabilidad; documentar cambios de inventario, personal y almacenamiento. |
| Reverso | Escala | Tres meses de piloto y tres meses basales comparables. Lotes e incidentes elegibles; tamaño requerido pendiente de tasa basal y cálculo de 8.2.5 con ajuste por establecimiento. |
| Reverso | Decisión y límites | Evaluar el umbral con el intervalo de incertidumbre y el plan de 8.2.5. Si no hay eventos, denominador suficiente o precisión, informar resultado inconcluso. La comparación antes-después aporta una asociación y tiene limitaciones de atribución causal. |
| Reverso | Requisitos y estado | Acceso autorizado a registros; definición de incidente confirmada; Q-06 y Q-08 resueltas lo suficiente para medir. **Planificado; no ejecutado en esta sección.** |

#### EXP-02. Alertas y tiempo de respuesta

| Lado | Campo | Contenido |
| :--- | :--- | :--- |
| Frente | Pregunta y trazabilidad | Q-02; RM-02; segunda hipótesis de 8.2.1. |
| Frente | Por qué | Decidir si la notificación ayuda a actuar oportunamente y qué aspectos del flujo necesitan revisión. |
| Frente | Hipótesis | H1: reducción de MD-02 de al menos 25 %. H0 operativa: reducción menor al 25 %. La referencia de 15 a 10 minutos de 8.2.2 es una meta de planificación; no una línea base ya medida. |
| Frente | SUT | Un flujo verificable de aviso y registro de acción vinculado a la lectura. Comprobar primero su disponibilidad en la versión experimental; no presuponer que WhatsApp o un canal móvil ya están implementados. |
| Reverso | Medidas | Principal: MD-02. Contexto: MD-07 y MD-08. Capturar lectura inicial fuera de rango, identificador de alerta y acción; sincronizar relojes. |
| Reverso | Condiciones | Proceso habitual frente a proceso con notificación automática; comparar tipo y severidad equivalentes y registrar turno y conectividad. No retirar controles de conservación ni alertas obligatorias. |
| Reverso | Escala | Piloto de tres meses. Tamaño requerido según distribución basal de tiempos y remuestreo de 8.2.5, considerando dependencia por operador y sede. |
| Reverso | Decisión y límites | Evaluar la reducción de medianas con su incertidumbre. Conservar las desviaciones no atendidas y registros incompletos como incidencias del protocolo; no eliminarlos silenciosamente ni usar únicamente respuestas rápidas. Si impiden una comparación confiable, declarar el límite o resultado inconcluso. |
| Reverso | Requisitos y estado | Notificación y registro trazables; reglas previas para elegibilidad, seguimiento y datos faltantes; Q-06, Q-07 y Q-08. **Planificado; no ejecutado en esta sección.** |

#### EXP-03. Historial digital y preparación de auditoría

| Lado | Campo | Contenido |
| :--- | :--- | :--- |
| Frente | Pregunta y trazabilidad | Q-03; RM-03; tercera hipótesis de 8.2.1. |
| Frente | Por qué | Decidir si el historial resuelve la búsqueda de evidencia requerida por los gestores. |
| Frente | Hipótesis | H1: reducción de MD-03 de al menos 20 %. H0 operativa: reducción menor al 20 %. |
| Frente | SUT | Consultar el historial disponible para responder solicitudes acotadas por sede, dispositivo y periodo. No desarrollar una exportación completa antes de comprobar la utilidad de la tarea básica. |
| Reverso | Medidas | MD-03. La entrega debe contener el conjunto solicitado en ambas condiciones; una búsqueda incompleta no se cuenta como una respuesta rápida satisfactoria. |
| Reverso | Condiciones | Solicitudes equivalentes mediante registros manuales y consulta digital. Usar conjuntos distintos pero comparables y contrabalancear el orden para reducir aprendizaje; registrar experiencia previa. |
| Reverso | Escala | Observación prevista de tres meses según 8.2.5. Número de participantes y solicitudes pendiente de variabilidad basal y diseño pareado; varias tareas de una persona no equivalen a varios participantes independientes. |
| Reverso | Decisión y límites | Comparar tiempos y su incertidumbre solo con el protocolo de completitud y fallos predefinido. Si la versión no permite recuperar el historial requerido, registrar la falta de preparación; una maqueta no acredita la eficacia del producto implementado. |
| Reverso | Requisitos y estado | Historial accesible, datos autorizados y solicitudes preparadas antes de medir. **Planificado; no ejecutado en esta sección.** |

#### EXP-04. Concordancia del registro mediante sensores

| Lado | Campo | Contenido |
| :--- | :--- | :--- |
| Frente | Pregunta y trazabilidad | Q-04; RM-04; cuarta hipótesis de 8.2.1. |
| Frente | Por qué | Decidir si las lecturas almacenadas son una base confiable para interpretar alertas y resultados posteriores. |
| Frente | Hipótesis | H1: aumento relativo de MD-04 de al menos 25 % frente al registro manual. H0 operativa: aumento relativo menor al 25 %. |
| Frente | SUT | Registrar lecturas pareadas del sensor, del procedimiento manual y de un instrumento de referencia, con variable, lugar, instante y tolerancia identificados. |
| Reverso | Medidas | MD-04 según 8.2.2. Definir la tolerancia por variable antes de recoger datos y registrar la evidencia de calibración del instrumento. |
| Reverso | Condiciones | Captura automática y manual bajo condiciones comparables, contrastadas con el mismo instrumento. La transmisión correcta por la API no demuestra concordancia física. No provocar desviaciones en inventario real. |
| Reverso | Escala | Tres meses previstos; pares de lecturas según cálculo de 8.2.5. Considerar agrupamiento por dispositivo y establecimiento y correlación temporal; lecturas consecutivas no son réplicas independientes. |
| Reverso | Decisión y límites | Calcular mejora relativa e incertidumbre. Si la precisión basal supera 80 %, mejorarla 25 % de forma relativa exigiría superar 100 % y el objetivo no sería factible. Revisar y versionar el umbral junto con 8.2 antes de la prueba; si la base es cero, no calcular mejora relativa. |
| Reverso | Requisitos y estado | Sensores e instrumento disponibles; tolerancias, tasa basal y factibilidad del umbral revisadas. **Planificado; no ejecutado en esta sección.** |

#### EXP-05. Supervisión multisede y pérdidas documentadas

| Lado | Campo | Contenido |
| :--- | :--- | :--- |
| Frente | Pregunta y trazabilidad | Q-05; RM-05; quinta hipótesis de 8.2.1. |
| Frente | Por qué | Decidir si centralizar información mejora la revisión operativa y si existe evidencia separada de beneficio económico. |
| Frente | Hipótesis | H1: reducción de al menos 30 % en MD-05 y 20 % en MD-06. H0 operativa: al menos uno de los dos umbrales no se alcanza. |
| Frente | SUT | Tareas equivalentes con el dashboard existente y un registro autorizado de pérdidas e inventario, sin construir un módulo financiero adicional. |
| Reverso | Medidas | MD-05 y MD-06 como resultados separados; MD-07 como contexto de cobertura. No inferir pérdidas evitadas a partir de clics, consultas o tiempo de tarea. |
| Reverso | Condiciones | Revisión centralizada frente a revisión habitual de las mismas sedes o de sedes comparables. Contrabalancear las tareas y documentar diferencias de inventario, periodo y personal para el componente económico. |
| Reverso | Escala | Seis meses según 8.2.5. Número de gestores, sedes, tareas y registros pendiente de la línea base; estimar escala para ambos resultados y considerar agrupamiento por sede. |
| Reverso | Decisión y límites | Evaluar cada umbral con su incertidumbre. Si solo mejora el tiempo, documentar respaldo parcial para la eficiencia, sin afirmar reducción de pérdidas ni aprobación de la hipótesis conjunta. Base económica nula o registros insuficientes impiden estimar una reducción relativa confiable. |
| Reverso | Requisitos y estado | Varias sedes elegibles, acceso a inventarios e incidentes, capacidad de seguimiento y Q-06/Q-08. **Planificado; no ejecutado en esta sección.** |

#### EXP-06. Exploración de cobertura y viabilidad de captura

| Lado | Campo | Contenido |
| :--- | :--- | :--- |
| Frente | Pregunta y trazabilidad | Q-06; RM-06; exploración previa a los cinco experimentos de impacto. |
| Frente | Por qué | Aprender si se pueden observar establecimientos y controles de forma suficiente antes de comprometer pilotos extensos. |
| Frente | Hipótesis | No aplica una H1 direccional: se busca conocer cobertura, registros disponibles y causas de ausencia. No se interpreta esta exploración como prueba de las cinco hipótesis. |
| Frente | SUT | Revisar inventario de dispositivos, última lectura y calendario de controles; observar un recorrido de captura y cotejarlo con la API y el registro autorizado. |
| Reverso | Medidas | MD-07 y MD-08. Registrar también el motivo documental de un control no trazable, distinguiendo ausencia de lectura de una lectura existente fuera de rango. |
| Reverso | Condiciones | Entorno de preparación autorizado, con establecimientos y dispositivos identificados. Definir vigencia de lectura, controles programados y datos completos antes de aplicar las fórmulas. |
| Reverso | Escala | Una semana inicial de observación propuesta, con los establecimientos elegibles disponibles. Es una exploración de factibilidad sin pretensión de potencia estadística ni generalización poblacional. |
| Reverso | Decisión y límites | Describir MD-07 y MD-08 y las restricciones encontradas. Preparar los pilotos cuando cada campo esencial pueda capturarse y vincularse; si no, revisar instrumentación y volver a observar. Las metas de seis meses de 8.2.2 no se declaran alcanzadas por observar una semana. |
| Reverso | Requisitos y estado | Acceso de lectura, inventario y calendario acordados, responsable y revisor designados. **Propuesto; no ejecutado en esta sección.** |

**Reglas comunes antes de ejecutar**

1. Asignar responsable y revisor, fijar versión de la aplicación y verificar que estén disponibles las funciones utilizadas. La validación con móvil emulado no acredita una aplicación móvil nativa ni pruebas en dispositivos físicos.
2. Registrar consentimiento cuando participen usuarios, limitar los datos a los necesarios y usar identificadores seudónimos. Conservar los procedimientos habituales de conservación; no inducir deterioro ni retirar medidas de protección para construir un control.
3. Versionar hipótesis, métricas, condiciones, reglas de exclusión y análisis antes de observar resultados. Usar el cálculo de 8.2.5 con datos basales; el 5 % de significancia y el 80 % de potencia son objetivos de diseño, no garantías ya demostradas.
4. Distinguir el umbral de relevancia práctica de la prueba estadística de ausencia de efecto. Las H0 operativas de 8.2.1 son criterios de negocio; no se obtiene un valor p comparando solamente un porcentaje con una meta. La especificación inferencial debe corresponder a la unidad de análisis y a los umbrales antes de ejecutar.
5. Conservar registros incompletos, incidencias y diferencias entre periodos en el informe de ejecución. Un resultado inconcluso no equivale a confirmar ni refutar automáticamente una creencia.
6. Documentar el aprendizaje y la decisión de continuar, ajustar o detener en 8.4, y actualizar las prioridades en 8.4.2. Las capturas previas de la aplicación solo acreditan interfaces y contexto; los resultados de estos experimentos requieren sus propios registros.

**Correspondencia con el diseño:** EXP-01 a EXP-05 mantienen las cinco preguntas, los umbrales y los periodos previstos en 8.2. EXP-06 prepara su viabilidad. Antes de ejecutar debe revisarse la consistencia del capítulo completo: los 15 minutos de MD-02 requieren medición basal; el aumento relativo de 25 % de MD-04 requiere comprobar su factibilidad; y las metas generales de MD-05 y MD-06 deben distinguirse de los umbrales específicos de EXP-05. No se modifican silenciosamente esas definiciones después de medir.

## 8.2. Experiment Design

Esta sección presenta el diseño experimental de KairoLabs para contrastar nuestras hipótesis con evidencia. Integra la formulación de hipótesis, las métricas de negocio y medidas, las condiciones y escala de las pruebas, la selección de métodos, los objetivos de analítica, los indicadores clave y el seguimiento web y móvil. El diseño considera las necesidades del personal operativo de almacenes farmacéuticos y de los gestores de salud, y permite relacionar los resultados observados con decisiones concretas sobre el producto.

### 8.2.1. Hypotheses

Formulamos cinco hipótesis comprobables a partir de las necesidades del personal operativo y de los gestores de salud, así como de las funciones de monitoreo, alertas, trazabilidad, sensores y supervisión multisede de KairoLabs. Cada hipótesis establece un resultado medible y su hipótesis nula define el umbral que consideramos insuficiente para respaldar nuestra creencia. Las comparaciones se realizan respecto de una línea base; para evaluar la precisión de las lecturas, se contrastan los datos del sensor con un instrumento de referencia y una tolerancia previamente establecida.

| Question (Pregunta) | Belief (Creencia) | Hypothesis (Hipótesis de trabajo, H1) | Null Hypothesis (Hipótesis nula operativa, H0) |
| :--- | :--- | :--- | :--- |
| ¿El monitoreo continuo ayuda a reducir los incidentes de deterioro de medicamentos? | Creemos que las rondas y los registros manuales pueden dejar pasar desviaciones entre revisiones. Consultar lecturas continuas permitiría reconocer antes una condición crítica. | En los primeros tres meses del piloto, la tasa de incidentes de deterioro asociados a condiciones de almacenamiento disminuirá al menos **30 %** frente a la línea base de los mismos establecimientos. | La tasa de incidentes no alcanzará la reducción mínima del **30 %** frente a la línea base. |
| ¿Las alertas automáticas ayudan al personal a responder más rápido ante una desviación? | Creemos que una alerta inmediata puede acortar el tiempo entre detectar una lectura fuera de rango y registrar una acción. En la validación, el personal operativo prefirió recibir avisos en el celular y pidió poder registrar cómo atendió la alerta. | Durante el piloto, el tiempo mediano entre una lectura fuera de rango y el registro de una respuesta disminuirá al menos **25 %** frente al proceso sin notificación automática. | La reducción del tiempo mediano de respuesta será menor al **25 %**. |
| ¿El historial digital facilita reunir evidencia para una auditoría sanitaria? | Creemos que los registros en papel pueden quedar incompletos y tomar tiempo para reunirlos. En la entrevista de validación, el gestor sugirió contar con un historial exportable para auditorías. | Durante los primeros tres meses, el tiempo promedio para reunir los registros solicitados disminuirá al menos **20 %** frente al proceso manual. | La reducción del tiempo para reunir evidencia será menor al **20 %**. |
| ¿El registro automático mediante sensores mejora la precisión de las lecturas? | Creemos que transcribir varias lecturas al día añade trabajo y oportunidades de error. La integración de sensores IoT permitirá automatizar el registro y comparar sus lecturas con un instrumento de referencia. | En un piloto de tres meses, la proporción de lecturas correctas aumentará al menos **25 %** frente al registro manual. Se contrastará cada lectura con un instrumento de referencia y una tolerancia definida antes de la prueba. | El aumento de lecturas correctas será menor al **25 %**. |
| ¿La gestión centralizada mejora la eficiencia de supervisión y reduce las pérdidas entre varias sedes? | Creemos que los gestores que supervisan más de un almacén necesitan consolidar registros. En la validación, el gestor consideró útil revisar sus sedes desde un solo lugar y pudo registrar un establecimiento y asignarle un operador sin ayuda. | Durante los primeros seis meses, el dashboard multisede reducirá al menos **30 %** el tiempo promedio para revisar el estado de todos los establecimientos y disminuirá al menos **20 %** las pérdidas económicas documentadas por incidentes de almacenamiento, frente a la línea base. | La hipótesis no se respaldará si la reducción queda por debajo de **30 %** en el tiempo de supervisión o de **20 %** en las pérdidas económicas. |

**Lectura de las hipótesis y criterios de decisión**

Las cinco hipótesis se derivan de necesidades del proyecto y vinculan cada problema con un resultado que podemos observar: detección de incidentes, respuesta a alertas, preparación de evidencia, precisión de lecturas y eficiencia multisede. En la última hipótesis, el tiempo de supervisión y las pérdidas económicas son dos resultados relacionados con la gestión centralizada.

Para interpretar los resultados:

- **H1** expresa el cambio que esperamos observar y el umbral que respaldaría nuestra creencia.
- **H0** establece que ese umbral no se alcanza; por tanto, el resultado no respalda la hipótesis de trabajo.
- Si los datos respaldan **H0**, revisaremos las condiciones y los resultados, ajustaremos el diseño o reconsideraremos el supuesto antes de decidir si continuamos con la funcionalidad.

### 8.2.2. Domain Business Metrics

Las métricas de dominio permiten determinar si KairoLabs aporta valor a la conservación de medicamentos, la respuesta ante desviaciones, la trazabilidad y la eficiencia de los almacenes. Cada experimento se evaluará con las métricas definidas en esta tabla y sus metas se compararán con una línea base del mismo contexto de uso. Las visitas, impresiones o clics podrán describir la interacción con la plataforma, pero no se considerarán por sí solos evidencia de impacto de negocio.

| ID / nombre de la métrica | Descripción y vínculo con el objetivo de negocio | Fórmula de cálculo | Técnica de recolección | Meta deseada |
| :--- | :--- | :--- | :--- | :--- |
| **MD-01. Tasa de incidentes de deterioro** | Mide la frecuencia de incidentes en los que un medicamento se deteriora por una desviación ambiental. Se vincula con la meta de proteger la conservación y reducir pérdidas de productos farmacéuticos. | `Tasa = (incidentes confirmados de deterioro / lotes monitoreados) × 100`.<br>`Reducción = ((tasa base − tasa piloto) / tasa base) × 100`. | Consolidamos los incidentes con sede, fecha, condición ambiental, dispositivo y lote afectado; contrastamos cada caso con las lecturas y el registro de disposición del producto. | Reducir la tasa al menos **30 %** frente a la línea base durante los primeros tres meses. |
| **MD-02. Tiempo de respuesta a desviaciones** | Mide cuánto tarda el personal en registrar una acción desde la primera lectura fuera del rango de conservación. Refleja la capacidad de reaccionar oportunamente ante alertas. | `Mediana(hora de registro de la acción − hora de la primera lectura fuera de rango)`, en minutos. | Comparamos las marcas de tiempo de las lecturas con las del registro de atención de la alerta o incidente en la plataforma. | Reducir el tiempo de referencia de **15 a 10 minutos o menos** (mejora de **33,3 %**), superando el umbral experimental de 25 %. |
| **MD-03. Tiempo de preparación de evidencia para auditoría** | Mide el tiempo requerido para reunir el historial de conservación solicitado para revisar una sede, dispositivo o periodo. Se vincula con la trazabilidad y la eficiencia de las auditorías sanitarias. | `Tiempo promedio = suma de minutos de solicitudes completadas / número de solicitudes completadas`.<br>`Reducción = ((promedio manual − promedio digital) / promedio manual) × 100`. | Registramos el inicio de cada solicitud de evidencia y el momento en que se entrega el conjunto de lecturas requerido; comparamos solicitudes equivalentes por búsqueda manual y consulta digital. | Reducir el tiempo promedio al menos **20 %** frente al proceso manual. |
| **MD-04. Precisión de lecturas ambientales** | Mide la concordancia de las lecturas almacenadas por KairoLabs con un instrumento de referencia. La precisión de los datos respalda decisiones confiables sobre la conservación. | `Precisión = (pares de lecturas dentro de tolerancia / pares válidos) × 100`.<br>`Mejora relativa = ((precisión con sensores − precisión manual) / precisión manual) × 100`. | Registramos lecturas simultáneas del sensor y del instrumento de referencia en condiciones comparables; clasificamos cada par según la tolerancia establecida para la variable. | Aumentar la proporción de lecturas correctas al menos **25 %** en términos relativos frente al método manual. |
| **MD-05. Tiempo de supervisión multisede** | Mide el tiempo para revisar el estado de todos los establecimientos asignados a un gestor e identificar cuáles requieren atención. Se vincula con la eficiencia operativa y la supervisión centralizada. | `Tiempo promedio = suma del tiempo de revisión de establecimientos / número de revisiones completadas`.<br>`Reducción = ((tiempo base − tiempo con dashboard) / tiempo base) × 100`. | Cronometramos tareas equivalentes: localizar todas las sedes, identificar su estado y reconocer los casos que requieren atención. Registramos inicio, finalización y tarea completada. | Reducir **20 %** los tiempos de gestión operativa de los almacenes y, específicamente, al menos **30 %** el tiempo de revisión multisede durante los primeros seis meses. |
| **MD-06. Tasa de pérdidas económicas por almacenamiento** | Cuantifica el valor de los medicamentos dañados o descartados por incidentes ambientales en relación con el valor del inventario monitoreado. Complementa la tasa de incidentes con su impacto económico. | `Tasa = (valor de productos dañados o descartados por incidentes / valor del inventario monitoreado) × 100`.<br>`Reducción = ((tasa base − tasa piloto) / tasa base) × 100`. | Contrastamos los registros de incidentes con actas de baja, devolución o cuarentena y con el valor documentado de los productos afectados y del inventario monitoreado. | Reducir las pérdidas al menos **30 %** a nivel general y **20 %** en establecimientos con supervisión multisede, frente a sus respectivas líneas base. |
| **MD-07. Cobertura de establecimientos monitoreados** | Mide la proporción de establecimientos del alcance con dispositivos activos que reportan lecturas vigentes. Refleja la cobertura y continuidad del monitoreo multisede. | `Cobertura = (establecimientos con dispositivo activo y lectura vigente / establecimientos incluidos) × 100`. | Revisamos el inventario de establecimientos y dispositivos junto con la marca de tiempo de la última lectura recibida por cada dispositivo. | Mantener conectados y monitoreados en tiempo real al menos **80 %** de los establecimientos incluidos durante los primeros seis meses. |
| **MD-08. Controles de conservación conformes y trazables** | Mide la proporción de controles programados con evidencia completa y lecturas dentro del rango configurado. Cada registro identifica fecha y lugar, dispositivo, variable, valor y estado; así se puede revisar el cumplimiento documentado de las condiciones de almacenamiento. | `Controles conformes y trazables = (controles con lectura dentro del rango y registro completo / controles programados) × 100`. | Contrastamos el calendario de controles con el historial de lecturas y verificamos fecha, hora, establecimiento, dispositivo, variable, valor, rango aplicable y estado. | Alcanzar **100 %** de controles programados conformes y trazables durante los primeros seis meses de uso. |

Estas métricas conforman el marco común para evaluar los experimentos de KairoLabs: cada resultado se interpreta junto con su línea base, su periodo de observación y la meta correspondiente, evitando tomar actividad digital aislada como prueba de valor para el negocio.

### 8.2.3. Measures

Las medidas especifican qué evidencia recogeremos para responder las preguntas de los cinco experimentos. Seleccionamos como medidas principales los resultados de negocio definidos en **8.2.2**; las medidas secundarias aportan contexto para interpretar esos resultados y comprobar que las funciones de monitoreo, alertas, trazabilidad y supervisión multisede estuvieron disponibles durante la observación. Cada medida es representativa del cambio que plantea su hipótesis y se limita a los datos necesarios para evaluarlo.

| Hipótesis | Medida principal | Evidencia secundaria | Recolección y alcance |
| :--- | :--- | :--- | :--- |
| **H1. Monitoreo continuo y deterioro** | **MD-01. Tasa de incidentes de deterioro:** comparar la tasa del piloto con la línea base de los mismos establecimientos durante los primeros tres meses. | **MD-07. Cobertura de establecimientos monitoreados** y **MD-08. Controles de conservación conformes y trazables**. Permiten interpretar la tasa considerando qué proporción del entorno estuvo efectivamente monitoreada y documentada. | Consolidar incidentes confirmados, lotes monitoreados y registros de lectura con sede y fecha. Revisar únicamente establecimientos incluidos en el piloto y el periodo de comparación establecido. |
| **H2. Alertas y tiempo de respuesta** | **MD-02. Tiempo de respuesta a desviaciones:** medir la mediana entre la primera lectura fuera de rango y el registro de la acción, y compararla con el proceso sin notificación automática. | **MD-07. Cobertura de establecimientos monitoreados** y **MD-08. Controles de conservación conformes y trazables**, para identificar si la lectura y el registro de atención están disponibles para la comparación. | Usar las marcas de tiempo de lecturas y atenciones de alertas vinculadas al mismo incidente. Incluir solo desviaciones con hora de detección y respuesta registradas en el periodo del piloto. |
| **H3. Historial digital y evidencia de auditoría** | **MD-03. Tiempo de preparación de evidencia para auditoría:** comparar el tiempo promedio para completar solicitudes equivalentes mediante búsqueda manual y consulta del historial digital. | **MD-08. Controles de conservación conformes y trazables**, para confirmar que el conjunto solicitado contiene los datos necesarios para revisar el periodo, la sede y el dispositivo. | Registrar el inicio de cada solicitud y la entrega de los registros requeridos. Medir solicitudes comparables y limitar la revisión a los historiales y periodos incluidos en la prueba. |
| **H4. Sensores y precisión de lecturas** | **MD-04. Precisión de lecturas ambientales:** comparar la proporción de lecturas dentro de tolerancia con el instrumento de referencia frente a la proporción correcta del registro manual. | **MD-07. Cobertura de establecimientos monitoreados** y **MD-08. Controles de conservación conformes y trazables**, para contextualizar las lecturas recibidas y verificar su integridad. | Recoger pares de lecturas del sensor y del instrumento de referencia, junto con los registros manuales correspondientes, en condiciones y momentos comparables. Evaluar las variables y tolerancias definidas para la prueba; excluir pares incompletos o no comparables. |
| **H5. Supervisión multisede y pérdidas** | **MD-05. Tiempo de supervisión multisede:** comparar el tiempo promedio para revisar todas las sedes e identificar las que requieren atención. | **MD-06. Tasa de pérdidas económicas por almacenamiento**, como resultado de negocio complementario, y **MD-07. Cobertura de establecimientos monitoreados**, para interpretar el alcance de la supervisión. | Cronometrar revisiones equivalentes con la línea base y el dashboard. Para las pérdidas, contrastar incidentes con documentos de baja, devolución o cuarentena y el valor registrado de los productos afectados, durante el periodo de comparación. |

La recolección se restringe a lecturas ambientales, incidentes, acciones sobre alertas, solicitudes de evidencia, revisiones multisede y documentos que sustentan pérdidas. Conservamos las marcas de tiempo y los datos de sede, dispositivo y lote solo cuando son necesarios para relacionar una observación con su contexto. No usamos impresiones, clics ni actividad general como evidencia de éxito: las señales técnicas de registros y trazas sirven para explicar interrupciones o datos incompletos, mientras que la decisión sobre cada hipótesis se basa en las medidas de negocio anteriores.

### 8.2.4. Conditions

Las condiciones describen el escenario en que recogeremos cada medida y permiten distinguir el efecto de la propuesta de otros factores del entorno. Para cada hipótesis establecemos una condición experimental, que incorpora la función evaluada, y una condición de control, que conserva el proceso de referencia asociado a **H0**. En cada comparación mantenemos equivalentes, en lo posible, los establecimientos, periodos, tareas y criterios de registro, de modo que las diferencias observadas puedan relacionarse con el cambio evaluado.

**Hipótesis 1. Monitoreo continuo y deterioro**

| Elemento | Condición |
| :--- | :--- |
| **Question** | ¿El monitoreo continuo ayuda a reducir los incidentes de deterioro de medicamentos? |
| **Condición Experimental** | Los establecimientos utilizan las lecturas ambientales continuas de KairoLabs para observar las condiciones de conservación y reconocer desviaciones. |
| **Condición de Control** | El personal mantiene el proceso habitual de rondas y registros manuales, sin consultar el monitoreo continuo de KairoLabs para detectar desviaciones. |

La comparación considera los mismos establecimientos o establecimientos equivalentes, periodos de tres meses y criterios comunes para registrar lotes, desviaciones e incidentes confirmados.

**Hipótesis 2. Alertas automáticas y tiempo de respuesta**

| Elemento | Condición |
| :--- | :--- |
| **Question** | ¿Las alertas automáticas ayudan al personal a responder más rápido ante una desviación? |
| **Condición Experimental** | Ante una lectura fuera de rango, el personal recibe la notificación automática y registra en KairoLabs la acción tomada y su hora. |
| **Condición de Control** | El personal sigue el proceso habitual de revisión y atención, sin recibir la notificación automática de KairoLabs; registra la detección y la acción con el mismo criterio temporal. |

Se comparan desviaciones equivalentes por tipo y severidad, con los mismos rangos ambientales y criterios para registrar la detección y la respuesta.

**Hipótesis 3. Historial digital y evidencia de auditoría**

| Elemento | Condición |
| :--- | :--- |
| **Question** | ¿El historial digital facilita reunir evidencia para una auditoría sanitaria? |
| **Condición Experimental** | El responsable consulta el historial digital de KairoLabs para reunir las lecturas solicitadas de una sede, dispositivo y periodo. |
| **Condición de Control** | El responsable busca los mismos datos en los registros manuales disponibles, sin utilizar el historial digital de KairoLabs. |

Las solicitudes son equivalentes en contenido y alcance, y utilizan el mismo perfil de responsable, periodo de registros y criterio para determinar cuándo la búsqueda está completa.

**Hipótesis 4. Sensores y precisión de lecturas**

| Elemento | Condición |
| :--- | :--- |
| **Question** | ¿El registro automático mediante sensores mejora la precisión de las lecturas ambientales? |
| **Condición Experimental** | Las lecturas ambientales se capturan automáticamente con los sensores integrados en KairoLabs. |
| **Condición de Control** | Las lecturas se obtienen mediante el procedimiento manual utilizado como referencia, sin sustituirlo por la captura automática. |

Se registran las mismas variables y ubicaciones en momentos y condiciones ambientales comparables. Ambos registros se contrastan con el mismo instrumento de referencia y la tolerancia establecida para cada variable.

**Hipótesis 5. Supervisión multisede y pérdidas**

| Elemento | Condición |
| :--- | :--- |
| **Question** | ¿La gestión centralizada mejora la eficiencia de supervisión y reduce las pérdidas entre varias sedes? |
| **Condición Experimental** | El gestor consulta el dashboard de KairoLabs para revisar en una sola vista el estado de las sedes asignadas e identificar cuáles requieren atención. |
| **Condición de Control** | El gestor revisa la información de cada sede por separado mediante el proceso y los registros habituales, sin el dashboard multisede. |

Se mantienen equivalentes las sedes asignadas, el periodo de información, las tareas de revisión y los criterios para identificar una sede que requiere atención. Para comparar pérdidas, se consideran periodos y registros de incidentes equivalentes.

En todas las comparaciones, el personal mantiene las prácticas necesarias para conservar los medicamentos y atender desviaciones; la condición de control representa el proceso habitual y no implica omitir acciones de seguridad. La población de interés está formada por personal operativo que registra o atiende condiciones de almacenamiento y gestores responsables de uno o más almacenes farmacéuticos. Estas condiciones delimitan la interpretación de los resultados al contexto de uso de KairoLabs.

### 8.2.5. Scale Calculations and Decisions

La escala se define para cada experimento según su variable, unidad de análisis y periodo de observación. En las cinco comparaciones usamos **α = 5 %** como nivel de significancia y **80 %** como potencia estadística objetivo. El MDE corresponde al umbral cuantitativo de cada H1; el tamaño de muestra se calcula con la tasa base o la variabilidad observada en la condición de control, evitando asignar el mismo número de observaciones a resultados diferentes.

**Experimento 1 — Validación del monitoreo continuo**

| Parámetro | Valor | Justificación |
| :--- | :--- | :--- |
| Nivel de significancia (α) | **5 %** | Limita la probabilidad de concluir que el monitoreo reduce los incidentes cuando la diferencia observada se debe al azar. |
| Potencia estadística (1−β) | **80 %** | Proporciona una probabilidad objetivo de detectar la reducción planteada si el efecto existe. |
| MDE | **30 % de reducción** en la tasa de incidentes de deterioro. | Corresponde al umbral definido para respaldar H1. |
| Duración | **Tres meses** de piloto, comparados con una línea base de igual duración. | Permite contrastar periodos equivalentes en los mismos establecimientos o en establecimientos comparables. |
| Tamaño de muestra | Todos los lotes monitoreados y todos los incidentes confirmados en los establecimientos elegibles durante el periodo. El número de lotes requerido se calcula con la tasa basal, la razón objetivo **0,70**, α y potencia, con ajuste por establecimiento. | La unidad de exposición es el lote monitoreado; considerar el agrupamiento por establecimiento evita tratar observaciones correlacionadas como independientes. |

**Decisión:** respaldamos H1 si la reducción estimada alcanza el MDE y la comparación es compatible con el nivel de significancia establecido. Si la precisión del intervalo no permite distinguir el umbral, el resultado se interpreta como inconcluso.

**Experimento 2 — Validación de las alertas automáticas**

| Parámetro | Valor | Justificación |
| :--- | :--- | :--- |
| Nivel de significancia (α) | **5 %** | Limita los falsos positivos al atribuir a las alertas una reducción del tiempo de respuesta. |
| Potencia estadística (1−β) | **80 %** | Define la probabilidad objetivo de detectar el cambio esperado en los tiempos de respuesta. |
| MDE | **25 % de reducción** en el tiempo mediano de respuesta. | Coincide con el umbral de H1 para comparar la notificación automática con el proceso habitual. |
| Duración | **Tres meses** de observación del piloto. | Recoge desviaciones a lo largo de un periodo común con los experimentos de monitoreo y sensores. |
| Tamaño de muestra | Todas las desviaciones elegibles que tengan hora de detección y hora de respuesta registradas en ambas condiciones. El número requerido se estima mediante simulación o remuestreo de la distribución de tiempos, con α y potencia establecidos. | La medida es una mediana; la escala se basa en la distribución de tiempos y no en una suposición de normalidad de medias. |

**Decisión:** respaldamos H1 si el tiempo mediano disminuye al menos 25 % frente al proceso habitual. Desviaciones sin marcas de tiempo comparables no forman parte del análisis.

**Experimento 3 — Validación del historial digital**

| Parámetro | Valor | Justificación |
| :--- | :--- | :--- |
| Nivel de significancia (α) | **5 %** | Limita los falsos positivos en la comparación del tiempo de preparación de evidencia. |
| Potencia estadística (1−β) | **80 %** | Establece la probabilidad objetivo de detectar la reducción esperada. |
| MDE | **20 % de reducción** en el tiempo promedio para reunir evidencia. | Corresponde al umbral de H1 frente a la búsqueda manual. |
| Duración | **Tres meses** de observación. | Permite recoger solicitudes de evidencia en el mismo periodo de comparación del piloto. |
| Tamaño de muestra | Solicitudes equivalentes de registros, medidas tanto con búsqueda manual como con consulta digital. `n = ((Z₁₋α + Z₁₋β) × σd / Δ)²`, donde `σd` es la desviación estándar de las diferencias pareadas y `Δ` equivale al 20 % del tiempo medio de referencia. | La comparación de las mismas solicitudes controla diferencias en sede, dispositivo, periodo y contenido requerido. |

**Decisión:** respaldamos H1 si el tiempo promedio de consulta digital disminuye al menos 20 % frente a la búsqueda manual y la precisión de la estimación es suficiente para distinguir ese umbral.

**Experimento 4 — Validación de las lecturas de sensores**

| Parámetro | Valor | Justificación |
| :--- | :--- | :--- |
| Nivel de significancia (α) | **5 %** | Limita los falsos positivos al atribuir a los sensores una mejora de precisión. |
| Potencia estadística (1−β) | **80 %** | Define la probabilidad objetivo de detectar la mejora planteada. |
| MDE | **25 % de mejora relativa** en la proporción de lecturas correctas respecto del registro manual. | Mantiene el criterio cuantitativo de H1 y de MD-04. |
| Duración | **Tres meses** de lecturas emparejadas. | Abarca las variables y ubicaciones consideradas durante el piloto. |
| Tamaño de muestra | Todos los pares válidos de lecturas del sensor y del método manual, contrastados con el mismo instrumento de referencia. El número requerido se calcula para proporciones pareadas (prueba de McNemar), usando la proporción esperada de pares discordantes, α y potencia. | El emparejamiento y la tolerancia común permiten comparar la precisión de ambos métodos en condiciones equivalentes. |

**Decisión:** respaldamos H1 si la proporción de lecturas correctas con sensores mejora al menos 25 % en términos relativos. Los pares incompletos o tomados bajo condiciones no comparables se excluyen con el mismo criterio en ambas condiciones.

**Experimento 5 — Validación de la supervisión multisede**

| Parámetro | Valor | Justificación |
| :--- | :--- | :--- |
| Nivel de significancia (α) | **5 %** | Limita los falsos positivos para los resultados de tiempo y pérdidas económicas. |
| Potencia estadística (1−β) | **80 %** | Es la probabilidad objetivo de detectar cada cambio mínimo planteado. |
| MDE | **30 % de reducción** en tiempo de revisión y **20 % de reducción** en la tasa de pérdidas económicas. | Son los dos umbrales de H1 y corresponden a MD-05 y MD-06. |
| Duración | **Seis meses** de observación multisede. | Corresponde al periodo establecido para evaluar supervisión y pérdidas económicas. |
| Tamaño de muestra | Todas las revisiones multisede comparables y todos los incidentes con pérdidas documentadas en los establecimientos incluidos. Se calcula por separado el número requerido para el tiempo de revisión y para la tasa de pérdidas, usando la variabilidad o tasa basal correspondiente. | Los dos resultados tienen unidades distintas; cada uno debe alcanzar su propia escala objetivo para evaluar H1. |

**Decisión:** respaldamos H1 solo si ambos resultados alcanzan sus MDE respectivos. Si uno no alcanza su umbral o no tiene precisión suficiente, se informa por separado y la hipótesis conjunta no se considera respaldada.

En todos los experimentos, los establecimientos, responsables, tareas y criterios de inclusión se mantienen representativos del uso de KairoLabs en almacenes farmacéuticos. Se informan el número de observaciones válidas, el efecto estimado y su intervalo de confianza. La cantidad de registros por sí sola no confirma una hipótesis: la decisión depende de la calidad de la comparación, la precisión alcanzada y el MDE definido.

### 8.2.6. Methods Selection

Para recoger las medidas definidas en **8.2.3** y evaluarlas con la escala de **8.2.5**, distinguimos la pregunta que investigamos del método que usamos para responderla. Seleccionamos técnicas de campo, tareas comparativas y lecturas emparejadas, procurando usar la cosa más simple y útil (*Simplest Useful Thing*) para obtener evidencia pertinente en el contexto de almacenes farmacéuticos.

**Hipótesis 1: Impacto del monitoreo continuo**

**Método: Piloto de campo con comparación antes-después (*Field Trial*)**

- **Propósito:** evaluar si el monitoreo continuo se relaciona con una reducción de al menos **30 %** en la tasa de incidentes de deterioro.
- **Ejecución:** se comparan, por establecimiento, los lotes monitoreados y los incidentes confirmados durante una línea base de tres meses y tres meses de uso del monitoreo KairoLabs. La tasa se ajusta por el volumen de lotes.
- **Herramientas:** [aplicación web KairoLabs](https://kairo-labs-frontend.vercel.app), [API de sensores en Swagger](https://medi-track-sensor-platform.onrender.com/swagger/index.html), inventario y registro de incidentes del establecimiento.

![Detalle de dispositivo con lecturas y estados ambientales](../assets/chapter-5/web-dispositivo-detalle.png)

*Figura 8.2.6-1. Referencia de la interfaz utilizada para observar lecturas ambientales y sus estados.*

**Hipótesis 2: Eficacia de las alertas automáticas**

**Método: Piloto de campo con comparación de periodos**

- **Propósito:** determinar si las alertas automáticas reducen al menos **25 %** el tiempo mediano entre una desviación y la respuesta registrada.
- **Ejecución:** se contrastan las marcas de tiempo del proceso habitual con las de desviaciones atendidas mediante notificaciones automáticas. Los casos se comparan por tipo y severidad; se estima la diferencia de medianas y su intervalo de confianza mediante remuestreo.
- **Herramientas:** [aplicación web KairoLabs](https://kairo-labs-frontend.vercel.app), [API de sensores en Swagger](https://medi-track-sensor-platform.onrender.com/swagger/index.html) y registro de detección y atención de alertas.

![Vista de transportes y alertas críticas](../assets/chapter-5/web-transportes.png)

*Figura 8.2.6-2. Interfaz de transportes con indicadores de alertas críticas de cadena de frío.*

**Hipótesis 3: Eficacia del historial digital para auditorías**

**Método: Prueba comparativa de tareas con solicitudes equivalentes**

- **Propósito:** medir si el historial digital reduce al menos **20 %** el tiempo promedio para reunir evidencia de auditoría.
- **Ejecución:** el personal responsable completa solicitudes equivalentes de lecturas para una sede, dispositivo y periodo mediante búsqueda manual y consulta digital. Se registra el tiempo hasta entregar el conjunto solicitado y se comprueba que ambas búsquedas cubran los mismos datos.
- **Herramientas:** [aplicación web KairoLabs](https://kairo-labs-frontend.vercel.app), [documentación de la API](https://medi-track-sensor-platform.onrender.com/swagger/index.html) y planilla de registro de solicitudes y tiempos.

![Listado de dispositivos de KairoLabs](../assets/chapter-5/web-dispositivos.png)

*Figura 8.2.6-3. Listado de dispositivos que sirve de referencia para localizar una sede y delimitar una solicitud de registros.*

**Hipótesis 4: Precisión del registro mediante sensores**

**Método: Validación de campo con lecturas pareadas**

- **Propósito:** determinar si el registro mediante sensores mejora al menos **25 %** la proporción de lecturas correctas respecto del método manual.
- **Ejecución:** en las mismas ubicaciones y momentos se registran la lectura del sensor, la lectura manual y la de un instrumento de referencia. Cada par se clasifica según la tolerancia definida para su variable; el análisis compara las proporciones pareadas y considera el establecimiento y dispositivo de origen.
- **Herramientas:** dispositivos y sensores de KairoLabs, instrumento de referencia calibrado, [API de sensores en Swagger](https://medi-track-sensor-platform.onrender.com/swagger/index.html) y planilla de lecturas pareadas.

![Respuesta de la API con lecturas de dispositivos](../assets/chapter-5/api-get-devices.png)

*Figura 8.2.6-4. Evidencia de consulta de lecturas ambientales mediante el endpoint de dispositivos.*

**Hipótesis 5: Eficiencia de la supervisión multisede**

**Método: Prueba comparativa de tareas y análisis de registros de campo**

- **Propósito:** evaluar la reducción de al menos **30 %** en el tiempo de revisión multisede y, como resultado de negocio complementario, de **20 %** en las pérdidas económicas documentadas.
- **Ejecución:** los gestores completan tareas equivalentes de revisión con el proceso habitual y con el dashboard. Por separado, se comparan durante seis meses las tasas de pérdidas documentadas y su exposición por establecimiento; los resultados de tiempo y pérdidas se interpretan con sus MDE respectivos.
- **Herramientas:** [dashboard de KairoLabs](https://kairo-labs-frontend.vercel.app), [API de establecimientos y dispositivos](https://medi-track-sensor-platform.onrender.com/swagger/index.html), registros de incidentes y documentos de baja, devolución o cuarentena.

![Centro de Control de KairoLabs](../assets/chapter-5/web-centro-control.png)

*Figura 8.2.6-5. Centro de Control con indicadores y sensores organizados por sede.*

**Resumen de métodos seleccionados**

| Método | Hipótesis que valida | Tipo de evidencia | Herramientas principales |
| :--- | :---: | :--- | :--- |
| Piloto de campo con comparación antes-después | H1 | Cuantitativa, tasas de incidentes y exposición por lote | Aplicación web, API de sensores, inventario e incidentes |
| Piloto de campo con comparación de periodos | H2 | Cuantitativa, tiempos medianos de respuesta | Aplicación web, API y registro de alertas |
| Prueba comparativa de tareas con solicitudes equivalentes | H3 | Cuantitativa, tiempos de búsqueda y completitud del conjunto | Aplicación web, Swagger y planilla de registro |
| Validación de campo con lecturas pareadas | H4 | Cuantitativa, proporciones dentro de tolerancia | Sensores, instrumento de referencia, API y planilla |
| Prueba comparativa de tareas y análisis de registros de campo | H5 | Cuantitativa, tiempos de revisión y pérdidas documentadas | Dashboard, API, registros de incidentes y documentos de inventario |

**Herramientas y fuentes de evidencia**

| Herramienta o fuente | Uso en los métodos | Referencia |
| :--- | :--- | :--- |
| Aplicación web KairoLabs | Ejecutar las tareas de monitoreo, consulta de dispositivos y supervisión multisede. | [Abrir aplicación web](https://kairo-labs-frontend.vercel.app) · [Repositorio del frontend](https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Frontend) |
| API MediTrack Sensor | Consultar establecimientos, dispositivos y lecturas disponibles para las medidas de campo. | [Abrir Swagger UI](https://medi-track-sensor-platform.onrender.com/swagger/index.html) · [Repositorio de la API](https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Platform) |
| Planilla de registro | Anotar horas de solicitud, detección y respuesta, lecturas manuales y de referencia, y evidencia documental asociada. | Plantilla de captura del experimento, con los campos de MD-01 a MD-08. |
| Instrumento ambiental de referencia | Contrastar las lecturas de sensores y registros manuales bajo la tolerancia de cada variable. | Instrumento calibrado del establecimiento. |

Se priorizan las funciones y fuentes existentes de KairoLabs y registros operativos pertinentes; la planilla y el instrumento se limitan a las variables necesarias para cada comparación. Las capturas de esta sección documentan las interfaces y fuentes usadas para preparar los métodos; no representan resultados de los experimentos.

**Control de interferencias y ética**

Los experimentos se ejecutan de forma secuencial por tema y módulo. Un mismo participante no realiza al mismo tiempo tareas de dos experimentos que puedan alterar su comportamiento o contaminar las observaciones; si participa en más de uno, las sesiones se programan por separado y se registran por experimento.

El personal conserva los procedimientos habituales para proteger los medicamentos y atender desviaciones. No se retiran controles ni alertas preventivas para formar un grupo de control, no se provocan condiciones ambientales fuera de rango y no se manipulan inventarios reales para generar pérdidas. Las pruebas de consulta y supervisión usan registros autorizados; las tareas pueden emplear escenarios y datos de prueba. Los resultados se presentan de forma agregada y el acceso a los registros se limita a lo necesario para el análisis.

### 8.2.7. Data Analytics: Goals, KPIs and Metrics Selection

En esta sección definimos qué conocimiento esperamos obtener de los experimentos y qué datos usaremos para obtenerlo. La analítica de KairoLabs se enfoca en resultados de conservación farmacéutica y operación: detectar incidentes, responder a desviaciones, preparar evidencia, confiar en las lecturas y supervisar varias sedes. Seleccionamos indicadores que ya tienen fórmula, fuente y meta en **8.2.2**; la actividad digital general no se interpreta como valor de negocio por sí sola.

**1. Metas de análisis (Goals)**

La analítica permitirá al equipo:

- Evaluar si el monitoreo y las alertas se asocian con menos incidentes y respuestas más oportunas (**H1–H2**).
- Medir si el historial digital facilita reunir evidencia de conservación para auditoría (**H3**).
- Comprobar la precisión de las lecturas automáticas frente a un instrumento de referencia y al registro manual (**H4**).
- Estimar la eficiencia de la supervisión multisede y contextualizarla con la cobertura y las pérdidas documentadas (**H5**).
- Distinguir resultados de negocio de señales técnicas que permiten identificar interrupciones, errores o datos incompletos durante la observación.

**2. Selección de KPIs y métricas**

| Nivel | KPI / indicador | Métrica atómica (dato registrado) | Fuente | Justificación de selección y economía de rastreo |
| :--- | :--- | :--- | :--- | :--- |
| Negocio — conservación | **MD-01. Tasa de incidentes de deterioro** | Incidentes confirmados y lotes monitoreados, vinculados por sede, fecha y lote. | Registro de incidentes, inventario e historial de lecturas. | Responde directamente a H1; solo se registran incidentes confirmados y la exposición necesaria para calcular la tasa. |
| Negocio — pérdidas | **MD-06. Tasa de pérdidas económicas por almacenamiento** | Valor de productos dañados o descartados y valor del inventario monitoreado. | Incidentes y documentos de baja, devolución o cuarentena. | Cuantifica el impacto económico asociado a H5 sin registrar actividad ajena al deterioro ambiental. |
| Operación — respuesta | **MD-02. Tiempo de respuesta a desviaciones** | Hora de la primera lectura fuera de rango y hora de la acción registrada. | Lecturas y registro de atención de alertas. | Mide el intervalo necesario para H2; se conservan solo marcas de tiempo asociadas con una desviación. |
| Operación — trazabilidad | **MD-03. Tiempo de preparación de evidencia** | Inicio de la solicitud y entrega del conjunto de registros requerido. | Planilla de tareas y consulta del historial. | Mide H3 con solicitudes equivalentes; no requiere rastrear navegación general del usuario. |
| Producto — precisión de datos | **MD-04. Precisión de lecturas ambientales** | Lectura del sensor, lectura manual y lectura de referencia, junto con variable, ubicación, momento y tolerancia. | Sensores, instrumento de referencia y registros manuales. | Evalúa H4 directamente; se recogen pares comparables, no telemetría adicional sin relación con la lectura. |
| Operación — gestión multisede | **MD-05. Tiempo de supervisión multisede** | Inicio y fin de la tarea de revisión, sedes incluidas y tarea completada. | Planilla de tareas y dashboard de KairoLabs. | Responde al componente de eficiencia de H5 mediante tareas equivalentes y delimitadas. |
| Cobertura — disponibilidad de datos | **MD-07. Cobertura de establecimientos monitoreados** | Establecimientos incluidos, dispositivo activo y marca de tiempo de la última lectura. | Inventario de sedes y lecturas de la API. | Permite interpretar los resultados según la proporción realmente cubierta, sin contar visitas o impresiones. |
| Calidad — integridad del registro | **MD-08. Controles de conservación conformes y trazables** | Controles programados y registros completos con lectura, rango, sede, dispositivo, fecha y hora. | Calendario de controles e historial de lecturas. | Verifica que la evidencia usada para los experimentos sea interpretable y trazable. |

**3. Fuentes de analítica y observabilidad**

| Fuente / herramienta | Datos que aporta | Uso en el análisis |
| :--- | :--- | :--- |
| [Aplicación web KairoLabs](https://kairo-labs-frontend.vercel.app) y [API MediTrack Sensor](https://medi-track-sensor-platform.onrender.com/swagger/index.html) | Estado de sedes y dispositivos, lecturas ambientales y registros relacionados con alertas. | Fuente operativa para MD-01, MD-02, MD-04, MD-07 y MD-08. |
| **UptimeRobot** | Disponibilidad, tiempo de conexión/TTFB y códigos HTTP mediante sondeos sintéticos. | Identifica periodos de indisponibilidad que podrían explicar lecturas ausentes o interrumpidas. |
| **Vercel Analytics & Logs** | Indicadores técnicos web —Core Web Vitals—, solicitudes y errores registrados en la infraestructura. | Ayuda a contextualizar fallos de carga o degradaciones durante las sesiones de prueba. |
| **Axios Runtime Interceptors** | Errores del cliente, interrupciones de red y fallos de autenticación en la aplicación web. | Ayuda a diagnosticar registros incompletos o tareas que no se pudieron terminar por un error técnico. |
| **Planilla de tareas y documentos operativos** | Tiempos de búsqueda y revisión, acciones registradas e importes sustentados de pérdidas. | Complementa los datos de plataforma para MD-02, MD-03, MD-05 y MD-06. |

Las señales técnicas de UptimeRobot, Vercel y Axios son **indicadores de contexto y calidad de datos**, no sustituyen los KPIs de negocio ni se usan para declarar una hipótesis validada. El capítulo VII describe el pipeline de monitoreo y la telemetría de la plataforma; aquí se emplean esas fuentes para reconocer interrupciones y poner en contexto las observaciones experimentales.

**4. Auditoría técnica de la aplicación con Lighthouse**

Se ejecutó Lighthouse sobre la ruta de inicio de sesión del [frontend de KairoLabs](https://kairo-labs-frontend.vercel.app/login), en perfiles **Mobile** y **Desktop**. Los puntajes son una medición técnica de esa ruta bajo las condiciones de cada perfil; no se interpretan como resultados de las hipótesis de negocio ni representan una auditoría de la Landing Page o del Centro de Control.

| Indicador técnico de Lighthouse | Mobile | Desktop |
| :--- | :---: | :---: |
| Performance | **60/100** | **86/100** |
| Accessibility | **95/100** | **95/100** |
| Best Practices | **100/100** | **100/100** |
| SEO | **91/100** | **92/100** |
| First Contentful Paint (FCP) | **3,7 s** | **1,1 s** |
| Largest Contentful Paint (LCP) | **4,6 s** | **1,1 s** |
| Speed Index | **4,6 s** | **7,0 s** |
| Total Blocking Time (TBT) | **550 ms** | **30 ms** |
| Cumulative Layout Shift (CLS) | **0** | **0** |

El perfil Desktop presenta mejores puntajes de Performance y valores menores de FCP, LCP y TBT; el Speed Index reportado es **7,0 s**, por lo que lo conservamos como indicador independiente. En ambos perfiles Lighthouse señala una oportunidad de mejora en el contraste. En Mobile también reporta trabajo prolongado en el hilo principal y recursos JavaScript/CSS no utilizados; en Desktop identifica solicitudes que bloquean el renderizado, demora de fuentes y un payload total de **31 434 KB**. El SEO reporta `robots.txt` inválido (40 errores) en ambas capturas; al tratarse de `/login`, este indicador se interpreta como diagnóstico técnico, no como KPI de negocio.

Estos hallazgos orientan la revisión técnica; no se mezclan con MD-01 a MD-08 ni se usan como evidencia de impacto sobre conservación, alertas o pérdidas.

**Evidencia Lighthouse Mobile**

![Resumen de auditoría Lighthouse Mobile en la ruta de inicio de sesión](../assets/lightouse-1.png)

*Figura 8.2.7-1. Resumen Lighthouse Mobile de `/login`: Performance 60, Accessibility 95, Best Practices 100 y SEO 91.*

![Oportunidades de mejora de carga en Lighthouse](../assets/lightouse-2.png)

*Figura 8.2.7-2. Diagnósticos de carga: solicitudes que bloquean el renderizado, fuentes y descubrimiento del contenido principal.*

![Diagnósticos de rendimiento y recursos](../assets/lightouse-3.png)

*Figura 8.2.7-3. Trabajo del hilo principal, JavaScript y CSS no utilizados y tamaño de recursos identificados en la auditoría.*

![Detalle de accesibilidad de Lighthouse](../assets/lightouse-4.png)

*Figura 8.2.7-4. Auditoría de accesibilidad: oportunidad de mejora en contraste de colores.*

![Detalle de buenas prácticas y SEO de Lighthouse](../assets/lightouse-5.png)

*Figura 8.2.7-5. Detalle de Best Practices y SEO para la ruta auditada; Lighthouse señala observaciones de `robots.txt`.*

**Evidencia Lighthouse Desktop**

![Resumen de auditoría Lighthouse Desktop en la ruta de inicio de sesión](../assets/lightouse--desktop-1.png)

*Figura 8.2.7-6. Resumen Lighthouse Desktop de `/login`: Performance 86, Accessibility 95, Best Practices 100 y SEO 92.*

![Diagnósticos de rendimiento Lighthouse Desktop](../assets/lightouse--desktop-2.png)

*Figura 8.2.7-7. Diagnósticos Desktop de fuentes, solicitudes que bloquean el renderizado, recursos no utilizados y tamaño de la página.*

![Detalle de accesibilidad Lighthouse Desktop](../assets/lightouse--desktop-3.png)

*Figura 8.2.7-8. Auditoría Desktop de accesibilidad: observaciones de contraste y subtítulos del elemento de video.*

![Detalle de buenas prácticas Lighthouse Desktop](../assets/lightouse--desktop-4.png)

*Figura 8.2.7-9. Auditoría Desktop de buenas prácticas y observación sobre source maps.*

![Detalle SEO Lighthouse Desktop](../assets/lightouse--desktop-5.png)

*Figura 8.2.7-10. Auditoría SEO Desktop: `robots.txt` inválido y 40 errores reportados.*

**5. Economía del rastreo**

La recolección se activa para los establecimientos, participantes, variables y periodos que corresponden a cada experimento. Registramos identificadores de sede y dispositivo, marcas de tiempo y datos de resultado solo cuando hacen falta para calcular las métricas MD-01 a MD-08; excluimos clics generales, impresiones y datos personales que no aporten a esas mediciones. El equipo revisa los datos por experimento y conserva el acceso restringido a los registros operativos, presentando los resultados de forma agregada.

### 8.2.8. Web and Mobile Tracking Plan

Este plan especifica cómo registrar las observaciones de cada experimento en la aplicación web de KairoLabs y en su vista móvil. Los eventos se relacionan con las métricas **MD-01 a MD-08** y con las condiciones de control, experimental o pareada definidas previamente. La instrumentación captura acciones y datos necesarios para responder las hipótesis, no navegación general ni clics sin relación con ellas.

| Plataforma | Evento o acción rastreada | Métrica / KPI asociado | Condición / contexto de captura | Herramienta / fuente |
| :--- | :--- | :--- | :--- | :--- |
| Web y vista móvil | Lectura ambiental recibida; lote incorporado al monitoreo; incidente confirmado; control de conservación registrado. | **MD-01**, **MD-07**, **MD-08** | Sedes elegibles del piloto; condición de referencia o monitoreo KairoLabs; solo lecturas, lotes y controles vinculados al periodo. | Web Vue/Vite, API MediTrack y registro operativo del establecimiento. |
| Web y vista móvil | Alerta generada y respuesta registrada por el operador. | **MD-02**, **MD-08** | Una lectura fuera de rango; se registra la condición y las marcas de tiempo de detección y primera acción. | Web KairoLabs, API ASP.NET Core y MySQL. |
| Web y vista móvil | Solicitud de evidencia iniciada y conjunto de registros preparado. | **MD-03**, **MD-08** | Tarea equivalente bajo consulta manual o digital; se registra el mismo alcance de sede, dispositivo y periodo. | Web KairoLabs y planilla de tareas para la condición manual. |
| API y registro de campo | Par de lectura del sensor, lectura manual e instrumento de referencia. | **MD-04** | Misma variable, ubicación y momento; se identifica condición pareada y tolerancia aplicable. | API de sensores, instrumento de referencia y formulario controlado de captura. |
| Web y vista móvil | Revisión multisede iniciada y completada; documento de pérdida validado. | **MD-05**, **MD-06**, **MD-07** | Tarea con conjunto de sedes definido; las pérdidas se registran solo con sustento de baja, devolución o cuarentena. | Dashboard KairoLabs, API y registro documental del establecimiento. |
| Web — auditoría técnica | Reporte Lighthouse guardado para la ruta auditada; sondeo de disponibilidad y respuesta. | Indicadores técnicos de **8.2.7**: puntuaciones Lighthouse, Web Vitals, disponibilidad, TTFB y errores HTTP. | Auditoría puntual de `/login` en perfiles Mobile y Desktop; sondeos del servicio según su intervalo configurado. | Reportes Lighthouse, UptimeRobot y Vercel Analytics & Logs. |

En el campo **Plataforma**, “vista móvil” identifica la aplicación web usada desde un navegador en dispositivo móvil; conserva los mismos nombres de evento y reglas que la vista de escritorio. `platform` distingue `web_desktop`, `web_mobile`, `api` y `manual`, para poder segmentar la captura sin duplicar métricas ni eventos por cada formato de pantalla.

| Hipótesis | Método de 8.2.6 | Plataforma de ejecución | Captura de datos |
| :--- | :--- | :--- | :--- |
| **H1 — Monitoreo continuo** | Piloto de campo antes-después. | Aplicación web y API en contexto de establecimiento. | Lecturas por API; lotes e incidentes confirmados mediante registros del piloto. |
| **H2 — Alertas automáticas** | Piloto de campo con comparación de periodos. | Aplicación web y API. | Eventos automáticos de alerta y acción, relacionados por `alert_id`. |
| **H3 — Historial digital** | Prueba de tareas con solicitudes equivalentes. | Aplicación web y condición manual de comparación. | Eventos de inicio y entrega de evidencia, más tiempos de búsqueda manual. |
| **H4 — Precisión de sensores** | Validación de campo con lecturas pareadas. | API, navegador web/móvil y captura de campo. | Lectura automática enlazada con valor manual y de referencia. |
| **H5 — Supervisión multisede** | Tareas comparativas y análisis de registros. | Dashboard web usado en escritorio o navegador móvil. | Eventos de inicio/fin de tarea y registro documental de pérdidas. |

Las mediciones de Lighthouse son informes puntuales y se conservan como evidencia técnica de **8.2.7**, no como eventos de usuario ni como filas de `experiment_events`. La disponibilidad, TTFB y errores de Vercel/UptimeRobot se consultan en sus fuentes operativas y solo ayudan a interpretar interrupciones de la plataforma.

**Catálogo de eventos de seguimiento**

| Hipótesis | Evento | Disparador | Datos mínimos del evento |
| :--- | :--- | :--- | :--- |
| **H1** | `monitoring_reading_received` | La API recibe y almacena una lectura ambiental válida. | `establishment_id`, `device_id`, `reading_id`, `metric_name`, `value`, `unit`, `threshold_status`, `occurred_at`. |
| **H1** | `monitored_lot_recorded` | Un lote se incorpora al conjunto de lotes monitoreados del piloto. | `establishment_id`, `lot_key`, `condition_name`, `monitoring_start`, `monitoring_end`. |
| **H1** | `storage_incident_confirmed` | El responsable confirma un incidente de deterioro con evidencia del establecimiento. | `incident_key`, `establishment_id`, `lot_key`, `incident_type`, `evidence_ref`, `occurred_at`. |
| **H1** | `conservation_control_recorded` | Se registra un control programado de conservación con lectura y rango aplicable. | `control_id`, `establishment_id`, `device_id`, `reading_id`, `range_status`, `record_complete`, `occurred_at`. |
| **H2** | `alert_triggered` | Una lectura supera el rango configurado y genera una alerta. | `alert_id`, `establishment_id`, `device_id`, `severity`, `reading_id`, `occurred_at`. |
| **H2** | `alert_response_recorded` | El operador registra la primera acción para atender una alerta. | `alert_id`, `action_type`, `subject_key`, `occurred_at`. |
| **H3** | `audit_request_started` | El responsable inicia una solicitud de registros. | `request_id`, `establishment_id`, `device_id`, `period_start`, `period_end`, `condition_name`, `occurred_at`. |
| **H3** | `audit_evidence_ready` | El conjunto solicitado queda preparado para revisión. | `request_id`, `record_count`, `subject_key`, `occurred_at`. |
| **H4** | `sensor_accuracy_pair_recorded` | Se completa un par comparable de mediciones. | `reading_id`, `establishment_id`, `device_id`, `metric_name`, `sensor_value`, `manual_value`, `reference_value`, `tolerance`, `unit`, `occurred_at`. |
| **H5** | `multisite_review_started` | El gestor inicia una tarea de revisión del conjunto de sedes definido. | `review_id`, `subject_key`, `site_count`, `condition_name`, `occurred_at`. |
| **H5** | `multisite_review_completed` | El gestor completa la revisión y marca las sedes que requieren atención. | `review_id`, `sites_needing_attention`, `occurred_at`. |
| **H5** | `storage_loss_documented` | Se valida un importe de pérdida a partir de un documento operativo. | `incident_key`, `establishment_id`, `amount`, `currency`, `evidence_ref`, `occurred_at`. |

Los eventos de `monitoring_reading_received` y `alert_triggered` se originan en la API y se relacionan por `reading_id`, `device_id` y `alert_id`. Las acciones que no se generan dentro de la aplicación —confirmación documental de incidentes, lecturas manuales o de referencia, solicitudes manuales y pérdidas económicas— se capturan en el registro controlado del piloto con los mismos identificadores y nombres de evento. Así se conserva un esquema común sin atribuir a la telemetría automática datos que provienen de observación de campo.

**Estructura lógica de almacenamiento**

El flujo de captura envía los eventos del cliente web o de la vista móvil a la API ASP.NET Core para validación y almacenamiento en MySQL. El plan define `POST /api/v1/experiment-events` como ruta de recepción; los eventos originados por lecturas de sensores o documentos de campo se incorporan con el mismo esquema y sus fuentes identificadas. `experiment_events` organiza los datos para consultar por hipótesis, condición, plataforma y periodo. El `payload` contiene únicamente los campos específicos del evento; las consultas experimentales no requieren copiar nombres, correos, credenciales ni tokens de autenticación.

```sql
CREATE TABLE experiment_events (
    event_id BIGINT UNSIGNED NOT NULL AUTO_INCREMENT,
    experiment_id VARCHAR(8) NOT NULL,
    event_name VARCHAR(64) NOT NULL,
    platform ENUM('web_desktop', 'web_mobile', 'api', 'manual') NOT NULL,
    condition_name ENUM('baseline', 'control', 'experimental', 'paired') NOT NULL,
    subject_key CHAR(64) NULL,
    session_id CHAR(36) NULL,
    establishment_id BIGINT NULL,
    device_id BIGINT NULL,
    occurred_at DATETIME(3) NOT NULL,
    payload JSON NOT NULL,
    environment ENUM('test', 'pilot') NOT NULL,
    PRIMARY KEY (event_id),
    KEY idx_experiment_event_time (experiment_id, event_name, occurred_at),
    KEY idx_establishment_device (establishment_id, device_id),
    KEY idx_session (session_id)
);
```

Los tiempos se normalizan a UTC; `subject_key` es un identificador seudónimo y `session_id` agrupa acciones de una misma sesión de evaluación. `environment` separa datos de prueba de los del piloto y `condition_name` mantiene la comparación sin inferir el grupo a partir de la interfaz.

**Consultas de análisis**

La mediana de respuesta de H2 se obtiene emparejando cada alerta con su primera acción registrada:

```sql
WITH first_response AS (
    SELECT
        t.event_id AS trigger_event_id,
        MIN(r.occurred_at) AS response_at
    FROM experiment_events AS t
    JOIN experiment_events AS r
      ON JSON_UNQUOTE(JSON_EXTRACT(t.payload, '$.alert_id')) =
         JSON_UNQUOTE(JSON_EXTRACT(r.payload, '$.alert_id'))
     AND r.experiment_id = t.experiment_id
     AND r.event_name = 'alert_response_recorded'
     AND r.environment = 'pilot'
     AND r.occurred_at >= t.occurred_at
    WHERE t.experiment_id = 'H2'
      AND t.event_name = 'alert_triggered'
      AND t.environment = 'pilot'
    GROUP BY t.event_id
), response_times AS (
    SELECT TIMESTAMPDIFF(SECOND, t.occurred_at, f.response_at) AS response_seconds
    FROM first_response AS f
    JOIN experiment_events AS t ON t.event_id = f.trigger_event_id
), ranked AS (
    SELECT response_seconds,
           ROW_NUMBER() OVER (ORDER BY response_seconds) AS row_num,
           COUNT(*) OVER () AS total_rows
    FROM response_times
)
SELECT AVG(response_seconds) AS median_response_seconds
FROM ranked
WHERE row_num IN (FLOOR((total_rows + 1) / 2), FLOOR((total_rows + 2) / 2));
```

La precisión de H4 se calcula con el mismo conjunto de pares y tolerancia para el sensor y el registro manual:

```sql
SELECT
    COUNT(*) AS valid_pairs,
    ROUND(100 * AVG(
        ABS(CAST(JSON_UNQUOTE(JSON_EXTRACT(payload, '$.sensor_value')) AS DECIMAL(12,4)) -
            CAST(JSON_UNQUOTE(JSON_EXTRACT(payload, '$.reference_value')) AS DECIMAL(12,4))) <=
        CAST(JSON_UNQUOTE(JSON_EXTRACT(payload, '$.tolerance')) AS DECIMAL(12,4))
    ), 2) AS sensor_accuracy_pct,
    ROUND(100 * AVG(
        ABS(CAST(JSON_UNQUOTE(JSON_EXTRACT(payload, '$.manual_value')) AS DECIMAL(12,4)) -
            CAST(JSON_UNQUOTE(JSON_EXTRACT(payload, '$.reference_value')) AS DECIMAL(12,4))) <=
        CAST(JSON_UNQUOTE(JSON_EXTRACT(payload, '$.tolerance')) AS DECIMAL(12,4))
    ), 2) AS manual_accuracy_pct
FROM experiment_events
WHERE experiment_id = 'H4'
  AND event_name = 'sensor_accuracy_pair_recorded'
  AND environment = 'pilot';
```

**Economía y control de datos**

La captura se limita a las sedes, periodos y eventos incluidos en cada experimento. No se registran vistas generales, clics sin relación con una tarea, datos personales innecesarios ni contenido de documentos de auditoría; se conserva una referencia al sustento autorizado. Los eventos de control, experimentales y pareados se identifican explícitamente, y los registros de prueba se excluyen de los análisis del piloto. El esquema se consulta mediante SQL para generar MD-01 a MD-08 y los resultados se presentan agregados.

## 8.3. Experimentation

La fase de experimentación constituye el núcleo operativo del enfoque *Experiment-Driven Development* (EDD) para KairoLabs. En esta etapa, el equipo traduce las necesidades identificadas, los vacíos de conocimiento y las cinco hipótesis de negocio formuladas en la sección 8.2 en artefactos de software tangibles y medibles. 

A diferencia de los ciclos tradicionales de desarrollo basados exclusivamente en la entrega de requerimientos funcionales, el proceso de experimentación en KairoLabs está orientado a validar empíricamente el impacto del producto en escenarios reales de almacenamiento farmacéutico. Para ello, se definen especificaciones de software bajo el paradigma **To-Be** (estado futuro deseado), donde cada historia de usuario, tarea de desarrollo y despliegue en producción responde de forma directa a la contrastación de una hipótesis, garantizando la recolección sistemática de métricas de dominio (MD-01 a MD-08) y de analítica web/móvil.

### 8.3.1. To-Be User Stories

A partir de las hipótesis de trabajo ($H_1$ a $H_5$) establecidas en el diseño experimental, se especificaron cuatro Historias de Usuario de Experimentación (**To-Be User Stories**). Estas historias capturan el comportamiento esperado de la plataforma ante desviaciones críticas de temperatura/humedad, la visualización en tiempo real de telemetría de sensores IoT, la consolidación de evidencia digital para auditorías regulatorias y la supervisión centralizada entre múltiples sedes farmacéuticas.

Todas las historias se estructuraron bajo el estándar ágil de la industria y definen sus criterios de aceptación mediante el lenguaje formal **Gherkin** (*Given - When - Then*), abarcando tanto el flujo principal exitoso (*Happy Path*) como escenarios de contingencia o error (*Unhappy Path*).

---

#### **US-EXP01: Notificaciones y alertas automáticas en tiempo real ante desviaciones de temperatura**

* **User Story ID:** `US-EXP01`
* **Epic asociada:** `EP04 - Gestión de Alertas y Notificaciones`
* **Hipótesis asociada:** `H2` (Reducción de al menos 25% en el tiempo mediano de respuesta ante lecturas fuera de rango mediante avisos automáticos).
* **Story Points:** 5
* **Prioridad:** Must Have (Alta)

> **Descripción:**  
> **Como** personal operativo de almacenes farmacéuticos,  
> **deseo** recibir alertas automáticas e inmediatas en la interfaz web y móvil cuando los sensores IoT detecten lecturas fuera de los rangos críticos de conservación (menor a 2 °C o mayor a 8 °C para cadena de frío; fuera de 15 °C a 25 °C para temperatura ambiente),  
> **para** tomar acciones correctivas inmediatas y registrar la atención antes de que se produzca el deterioro físico o químico de los medicamentos.

* **Criterios de Aceptación (Gherkin):**

```gherkin
Scenario: Notificación inmediata y despliegue visual por temperatura fuera de rango (Happy Path)
  Given que el sensor IoT asignado a una zona de almacenamiento registra una temperatura de 9.5 °C
  And el rango seguro parametrizado para dicho lote de medicamentos es de 2.0 °C a 8.0 °C
  When el sistema ingiere la lectura a través del endpoint telemétrico
  Then el sistema debe generar una alerta crítica en menos de 10 segundos
  And la interfaz del operador debe mostrar un indicador visual prominente de advertencia (color rojo)
  And el sistema debe registrar la marca de tiempo exacta de detección para el cómputo de la métrica MD-02.

Scenario: Registro de acción correctiva y mitigación de alerta por el operador (Happy Path)
  Given que existe una alerta crítica activa en el establecimiento asignado al operador
  When el operador visualiza la alerta y presiona el botón "Atender Desviación"
  And ingresa la acción realizada ("Ajuste de termostato y verificación de sellado de puerta de cámara")
  Then el sistema debe actualizar el estado de la alerta a "Atendida"
  And registrar la marca de tiempo de resolución, calculando la latencia de respuesta para contrastar H2.

Scenario: Falla de conectividad o sensor inalcanzable (Unhappy Path)
  Given que un sensor IoT deja de emitir telemetría por más de 15 minutos consecutivos
  When el servicio de monitoreo en segundo plano evalúa la frecuencia de pulsos
  Then el sistema debe disparar una alerta técnica de tipo "Sensor Desconectado / Sin Señal"
  And notificar al operador para que realice la inspección física inmediata del dispositivo.
```

---

#### **US-EXP02: Visualización continua de lecturas y telemetría de sensores en Dashboard**

* **User Story ID:** `US-EXP02`
* **Epic asociada:** `EP03 - Monitoreo Ambiental y Telemetría`
* **Hipótesis asociada:** `H1` (Reducción de al menos 30% en incidentes de deterioro) y `H4` (Aumento de al menos 25% en lecturas correctas automatizadas vs. manuales).
* **Story Points:** 5
* **Prioridad:** Must Have (Alta)

> **Descripción:**  
> **Como** personal operativo y gestor farmacéutico,  
> **deseo** visualizar en un panel interactivo el estado térmico y de humedad en tiempo real de cada dispositivo sensor asignado a mi sede,  
> **para** identificar tendencias graduales de calentamiento o enfriamiento sin tener que esperar a realizar una ronda física manual de inspección con planillas en papel.

* **Criterios de Aceptación (Gherkin):**

```gherkin
Scenario: Consulta y actualización continua de telemetría ambiental (Happy Path)
  Given que el operador ha iniciado sesión y se encuentra en el Dashboard principal de su establecimiento
  When los sensores IoT transmiten nuevas lecturas de temperatura y humedad
  Then la interfaz debe refrescar los valores en pantalla sin requerir la recarga manual de la página
  And debe presentar un gráfico cronológico de las últimas 24 horas señalando las bandas de tolerancia seguras.

Scenario: Filtrado de telemetría por dispositivo y rango horario (Happy Path)
  Given que el usuario se encuentra en el módulo de visualización de telemetría
  When selecciona un sensor específico y define un rango horario de interés
  Then el sistema debe renderizar la serie temporal correspondiente con sus valores máximos, mínimos y media calculada.

Scenario: Ingesta de datos anómalos o fuera de escala física (Unhappy Path)
  Given que un sensor defectuoso envía una lectura físicamente inconsistente (ej. -99 °C o 150 °C)
  When el backend procesa la carga útil (payload)
  Then debe marcar la lectura como "Inválida / Anómala"
  And no debe alterar la curva de tendencia histórica, notificando al usuario sobre la necesidad de calibración.
```

---

#### **US-EXP03: Historial digital y exportación de reportes de trazabilidad para auditorías sanitarias**

* **User Story ID:** `US-EXP03`
* **Epic asociada:** `EP06 - Trazabilidad, Auditoría y Cumplimiento Regulatorio`
* **Hipótesis asociada:** `H3` (Reducción de al menos 20% en el tiempo promedio requerido para reunir evidencia en auditorías sanitarias frente al proceso manual).
* **Story Points:** 3
* **Prioridad:** Should Have (Media-Alta)

> **Descripción:**  
> **Como** gestor farmacéutico y responsable de cumplimiento normativo (Compliance Manager),  
> **deseo** consultar y exportar en formato digital consolidado (PDF / CSV) el historial inalterable de lecturas ambientales e incidentes por sede y periodo,  
> **para** presentar evidencia fidedigna de conservación durante auditorías e inspecciones sanitarias regulatorias de DIGEMID/CENARES sin demoras por búsqueda manual de archivos físicos.

* **Criterios de Aceptación (Gherkin):**

```gherkin
Scenario: Generación y descarga de reporte consolidado de trazabilidad (Happy Path)
  Given que el gestor se encuentra en la sección de "Reportes y Auditoría"
  When selecciona una sede, un rango de fechas de 30 días y presiona "Exportar Reporte Oficial"
  Then el sistema debe compilar los registros ambientales, eventos de calibración y bitácora de alertas
  And generar un archivo descargable con código de verificación e integridad digital en un tiempo inferior a 15 segundos.

Scenario: Búsqueda sin registros en el periodo seleccionado (Unhappy Path)
  Given que el gestor selecciona un rango de fechas en el que la sede aún no tenía sensores instalados
  When solicita la exportación del reporte
  Then el sistema debe mostrar un mensaje informativo indicando "No se encontraron registros de telemetría para el periodo indicado"
  And sugerir al usuario ajustar el intervalo de fechas.
```

---

#### **US-EXP04: Gestión centralizada multisede y supervisión operativa**

* **User Story ID:** `US-EXP04`
* **Epic asociada:** `EP07 - Supervisión Multisede y Operaciones`
* **Hipótesis asociada:** `H5` (Reducción de al menos 30% en el tiempo de supervisión de sedes y 20% de pérdidas económicas acumuladas).
* **Story Points:** 5
* **Prioridad:** Must Have (Alta)

> **Descripción:**  
> **Como** gestor farmacéutico a cargo de múltiples establecimientos de salud,  
> **deseo** contar con una vista matriz que consolide el estado de conservación de todas las sedes a mi cargo y permita asignar operadores responsables,  
> **para** optimizar el tiempo de supervisión general, intervenir proactivamente en sedes vulnerables y prevenir pérdidas de inventario por falta de control.

* **Criterios de Aceptación (Gherkin):**

```gherkin
Scenario: Supervisión integral de múltiples almacenes en una única vista (Happy Path)
  Given que el gestor administra 3 establecimientos farmacéuticos activos
  When accede a la vista matriz multisede
  Then debe visualizar el semáforo de estado de cada sede (Verde: Óptimo, Amarillo: Advertencia, Rojo: Crítico)
  And identificar en menos de 30 segundos qué almacén requiere intervención prioritaria.

Scenario: Asignación de operadores a un establecimiento (Happy Path)
  Given que el gestor registra una nueva sede farmacéutica
  When selecciona a un operador del personal operativo disponible y le asigna el rol de custodio
  Then el operador debe quedar vinculado a la sede y comenzar a recibir las alertas generadas por los sensores de ese local.
```

---

### 8.3.2. To-Be Product Backlog

El **To-Be Product Backlog** consolida y prioriza los ítems de trabajo necesarios para ejecutar la experimentación. Se empleó el esquema de estimación ágil basado en la serie de Fibonacci para Story Points y la técnica MoSCoW para priorización, vinculando explícitamente cada requerimiento con su correspondiente hipótesis experimental.

| Backlog ID | Epic ID | Título de la Historia de Usuario | Story Points | Prioridad | Hipótesis Validada | Criterio de Aceptación Resumen |
| :---: | :---: | :--- | :---: | :---: | :---: | :--- |
| **US-EXP01** | EP04 | Notificaciones y alertas automáticas ante desviaciones de temperatura | 5 | Must Have | $H_2$ | Emisión de alerta visual/push en $\le 10$ s ante lecturas críticas y registro de atención. |
| **US-EXP02** | EP03 | Monitoreo continuo y telemetría de sensores en Dashboard | 5 | Must Have | $H_1, H_4$ | Gráfico interactivo en vivo con bandas de conservación y actualización reactiva. |
| **US-EXP03** | EP06 | Historial digital y exportación de reportes para auditoría sanitaria | 3 | Should Have | $H_3$ | Descarga de PDF/CSV con bitácora inalterable y sellos de tiempo en $\le 15$ s. |
| **US-EXP04** | EP07 | Gestión centralizada multisede y asignación de operadores | 5 | Must Have | $H_5$ | Vista matriz multisede con semaforización de estado y vinculación de custodios. |

---

### 8.3.3. Pipeline-supported, Experiment-Driven To-Be Software Platform Lifecycle

Para garantizar que los experimentos sean reproducibles, verificables y desplegados sin fricción, KairoLabs implementa un ciclo de vida de plataforma soportado íntegramente por canalizaciones (*pipelines*) de Integración Continua y Despliegue Continuo (CI/CD):

1. **Gestión de Versiones y Trazabilidad:** Todo cambio experimental se desarrolla en ramas de tipo `feature/` vinculadas a un ítem del backlog de experimentación. La integración a la rama principal (`main`) se rige mediante *Pull Requests* con revisión colaborativa entre pares.
2. **Pipeline de Construcción y Verificación:** Se ejecutan flujos automatizados de validación de sintaxis, análisis estático y pruebas BDD (Behavior-Driven Development) basadas en los escenarios Gherkin definidos en el punto 8.3.1.
3. **Despliegue Continuo (CD) en Entornos Productivos:**
   * **Landing Page y Frontend Web:** Desplegados de forma automatizada en **Vercel** ante cada fusión validada en la rama principal, ofreciendo distribución global vía CDN y certificados SSL/TLS activos.
   * **Backend API & Web Services:** Desplegados en contenedores mediante **Render**, asegurando disponibilidad de endpoints RESTful bajo HTTPS y conectividad persistente con la base de datos relacional PostgreSQL.
4. **Instrumentación de Telemetría:** Cada despliegue incorpora el etiquetado y rastreo de eventos de usuario (Google Analytics / Lighthouse) y registros de telemetría de base de datos para medir el comportamiento de las métricas MD-01 a MD-08.

---

#### 8.3.3.1. To-Be Sprint Backlogs

Para la ejecución del ciclo experimental se planificó el **Sprint de Experimentación (Sprint To-Be)**. El equipo utilizó un tablero Kanban/Scrum en **Trello** para orquestar la descomposición de las historias de usuario en tareas técnicas específicas de frontend, backend y configuración de telemetría.

* **Sprint Goal:**  
  *"Implementar, integrar y desplegar en producción las capacidades To-Be de alertas automáticas en tiempo real, monitoreo continuo de sensores IoT en dashboard interactivo y reportería digital multisede, garantizando la instrumentación telemétrica necesaria para contrastar las hipótesis H1 a H5 en condiciones operativas."*

* **Enlace del Tablero de Gestión (Trello):**  
  [Tablero de Sprint de Experimentación KairoLabs](https://trello.com/invite/b/6a4aec825530c3b6ab9db1b7/ATTI2034d17571ccf6acbefeae2e9ecfb71e4BAC22E5/sprint-4)

A continuación, se detalla la descomposición técnica de tareas (*Work-Items / Tasks*) ejecutadas durante el Sprint To-Be, distribuidas equitativamente entre los integrantes del equipo:

| User Story | Task ID | Título de la Tarea Técnica | Descripción de Implementación | Estimación (Horas) | Asignado a | Estado |
| :---: | :---: | :--- | :--- | :---: | :--- | :---: |
| **US-EXP01** | T-EXP01 | Maquetación del banner y modal de alerta crítica | Diseñar en React/Vite el componente visual de alerta con semaforización cromática (rojo de peligro) y selector de acciones correctivas. | 4 | Diaz Mendoza, Sebastian Victor Andre | **Done** |
| **US-EXP01** | T-EXP02 | Lógica de detección de umbrales y registro de resolución | Implementar en el frontend el cálculo de desvíos térmicos y el envío del payload de atención de alerta con timestamp a la API. | 5 | Ramirez Escalante, Carlo Patricio | **Done** |
| **US-EXP01** | T-EXP03 | Endpoint backend para ingesta de alertas telemétricas | Desarrollar endpoint REST `POST /api/v1/devices/{id}/alerts` para registrar eventos de alerta y calcular latencia de atención. | 6 | Mallqui Vilca, Dhilsen Armil | **Done** |
| **US-EXP02** | T-EXP04 | Gráfico cronológico de telemetría de 24 horas | Integrar librería de gráficos interactivos para renderizar las lecturas de temperatura y humedad con bandas de seguridad. | 6 | Dinklange Arevalo, Sandro | **Done** |
| **US-EXP02** | T-EXP05 | Integración del flujo de datos en tiempo real | Conectar el estado del dashboard con los servicios de telemetría para actualización reactiva de lecturas ambientales. | 5 | Ramirez Escalante, Carlo Patricio | **Done** |
| **US-EXP02** | T-EXP06 | Endpoint backend para consulta de telemetría por dispositivo | Optimizar el endpoint `GET /api/v1/devices/{id}/sensor-data` para retornar lecturas agregadas por rango temporal. | 5 | Oblitas Alcalde, Rodrigo | **Done** |
| **US-EXP03** | T-EXP07 | Módulo de generación y exportación de reportes | Construir la interfaz de selección de rango de fechas y generación de reportes de auditoría en formato exportable (CSV/PDF). | 4 | Diaz Mendoza, Sebastian Victor Andre | **Done** |
| **US-EXP03** | T-EXP08 | Servicio backend de consolidación de trazabilidad | Desarrollar consulta optimizada para agregar historial de lecturas, incidencias resueltas y metadatos de calibración. | 5 | Mallqui Vilca, Dhilsen Armil | **Done** |
| **US-EXP04** | T-EXP09 | Vista matriz multisede con semáforos de estado | Implementar vista consolidadora de múltiples establecimientos farmacéuticos con indicadores rápidos de salud térmica. | 6 | Ramirez Escalante, Carlo Patricio | **Done** |
| **US-EXP04** | T-EXP10 | Asignación y vinculación de operadores por sede | Desarrollar funcionalidad de interfaz para vincular operadores a establecimientos mediante llamadas al endpoint de profiles. | 4 | Dinklange Arevalo, Sandro | **Done** |
| **US-EXP01 a 04** | T-EXP11 | Configuración de pipeline CI/CD y despliegue To-Be | Validar build automatizado en GitHub Actions, auto-deploy en Vercel (frontend) y Render (backend), y verificar variables de entorno. | 4 | Oblitas Alcalde, Rodrigo | **Done** |

---

##### 8.3.3.2. Implemented To-Be Landing Page Evidence

Landing Page desplegada en Vercel: https://landing-page-kairolabs.vercel.app

![Landing Page - Inicio](../assets/chapter-5/landing-hero.jpg)

![Landing Page - Tecnología](../assets/chapter-5/landing-tecnologia.jpg)

![Landing Page - Sectores](../assets/chapter-5/landing-sectores.jpg)

![Landing Page - Planes](../assets/chapter-5/landing-planes.png)

<p align="center">
  <img src="../assets/chapter-5/landing-responsive-mobile.jpg" alt="Landing Page en smartphone" width="300">
</p>

##### 8.3.3.3. Implemented To-Be Frontend-Web Application Evidence

Web Application desplegada en Vercel: https://kairo-labs-frontend.vercel.app

![Web App - Login](../assets/chapter-5/web-login.jpg)

![Web App - Registro](../assets/chapter-5/web-register-entidad.jpg)

![Web App - Inicio](../assets/chapter-5/web-home-entidad.png)

![Web App - Establecimientos](../assets/chapter-5/web-establecimientos.png)

![Web App - Mapa de establecimientos](../assets/chapter-5/web-mapa-establecimientos.jpg)

![Web App - Dispositivos](../assets/chapter-5/web-dispositivos.png)

![Web App - Detalle de dispositivo](../assets/chapter-5/web-dispositivo-detalle.png)

![Web App - Transportes](../assets/chapter-5/web-transportes.png)

![Web App - Planes](../assets/chapter-5/web-planes.png)

##### 8.3.3.4. Implemented To-Be Native-Mobile Application Evidence

Versión móvil de KairoLabs: https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Mobile

![App móvil - Inicio, menú, Nosotros y Tecnología](../assets/chapter-5/mobile-overview-1.png)

![App móvil - Sectores, Planes y Contacto](../assets/chapter-5/mobile-overview-2.png)

##### 8.3.3.5. Implemented To-Be RESTful API and/or Serverless Backend Evidence

https://medi-track-sensor-platform.onrender.com/swagger/index.html

![Swagger UI](../assets/chapter-5/api-swagger-overview.png)

![GET establishments](../assets/chapter-5/api-get-establishments.png)

![GET devices](../assets/chapter-5/api-get-devices.png)

##### 8.3.3.6. Team Collaboration Insights

El equipo Aether System trabajó de forma colaborativa en la organización de GitHub `1ASI0732-2620-9082-Aether-System`, distribuyendo el desarrollo entre los repositorios del informe, la Landing Page, la Web Application y la aplicación móvil.

![Contributors - Project Report](../assets/chapter-5/gh-report-contributors.png)

![Contributors - Landing Page](../assets/chapter-5/gh-landing-contributors.png)

![Contributors - Web Application](../assets/chapter-5/gh-frontend-contributors.png)

![Contributors - Mobile](../assets/chapter-5/gh-mobile-contributors.png)
### 8.3.4. To-Be Validation Interviews

Se desarrolla un escenario de validación simulado de KairoLabs con seis participantes ficticios, tres por segmento. Los nombres, edades, respuestas y resultados de 8.3.4 a 8.4.2 pertenecen a este ejercicio. Los seis enlaces proporcionados se asocian a los registros en el mismo orden.

#### 8.3.4.1. Diseño de Entrevistas

**Objetivo.** Revisar si las mejoras To-Be ayudan a interpretar una alerta, consultar el historial y supervisar los establecimientos. El interés está en conocer qué entiende la persona, dónde necesita ayuda y qué cambiaría para usar la plataforma en su trabajo.

**Participantes y dinámica.** El diseño considera tres personas de almacenes farmacéuticos y tres gestores de establecimientos de salud. Cada sesión se plantea como una entrevista semiestructurada de 20 a 25 minutos: presentación del contexto, recorrido por tareas y preguntas de cierre. Se utiliza el mismo conjunto de dispositivos, lecturas y sedes de prueba. El entrevistador primero deja que la persona intente resolver cada tarea y después registra las ayudas solicitadas.

| Tarea | Segmento | Qué se observa | Relación con el diseño experimental |
| :--- | :--- | :--- | :--- |
| Identificar una alerta fuera de rango y explicar su prioridad. | Ambos. | Si reconoce el establecimiento, el dispositivo y la condición que requiere atención. | Q-02; EXP-02; MD-02. |
| Diferenciar una lectura vigente de un sensor sin comunicación. | Ambos. | Si consulta la hora de la última lectura y evita interpretar un dato antiguo como una condición actual. | Q-06 y Q-07; EXP-06; MD-07 y MD-08. |
| Recuperar el historial de una sede, dispositivo y periodo. | Ambos. | Si encuentra el conjunto solicitado y aplica los filtros adecuados. | Q-03; EXP-03; MD-03. |
| Registrar la acción tomada ante una alerta. | Personal operativo. | Si entiende la diferencia entre visualizar la alerta y registrar su atención. | Q-02 y Q-07; US-EXP01. |
| Revisar varias sedes e identificar cuál requiere atención. | Gestores. | Si puede comparar estados y entrar al establecimiento correspondiente. | Q-05; EXP-05; MD-05. |

**Preguntas comunes**

1. ¿Qué información miraste primero y por qué?
2. ¿Qué harías al encontrar esta alerta?
3. ¿Cómo comprobarías si la lectura que ves sigue siendo actual?
4. ¿Cómo buscarías lo ocurrido con este dispositivo durante un periodo concreto?
5. ¿Qué parte te hizo dudar o te obligó a pedir ayuda?

**Preguntas para personal operativo**

- ¿Qué necesitarías registrar después de atender una desviación?
- ¿Qué harías si cambia el turno mientras una alerta sigue abierta?
- ¿Podrías realizar este recorrido desde el celular durante tu jornada?

**Preguntas para gestores**

- ¿Cómo decidirías qué sede revisar primero?
- ¿Qué datos tendría que incluir el historial para que te sirva en una auditoría?
- ¿Qué comprobarías antes de confiar en una lectura o comparar dos establecimientos?

En cada registro se distingue entre una tarea completada sin ayuda y una que requirió orientación. Los comentarios sobre utilidad se usan para revisar la experiencia; no equivalen a medir reducción de deterioro, precisión física del sensor o pérdidas económicas.

#### 8.3.4.2. Registro de Entrevistas

**Segmento 1: Personal operativo de almacenes farmacéuticos**

##### Entrevista TV-01

| Campo | Registro |
| :--- | :--- |
| Nombre y apellidos | Lucía Paredes Huamán |
| Edad | 29 años |
| Ocupación | Técnica de farmacia encargada de recepción y conservación. |
| Contexto | Almacén farmacéutico en Lima; seis años de experiencia. |
| Enlace asociado | [Video 1](https://upcedupe-my.sharepoint.com/:v:/g/personal/u20241c630_upc_edu_pe/IQDai321wS-vQI5NkwqzffbFAXzp9qMoHxmiW24EyAcCOvA?e=bFRsDw) |
| Imagen | |

Lucía identificó la alerta y registró una acción sin orientación. También encontró el historial solicitado. Su principal duda apareció al revisar un dispositivo sin comunicación: interpretó primero el último valor visible como una lectura actual y necesitó ayuda para revisar su hora. Comentó: «Si el dato es de hace rato, necesito darme cuenta antes de tomar una decisión». Propuso mostrar la antigüedad de la lectura junto a la temperatura y resaltar el estado de desconexión.

##### Entrevista TV-02

| Campo | Registro |
| :--- | :--- |
| Nombre y apellidos | Marco Antonio Salazar Rojas |
| Edad | 38 años |
| Ocupación | Auxiliar de almacén y responsable de controles por turno. |
| Contexto | Distribuidora farmacéutica en Callao; doce años de experiencia. |
| Enlace asociado | [Video 2](https://upcedupe-my.sharepoint.com/:v:/g/personal/u20241c630_upc_edu_pe/IQDbmsfyIXK3QqaaOqt_aeWGAV4e-Il19oqA99QkHEzMAc8?e=KhGQHk) |
| Imagen | |

Marco reconoció la alerta fuera de rango y pudo registrar la atención. Necesitó orientación para diferenciar una interrupción de comunicación de una condición normal y para seleccionar el dispositivo correcto en el historial. En la vista móvil le costó ubicar los filtros. Señaló: «En el cambio de turno quiero saber qué se atendió y qué sigue abierto». Sugirió destacar los filtros activos y mantener visible el estado de cada alerta durante el relevo.

##### Entrevista TV-03

| Campo | Registro |
| :--- | :--- |
| Nombre y apellidos | Rosa Elena Quispe Medina |
| Edad | 46 años |
| Ocupación | Técnica de farmacia responsable de cadena de frío. |
| Contexto | Almacén de una clínica en Arequipa; dieciocho años de experiencia. |
| Enlace asociado | [Video 3](https://upcedupe-my.sharepoint.com/:v:/g/personal/u20241c630_upc_edu_pe/IQDi-cMMD4MVQrnh6pxjUCJPATF1jBzFOBvFA2QWanMa6Bk?e=eXblQH) |
| Imagen | |

Rosa interpretó la alerta, distinguió el sensor desconectado y recuperó el historial sin ayuda. Al registrar una acción, confundió cerrar el detalle de la alerta con marcarla como atendida. Después de una indicación completó el recorrido. Consideró útil el gráfico para revisar lo sucedido durante el turno anterior y comentó: «Me sirve ver la tendencia, pero también quiero saber qué hizo la persona que atendió el caso». Recomendó aclarar el botón de registro y conservar la acción asociada al incidente.

**Segmento 2: Entidades de salud y gestores farmacéuticos**

##### Entrevista TV-04

| Campo | Registro |
| :--- | :--- |
| Nombre y apellidos | Daniela Ramos Cáceres |
| Edad | 35 años |
| Ocupación | Química farmacéutica y coordinadora de establecimientos. |
| Contexto | Red de tres centros de salud en Lima; nueve años de experiencia. |
| Enlace asociado | [Video 4](https://upcedupe-my.sharepoint.com/:v:/g/personal/u20241c630_upc_edu_pe/IQC8tnB_rovTQ6DGnwt7bVdEAZMAWnBciSuIPmpKYlqED_k?e=M53Mg7) |
| Imagen | |

Daniela completó sin ayuda la interpretación de la alerta, la revisión de vigencia, la consulta del historial y la comparación de sedes. Encontró útil que el panel reuniera los establecimientos, aunque pidió que los filtros de sede, dispositivo y periodo también quedaran identificados en el reporte. Explicó: «Si comparto el archivo, la otra persona tiene que entender de dónde salió cada registro». Propuso mantener esos datos visibles al revisar y exportar el historial.

##### Entrevista TV-05

| Campo | Registro |
| :--- | :--- |
| Nombre y apellidos | Eduardo Cruz Valverde |
| Edad | 42 años |
| Ocupación | Jefe de operaciones de una distribuidora farmacéutica. |
| Contexto | Supervisión de cinco almacenes en Trujillo; dieciséis años de experiencia. |
| Enlace asociado | [Video 5](https://upcedupe-my.sharepoint.com/:v:/g/personal/u20241c630_upc_edu_pe/IQDvP5TKmSk_TLsAtGPOdS5lAd9DDPyxtxPe-1W3nFx0nrY?e=DG2LHg) |
| Imagen | |

Eduardo identificó la sede con una alerta activa y distinguió las lecturas vigentes sin orientación. En el historial eligió inicialmente un dispositivo de otra sede y pidió ayuda para corregir el filtro. Consideró que la supervisión centralizada podía facilitar su trabajo, pero señaló que una vista rápida no bastaba para estimar pérdidas evitadas. Comentó: «Primero necesito ubicar el problema y luego revisar el lote y el registro del incidente». Sugirió mostrar la relación entre sede y dispositivo al filtrar.

##### Entrevista TV-06

| Campo | Registro |
| :--- | :--- |
| Nombre y apellidos | Patricia Mercedes Vega Soto |
| Edad | 51 años |
| Ocupación | Directora técnica de una red de farmacias. |
| Contexto | Supervisión de cuatro establecimientos en Cusco; veinticuatro años de experiencia. |
| Enlace asociado | [Video 6](https://upcedupe-my.sharepoint.com/:v:/g/personal/u20241c630_upc_edu_pe/IQD68cRq-kvTS7_eY1zC5UBlAS3K_fwehZNaR4SP538y6C4?e=FQjYcr) |
| Imagen | |

Patricia consultó el historial y comparó los establecimientos sin ayuda. Necesitó orientación para diferenciar una alerta ambiental de un sensor sin comunicación y revisar la antigüedad del dato. Pidió que los estados tuvieran texto además de colores. Señaló: «Verde debería decirme que el dato es actual, no solamente que la última temperatura estuvo bien». Propuso separar con claridad los estados normal, fuera de rango y sin comunicación.

## 8.4. Experiment Aftermath & Analysis

El análisis reúne los seis registros simulados y los relaciona con las preguntas de 8.1 y las hipótesis de 8.2. Se revisa la comprensión de las tareas y se proponen decisiones para la siguiente iteración de KairoLabs.

### 8.4.1. Analysis and Interpretation of Results

**Resumen del recorrido simulado**

| Registro | Interpreta la alerta | Distingue una lectura vigente | Recupera el historial solicitado | Registra una acción | Compara varias sedes |
| :--- | :---: | :---: | :---: | :---: | :---: |
| TV-01 — Lucía | Sin ayuda | Con ayuda | Sin ayuda | Sin ayuda | — |
| TV-02 — Marco | Sin ayuda | Con ayuda | Con ayuda | Sin ayuda | — |
| TV-03 — Rosa | Sin ayuda | Sin ayuda | Sin ayuda | Con ayuda | — |
| TV-04 — Daniela | Sin ayuda | Sin ayuda | Sin ayuda | — | Sin ayuda |
| TV-05 — Eduardo | Sin ayuda | Sin ayuda | Con ayuda | — | Sin ayuda |
| TV-06 — Patricia | Con ayuda | Con ayuda | Sin ayuda | — | Sin ayuda |

El guion asigna el registro de acciones al segmento operativo y la comparación de sedes al segmento gestor; el guion largo indica que esa tarea no formó parte del recorrido de ese perfil.

Cinco de los seis perfiles interpretan la alerta sin orientación, pero solo tres distinguen por sí mismos si el dato sigue vigente. Es el hallazgo que más afecta la lectura del panel: un valor antiguo dentro de rango puede confundirse con una situación actual normal. La siguiente iteración debe mostrar la hora de la última lectura y separar visualmente la desconexión de una desviación ambiental.

Cuatro perfiles recuperan el historial sin ayuda. Marco y Eduardo necesitan corregir la selección del dispositivo, por lo que conviene revisar la relación entre sede y dispositivo y hacer visibles los filtros activos. En el registro de acciones, dos de los tres perfiles operativos completan el recorrido sin orientación; el caso de Rosa muestra que cerrar un detalle y registrar la atención deben ser acciones claramente distintas.

Los tres gestores comparan las sedes sin ayuda. Sus comentarios destacan la utilidad de centralizar la revisión y conservar el contexto de los reportes. Esto orienta mejoras de navegación y trazabilidad, sin convertir la preferencia por el panel en una estimación de ahorro o de pérdidas evitadas.

**Interpretación por hipótesis**

| Hipótesis y métrica | Lectura del ejercicio | Decisión para la siguiente iteración |
| :--- | :--- | :--- |
| H1 — Monitoreo continuo; MD-01. | Los perfiles valoran consultar tendencias y revisar lo ocurrido entre turnos. El recorrido no mide una reducción del 30 % en incidentes de deterioro. | Mantener la hipótesis de campo y relacionar las lecturas con lotes e incidentes confirmados, como establece EXP-01. |
| H2 — Respuesta a alertas; MD-02. | La mayoría reconoce la alerta, pero aparecen dudas sobre desconexión, relevo de turno y registro de atención. La comprensión de la interfaz no demuestra una reducción del 25 % en la mediana de respuesta. | Aclarar los estados y el registro de acciones; después comparar detección y primera respuesta con marcas de tiempo equivalentes. |
| H3 — Evidencia para auditoría; MD-03. | El historial resulta comprensible para cuatro perfiles; los otros dos requieren ayuda con los filtros. No se cronometró una comparación manual-digital para evaluar el umbral del 20 %. | Revisar filtros de sede y dispositivo y conservar el periodo consultado en el reporte. Retomar la comparación de solicitudes completas de EXP-03. |
| H4 — Concordancia de lecturas; MD-04. | Revisar un valor en pantalla permite evaluar su interpretación, pero no su exactitud física ni una mejora relativa del 25 %. | Conservar la validación pareada con instrumento de referencia y tolerancias definidas en EXP-04. |
| H5 — Supervisión multisede y pérdidas; MD-05 y MD-06. | Los tres gestores completan la revisión de sedes. Esto permite revisar el recorrido, pero no acredita los umbrales de 30 % en tiempo y 20 % en pérdidas. | Mantener separados el tiempo de revisión y el resultado económico; aplicar las tareas comparativas y los registros documentales de EXP-05. |

**Ajustes propuestos para el producto**

| Ajuste | Registros que lo motivan | Historia relacionada | Cómo revisar el cambio |
| :--- | :--- | :--- | :--- |
| Mostrar última actualización y diferenciar normal, fuera de rango y sin comunicación mediante texto y color. | TV-01, TV-02 y TV-06. | US-EXP01 y US-EXP02. | Repetir el recorrido con lecturas vigentes y antiguas y comprobar su interpretación sin ayuda. |
| Aclarar la acción para registrar atención y mantener visible el estado durante el cambio de turno. | TV-02 y TV-03. | US-EXP01. | Pedir al operador que registre una acción y vuelva a consultar el incidente. |
| Vincular el filtro de dispositivo con la sede seleccionada y mostrar los filtros activos. | TV-02 y TV-05. | US-EXP03. | Solicitar el historial de una sede y dispositivo concretos y verificar el conjunto recuperado. |
| Conservar sede, dispositivo y periodo al consultar y exportar el historial. | TV-04 y TV-05. | US-EXP03 y US-EXP04. | Revisar que el reporte conserve el contexto de la consulta y sus registros. |

Estos ajustes se proponen a partir de la simulación; no se registran como cambios implementados ni como confirmación de las cinco hipótesis de negocio.

### 8.4.2. Re-scored and Re-prioritized Question Backlog

Se conserva la fórmula de 8.1.4: **P = (6 − C) + R + I + T**, con valores de 1 a 5 para confianza, riesgo, impacto e interés. Al tratarse de registros ficticios, **C mantiene su puntuación inicial**: la simulación no aumenta la evidencia real disponible. Los cambios en R, I y T representan una propuesta de planificación a partir de los problemas explorados.

| Orden | Pregunta | C | R | I | T | P anterior | P actual | Decisión propuesta |
| :---: | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :--- |
| 1 | Q-06. Cobertura y controles. | 1 | 5 | 5 | 5 | 18 | 20 | Comprobar vigencia, completitud y estados de comunicación antes de interpretar las demás medidas. Mantener EXP-06 en deep backlog. |
| 2 | Q-04. Concordancia de lecturas. | 2 | 5 | 5 | 5 | 19 | 19 | Conservar la prioridad de EXP-04: una lectura comprensible también debe ser confiable. Preparar instrumento, tolerancias y pares comparables. |
| 3 | Q-07. Barreras de atención. | 1 | 5 | 4 | 5 | 15 | 19 | Pasar de broad a deep backlog por las dudas sobre desconexión, relevo y registro de acciones. Detallar estos recorridos junto con EXP-02. |
| 4 | Q-02. Respuesta a alertas. | 2 | 5 | 5 | 4 | 18 | 18 | Mantener EXP-02 en deep backlog y separar la generación del aviso de la primera acción registrada. |
| 5 | Q-08. Línea base y variabilidad. | 1 | 4 | 4 | 5 | 17 | 18 | Dar mayor urgencia a los registros basales que permiten calcular la escala e interpretar las comparaciones. |
| 6 | Q-03. Evidencia para auditoría. | 2 | 4 | 5 | 5 | 16 | 18 | Mantener EXP-03 en deep backlog; revisar filtros y contexto del reporte antes de comparar tiempos de solicitudes completas. |
| 7 | Q-01. Incidentes de deterioro. | 1 | 5 | 5 | 2 | 17 | 17 | Mantener EXP-01 en broad backlog y conservar el seguimiento de tres meses con lotes e incidentes documentados. |
| 8 | Q-05. Supervisión y pérdidas. | 2 | 4 | 4 | 3 | 15 | 15 | Mantener EXP-05 en broad backlog y el seguimiento de seis meses. Distinguir la facilidad de revisar sedes del efecto económico. |

Q-06 sube por el riesgo de interpretar datos antiguos como actuales. Q-07 gana detalle por las dudas que aparecen durante la atención y el relevo. Q-03 aumenta por la importancia de recuperar el historial correcto, y Q-08 por la necesidad de contar con una referencia para las comparaciones.

En los empates se aplica primero el mayor riesgo y luego las dependencias de 8.1.4: Q-02 precede a Q-08 y Q-03 por riesgo; Q-08 precede a Q-03 porque aporta la línea base para su comparación. Cuando no hay una dependencia directa que resuelva el empate, se conserva el orden anterior, como en Q-04 y Q-07.

La secuencia de ejecución propuesta comienza con Q-06 y la recolección basal de Q-08; continúa con la preparación de Q-04 y la exploración de Q-07; después retoma EXP-02 y EXP-03. La posición en la tabla expresa prioridad de aprendizaje, mientras que esta secuencia respeta los requisitos necesarios para ejecutar cada comparación.

## 8.5. Continuous Learning

El aprendizaje continuo de KairoLabs conecta las preguntas de 8.1, el diseño de 8.2, los recorridos de 8.3 y las decisiones de 8.4 con la siguiente iteración del producto. El objetivo es conservar qué se examinó, con qué evidencia, qué interpretación admite esa evidencia y qué decisión corresponde tomar. Cada ciclo debe permitir revisar o mantener una creencia, incluso cuando el resultado sea inconcluso.

En esta entrega, el insumo de 8.4 son **seis registros simulados**. Sus patrones permiten ensayar el análisis y proponer mejoras, pero no constituyen observaciones de usuarios reales ni resultados de los pilotos. Por ello, se mantiene la confianza inicial del backlog y se conservan como pendientes las comparaciones de negocio de EXP-01 a EXP-05. Los resultados de pruebas técnicas, las mediciones de Lighthouse y la demostración del producto se interpretan dentro de sus respectivos alcances.

### 8.5.1. Shareback Session Artifacts: Learning Workflow

La sesión de *shareback* es el espacio propuesto para compartir evidencia, contrastar interpretaciones y acordar el siguiente paso. Los siguientes artefactos se preparan a partir del informe para apoyar esa sesión. **No se registra una reunión como celebrada ni se atribuyen acuerdos, asistencia o aprobaciones sin un acta que los sustente.**

**Paquete de artefactos para el shareback**

| Artefacto | Contenido preparado y referencia | Uso en la sesión | Estado |
| :--- | :--- | :--- | :--- |
| Preguntas y tarjetas | Q-01 a Q-08 y EXP-01 a EXP-06 de 8.1. | Recordar qué se busca aprender y los criterios definidos antes de ejecutar. | Documentado. |
| Protocolo y medidas | Hipótesis, MD-01 a MD-08, condiciones, escala y seguimiento de 8.2. | Revisar si la captura permite responder cada pregunta sin cambiar las metas después de medir. | Documentado; requisitos de ejecución por confirmar. |
| Resumen del ejercicio | Matriz de los seis recorridos simulados de 8.4.1. | Examinar problemas de vigencia, atención, filtros y contexto de reportes. | Simulación documental; no evidencia de campo. |
| Registro de aprendizajes y decisiones | Matriz LC-01 a LC-05 incluida a continuación. | Separar observación del ejercicio, interpretación y propuesta de acción. | Preparado para revisión. |
| Backlog revisado | Puntuaciones y secuencia de 8.4.2. | Contrastar prioridades y dependencias conservando la confianza inicial. | Propuesta de repriorización. |
| Demostración integrada | Video enlazado en 8.6.1. | Presentar los recorridos del producto y discutir su relación con el protocolo. | Enlace aportado por el equipo; no sustituye resultados experimentales. |
| Acta de shareback | Fecha efectiva, participantes, versión revisada, decisiones, responsable, plazo y discrepancias. | Dejar trazabilidad de los acuerdos que efectivamente se adopten. | Pendiente de celebración y registro. |

**Registro de aprendizajes y decisiones propuestas**

| ID | Insumo del ejercicio de 8.4 | Interpretación y límite | Siguiente acción propuesta | Pregunta e historia relacionadas | Comprobación posterior |
| :--- | :--- | :--- | :--- | :--- | :--- |
| LC-01 | Tres de los seis perfiles simulados distinguen sin ayuda una lectura vigente. | La vigencia merece revisión en el escenario ensayado; la proporción no estima el comportamiento de usuarios reales. | Mostrar última lectura y diferenciar normal, fuera de rango y sin comunicación con texto y color. | Q-06 y Q-07; US-EXP01 y US-EXP02. | Preparar EXP-06 y observar recorridos reales autorizados con lecturas vigentes, antiguas y ausentes. |
| LC-02 | Dos de los tres perfiles operativos simulados completan el registro de una acción sin orientación. | El cierre de un detalle y la atención de una alerta deben distinguirse. No se ha medido MD-02. | Revisar la acción de atención, su confirmación y la continuidad entre turnos. | Q-02 y Q-07; US-EXP01. | Verificar el flujo y las marcas temporales antes de la comparación de EXP-02. |
| LC-03 | Dos perfiles simulados requieren ayuda para recuperar el historial por sede y dispositivo. | La selección de filtros puede afectar la tarea; no se conoce todavía el ahorro de tiempo. | Vincular los dispositivos con su sede y mantener visibles los filtros activos. | Q-03; US-EXP03. | Repetir solicitudes equivalentes, comprobar completitud y aplicar MD-03 con el protocolo de EXP-03. |
| LC-04 | Los tres gestores simulados completan la comparación de sedes. | El ejercicio permite revisar el recorrido, pero no acredita menores tiempos ni pérdidas. | Conservar la supervisión centralizada y preparar la captura separada de tiempos y pérdidas documentadas. | Q-05; US-EXP04. | Aplicar MD-05 y MD-06 por separado en EXP-05. |
| LC-05 | El ejercicio no incluye instrumentos de referencia, tasas basales ni observación longitudinal. | No permite contrastar precisión física, deterioro o impacto económico. | Preparar Q-08, instrumentos, tolerancias, acceso a registros y cálculo de escala antes de iniciar los pilotos. | Q-01, Q-04 y Q-08; EXP-01 y EXP-04. | Revisar requisitos y protocolo; conservar el estado pendiente cuando falte evidencia. |

**Learning Workflow**

1. **Recuperar la pregunta y el protocolo.** Identificar Q, EXP, hipótesis, métrica y versión del producto. Definir si se revisa una simulación, una comprobación técnica o una observación de campo.
2. **Preparar la evidencia.** Reunir registros autorizados, condiciones de captura e incidencias. Identificar datos faltantes y mantener separados los entornos de prueba y piloto.
3. **Compartir e interpretar.** Presentar el hallazgo junto con su fuente y límites. Examinar explicaciones alternativas, como conectividad, experiencia previa, aprendizaje o diferencias entre sedes.
4. **Tomar una decisión trazable.** Proponer continuar, ajustar, repetir, posponer o detener. Registrar qué evidencia motivaría reconsiderar la decisión; una ausencia de medición no equivale a un resultado favorable.
5. **Actualizar el trabajo.** Vincular la decisión con el question backlog de 8.4.2 y, cuando corresponda, con las historias y tareas To-Be de 8.3. Un cambio propuesto no pasa a implementado sin su evidencia.
6. **Verificar y aprender nuevamente.** Repetir la tarea o comparación adecuada después del cambio, conservar la versión del protocolo y preparar el siguiente shareback. Aumentar la confianza únicamente con evidencia pertinente a la pregunta.

**Agenda sugerida y registro de cierre**

Se propone una sesión de 30 minutos: cinco para recordar preguntas y alcance, diez para revisar evidencia, diez para discutir decisiones y cinco para registrar responsables y próximos pasos. La duración es una propuesta de organización, no una sesión ya ejecutada.

| Campo del acta | Información que se registrará al realizar la sesión |
| :--- | :--- |
| Identificación | Fecha, participantes efectivos, facilitador y versión del informe/producto. |
| Evidencia revisada | Enlaces a registros, protocolo y artefactos; tipo de evidencia y restricciones. |
| Decisión | Pregunta, aprendizaje, decisión adoptada y desacuerdos relevantes. |
| Seguimiento | Responsable y revisor asignados, plazo acordado y comprobación requerida. |
| Cierre del ciclo | Resultado de la comprobación y enlace al backlog actualizado. |

Este flujo permite que la siguiente iteración responda al aprendizaje disponible y no solamente a una lista de funcionalidades. La sesión y su acta quedan como actividad pendiente; los artefactos anteriores ya organizan el material documental para realizarla.

## 8.6. To-Be Software Platform Pre-launch

La preparación previa al lanzamiento reúne la presentación del producto integrado y una revisión de sus implicaciones globales, económicas, ambientales y sociales. Para KairoLabs, la demostración del ecosistema desplegado permite comunicar sus recorridos principales; la evaluación GEES ayuda a distinguir las capacidades documentadas de los impactos que requieren observación posterior.

El alcance presentado comprende Landing Page, frontend web, backend y documentación de la API. La vista móvil del frontend debe distinguirse de una aplicación nativa. La disponibilidad de una demostración no acredita por sí sola operación clínica, exactitud de sensores, cumplimiento normativo, disponibilidad sostenida ni ejecución de los pilotos previstos.

### 8.6.1. About-the-Product Intro Video

**Nombre de presentación:** *KairoLabs — Video final del producto: ecosistema integrado de Landing Page, frontend y backend*.

<p align="center">
  <img src="../assets/chapter-8/about-the-product-dashboard.png" alt="Vista del panel de KairoLabs mostrada en la demostración del producto" width="900">
</p>

*Figura 8.6.1-1. Panel de inicio de KairoLabs con accesos de gestión y Centro de Control Operativo.*

*Nota.* Captura proporcionada por el equipo como referencia visual del video. Presenta la aplicación ejecutada localmente con datos de demostración; no acredita resultados de los experimentos de negocio.

**Enlace al video final del producto:** https://drive.google.com/drive/folders/17UCreuvhtV31VfqfocBDZ8wOHEVsYKmO?usp=sharing

El enlace proporcionado corresponde a una carpeta de Google Drive; el nombre anterior identifica la presentación en este informe y no afirma que sea el nombre exacto del archivo almacenado. La descripción del recorrido corresponde a la información aportada por el equipo.

El video demuestra el funcionamiento del ecosistema desplegado: Landing Page, flujo de autenticación, dashboard de monitoreo, gestión de establecimientos y dispositivos, y documentación Swagger de la API. La presentación conecta la propuesta de valor de KairoLabs con las tareas del personal operativo y de los gestores farmacéuticos.

| Componente del recorrido | Contenido presentado | Relación con el proyecto |
| :--- | :--- | :--- |
| Landing Page | Presentación de KairoLabs y acceso al ecosistema. | Comunica la solución y sus segmentos objetivo. |
| Autenticación | Acceso a la aplicación mediante el flujo de inicio de sesión. | Introduce el entorno de trabajo del usuario. |
| Dashboard de monitoreo | Consulta de condiciones y estados disponibles en el panel. | Contextualiza las preguntas de monitoreo y supervisión de 8.1. |
| Establecimientos | Recorrido de gestión de sedes. | Muestra la organización operativa relacionada con la supervisión multisede. |
| Dispositivos | Consulta y gestión de dispositivos y su información. | Presenta el contexto de las lecturas utilizadas por la plataforma. |
| API y Swagger | Presentación de la documentación y operaciones expuestas por el backend. | Explica el componente de servicios que soporta la aplicación integrada. |

**Alcance de la evidencia:** la demostración presenta recorridos funcionales. No se utiliza para declarar cumplidas las reducciones de deterioro, respuesta, preparación de auditoría o pérdidas de 8.2. Tampoco sustituye los datos de calibración, los registros longitudinales, las pruebas de seguridad ni las entrevistas reales. No se asignan duración ni marcas de tiempo porque no se han documentado en esta sección.

Antes de la entrega, el equipo debe comprobar que la carpeta y el archivo de video permitan visualización al evaluador. Si se obtiene un enlace directo al archivo, podrá sustituirse el enlace de carpeta sin cambiar el alcance de la evidencia.

### 8.6.2. Resumen usando Gees Framework

El marco **GEES** organiza la revisión en cuatro lentes: **Global, Economic, Environmental y Social**, conforme a la matriz de resumen del sistema informático de la guía del curso. Se aplica al contexto de KairoLabs sin trasladar como resultados propios los ejemplos de ahorro, energía o certificación que aparecen en el modelo referencial.

| Lente GEES | Indicador o criterio clave | Hallazgo o estado documentado de KairoLabs | Aprendizaje y acción previa al lanzamiento | Estándar o marco de referencia |
| :--- | :--- | :--- | :--- | :--- |
| **Global** | Interoperabilidad, dependencias tecnológicas y tratamiento de datos. | El informe describe una aplicación web Vue y una API ASP.NET Core con MySQL, servicios desplegados y documentación Swagger. Las consultas integradas y el video presentan el intercambio entre componentes; no acreditan residencia de datos, arquitectura multirregión ni conformidad transfronteriza. | Precisar proveedores, ubicación y acceso a datos, contratos de API y configuración por entorno. Revisar las discrepancias tecnológicas del capítulo antes de asumir una nueva arquitectura. Relacionar la disponibilidad de datos con Q-06. | ISO/IEC 27001 e ISO/IEC 27701, citadas por la guía como referencias de seguridad y privacidad; sin afirmar certificación. |
| **Economic** | Eficiencia operativa, costo total de propiedad y resultados de conservación. | Se plantean MD-03 para preparar evidencia, MD-05 para supervisión y MD-06 para pérdidas. No se presentan aquí costos consolidados, ROI, ahorro medido ni resultados de los pilotos de tres o seis meses. Los recorridos simulados no prueban esos beneficios. | Recoger la línea base de Q-08, documentar costos de alojamiento, dispositivos y mantenimiento, y evaluar EXP-03 y EXP-05 con sus propios datos. Mantener separadas eficiencia de consulta y pérdidas económicas. | ISO/IEC 25010 y marcos de gestión financiera de TI, como referencias de calidad y evaluación del valor indicadas en la guía. |
| **Environmental** | Conservación de productos, consumo de recursos y ciclo de vida de dispositivos. | Reducir deterioro podría disminuir descarte farmacéutico, pero es un beneficio esperado de MD-01, no un resultado demostrado. No se dispone aquí de mediciones de energía, emisiones, PUE, origen renovable del alojamiento ni gestión certificada de residuos electrónicos. | Ejecutar EXP-01 con incidentes y lotes documentados; recopilar información verificable de infraestructura y dispositivos si se evalúa impacto ambiental. No convertir una reducción monetaria en emisiones evitadas sin un método y datos específicos. | ISO 14001 y GHG Protocol, incluidos en el modelo de la guía como referencias de gestión ambiental y emisiones; no como conformidades acreditadas. |
| **Social** | Comprensión, accesibilidad, protección del usuario y responsabilidad profesional. | El capítulo VI documenta evaluaciones heurísticas y el 8.2.7 incluye diagnósticos de accesibilidad de Lighthouse. Los recorridos simulados de 8.4 destacan la vigencia del dato, los estados y los filtros; no representan evidencia adicional de usuarios reales ni conformidad integral de accesibilidad. | Priorizar estados con texto y color, hora de última lectura y filtros claros según LC-01 a LC-03. Revalidar con participantes reales autorizados; proteger los registros y mantener mecanismos de revisión humana de decisiones operativas. | ISO 26000, WCAG 2.2 y los Objetivos de Desarrollo Sostenible, como referencias sociales y de accesibilidad recogidas por la guía; sin afirmar cumplimiento o impacto medido. |

**Balance para el pre-launch**

KairoLabs dispone de una propuesta integrada documentada y de un enlace de demostración para comunicar sus recorridos principales. El siguiente paso consiste en revisar las condiciones de medición y las mejoras propuestas, comprobar acceso a la evidencia y preparar los experimentos que todavía requieren datos de campo. La priorización de Q-06, Q-04 y Q-07 de 8.4.2 orienta esa preparación hacia vigencia de datos, confiabilidad e interpretación de alertas.

La matriz GEES no certifica el sistema ni declara un lanzamiento productivo autorizado. Resume qué se conoce, qué se espera conseguir y qué evidencia falta para juzgar los impactos del producto. Sus referencias proceden de la **Matriz de Resumen del Sistema Informático (Framework GEES)** de la guía del curso; utilizarlas como lentes de revisión no sustituye una evaluación formal de conformidad.
