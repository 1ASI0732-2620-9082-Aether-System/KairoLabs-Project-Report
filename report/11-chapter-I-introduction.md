# Capítulo I: Introducción

## 1.1. Startup Profile

### 1.1.1. Descripción de la Startup

Aether System nace como una propuesta tecnológica enfocada en mejorar la conservación de medicamentos y otros productos termosensibles dentro de organizaciones del sector salud. Su objetivo principal es brindar a clínicas, farmacias, hospitales y operadores logísticos una herramienta digital que les permita anticiparse a desviaciones en las condiciones de almacenamiento y transporte, antes de que estas comprometan la calidad e inocuidad del producto.

La solución, denominada KairoLabs, consiste en una plataforma compuesta por una aplicación web responsive y una aplicación móvil nativa que integran diversas funcionalidades orientadas a la trazabilidad sanitaria, tales como el monitoreo continuo de variables ambientales críticas (temperatura, humedad y exposición a la luz), la generación de alertas automáticas ante desviaciones respecto a los rangos permitidos y un histórico auditable de las condiciones de conservación por lote.

El valor diferencial de la propuesta radica en centralizar, dentro de una sola plataforma, tanto mecanismos de supervisión preventiva como de reacción ante incidentes de conservación. Esto es especialmente relevante en un contexto regulatorio donde el almacenamiento de productos termolábiles debe mantenerse dentro de rangos estrictos —usualmente entre 2 °C y 8 °C para cadena de frío— conforme a la normativa nacional de Buenas Prácticas de Almacenamiento (DIGEMID, 2015). Al automatizar este control, KairoLabs reduce la dependencia de registros manuales de temperatura, uno de los puntos críticos identificados en los procesos de fiscalización sanitaria.

Asimismo, la plataforma busca fortalecer la coordinación entre los distintos actores de la cadena de suministro farmacéutica, almacenes, transportistas y puntos de dispensación, promoviendo una gestión logística más trazable, oportuna y alineada con los estándares sanitarios vigentes en el país.

### 1.1.2. Perfiles de integrantes del equipo

| Código     | Descripción | Foto |
|:-----------|:---|:---|
| u202319440 | **Mallqui Vilca, Dhilsen Armil**<br>Ingeniería de Software<br><br>Estudiante de Ingeniería de Software con énfasis en el desarrollo de soluciones escalables, la aplicación de buenas prácticas de ingeniería y la configuración de entornos de despliegue continuo. Orienta su aporte al cumplimiento de hitos técnicos del equipo, a la documentación rigurosa del proceso experimental y a la integración entre evidencia de campo, diseño de producto y pipelines de verificación. | ![Foto](../assets/dhilsen-malqui.png) |

> *(completar)*: los demás integrantes del equipo Aether System incorporarán sus perfiles de manera individual en versiones posteriores del informe.

## 1.2. Solution Profile

### 1.2.1. Antecedentes y problemática

Para analizar el problema de forma estructurada, se aplica la metodología 5W2H, la cual permite identificar los aspectos clave del problema:

**What (¿Qué está ocurriendo?)**
En establecimientos de salud del Perú persisten fallas recurrentes en el almacenamiento de medicamentos y productos termosensibles, incluyendo ambientes de cadena de frío sin condiciones restringidas ni adecuadas para su conservación (Contraloría General de la República, 2026a).

**Why (¿Por qué ocurre?)**
Las principales causas identificadas incluyen:
- Dependencia de registros manuales de temperatura, verificados solo al inicio y al final de la jornada, sin monitoreo continuo (DIGEMID, 2015).
- Ausencia de áreas de cadena de frío exclusivas y de acceso restringido en establecimientos de menor complejidad (Contraloría General de la República, 2026b).
- Escasa automatización de alertas ante desviaciones ambientales, lo que retrasa la detección de incidencias.

**Who (¿A quién afecta?)**
- Hospitales, clínicas, farmacias, almacenes especializados y distribuidores farmacéuticos, sujetos a la supervisión de la Dirección General de Medicamentos, Insumos y Drogas (DIGEMID, 2015).
- Pacientes, como stakeholders indirectos, en tanto dependen de que los medicamentos conserven su efectividad terapéutica hasta el punto de dispensación.

**Where (¿Dónde ocurre?)**
El problema se manifiesta en establecimientos de salud públicos de distintas regiones del país. Informes de control recientes documentan medicamentos almacenados en contacto directo con el piso y áreas de cadena de frío sin condiciones adecuadas en Arequipa y Huánuco (Contraloría General de la República, 2026b; 2026c), así como fármacos vencidos por fallas de almacenamiento en Piura (Contraloría General de la República, 2026d).

**When (¿Cuándo ocurre?)**
La necesidad de control es permanente a lo largo de todo el ciclo logístico —recepción, almacenamiento, distribución y dispensación—, tal como lo exige el Manual de Buenas Prácticas de Almacenamiento (DIGEMID, 2015), siendo la etapa de transporte la de mayor criticidad por su menor trazabilidad.

**How (¿Cómo ocurre?)**
Se han reportado casos de productos sin tarjetas de control visibles, lotes apilados sin parihuelas de soporte y almacenes sin señalización de umbrales de temperatura, lo que dificulta identificar oportunamente una desviación ambiental (Contraloría General de la República, 2026a).

**How Much (¿Cuánto impacto tiene?)**
Según estimaciones difundidas a partir de datos de la Organización Mundial de la Salud, hasta el 25 % de las vacunas y el 20 % de los medicamentos termosensibles a nivel mundial pueden deteriorarse por desviaciones de temperatura durante su logística (Transporte.mx, 2025), lo que representa pérdidas económicas significativas y, sobre todo, un riesgo directo para la efectividad terapéutica y la seguridad del paciente.

**Conclusión del análisis 5W2H:**

Del análisis realizado se concluye que el problema no es únicamente administrativo, sino la ausencia de visibilidad en tiempo real sobre las condiciones ambientales críticas a lo largo de la cadena de conservación de medicamentos. Esta carencia incrementa el riesgo de pérdida de efectividad terapéutica, genera merma económica y expone a los establecimientos de salud a observaciones regulatorias. En este contexto, se identifica la oportunidad de desarrollar una plataforma tecnológica que centralice el monitoreo, la alerta temprana y la trazabilidad de las condiciones de conservación.

**Enunciado del problema**

Actualmente, los establecimientos de salud, farmacias y operadores logísticos del sector farmacéutico no cuentan con una herramienta tecnológica integrada que les permita monitorear en tiempo real las condiciones ambientales críticas durante el almacenamiento y transporte de medicamentos, generar alertas automáticas ante desviaciones y mantener evidencia histórica auditable, lo que incrementa el riesgo de deterioro no detectado y compromete la calidad e inocuidad del producto.

**Restricciones del proyecto**

- El sistema depende de la disponibilidad y correcta calibración de los sensores IoT instalados.
- Limitaciones en la cobertura de conectividad en zonas de menor infraestructura tecnológica.
- Acceso restringido a datos oficiales de fiscalización sanitaria en tiempo real.
- Tiempo de desarrollo acotado al ciclo académico.
- Recursos técnicos y humanos limitados al equipo del curso.

## 1.2.2. Lean UX Process

### 1.2.2.1. Lean UX Problem Statements

#### **Problem Statement 1 — Personal encargado de almacenes farmacéuticos**

**Contexto:**
En establecimientos de salud y nodos de distribución del Perú, la falta de monitoreo continuo de temperatura, humedad y luz limita la capacidad del personal operativo para prevenir el deterioro de medicamentos y documentar condiciones de conservación.

**Problema:**
El personal de almacenes farmacéuticos no dispone de un sistema automatizado que brinde visibilidad en tiempo real y alertas accionables sobre condiciones críticas de almacenamiento, lo que incrementa la vulnerabilidad operativa y el riesgo de merma.

**Pregunta clave:**
¿Cómo proporcionar a los encargados de almacén una solución que permita monitorear condiciones ambientales en tiempo real, reducir incidencias no detectadas y mejorar la trazabilidad en al menos un 30 % durante los primeros seis meses de adopción?

---

#### **Problem Statement 2 — Gestores sanitarios y entidades con responsabilidad regulatoria**

**Contexto:**
Hospitales, redes de distribución y actores con deberes de cumplimiento normativo requieren evidencia confiable de conservación. La dependencia de procesos manuales dificulta demostrar conformidad y gestionar riesgos de calidad de manera sistemática.

**Problema:**
Los gestores sanitarios y las entidades con responsabilidad de supervisión carecen de instrumentos digitales que automaticen el monitoreo, la generación de evidencia histórica y el soporte a auditorías de conservación.

**Pregunta clave:**
¿Cómo diseñar un sistema que facilite el cumplimiento de lineamientos de conservación, de modo que una proporción creciente de lotes monitoreados se mantenga dentro de rangos admisibles durante el primer año de operación, con evidencia auditable?

> *(completar)*: contrastar ambos problem statements con hallazgos de entrevistas de campo (Capítulo II) y ajustar la formulación según evidencia empírica.

### 1.2.2.2. Lean UX Assumptions

#### Supuestos de Negocio

- **Creemos que** el sector salud peruano demanda una solución que combine telemetría IoT y software de monitoreo para reducir riesgos de conservación farmacéutica.
- **Creemos que** el valor percibido principal reside en la prevención de deterioro, la reducción de pérdidas y la disponibilidad de evidencia para auditoría.
- **Creemos que** el modelo de negocio puede sustentarse en suscripción escalable según sedes y sensores conectados, con servicios complementarios de instalación y soporte.
- **Creemos que** la diferenciación de KairoLabs radica en integrar monitoreo en tiempo real, alertas y trazabilidad histórica en un producto multiplataforma orientado al dominio farmacéutico.
- **Creemos que** si no se observa reducción de incidentes o mejora operativa en los primeros tres meses, la renovación de la suscripción se verá comprometida.
- **Creemos que** los almacenes prioritarios cuentan con conectividad suficiente para sincronizar telemetría hacia la nube. *(completar)*: validar cobertura de conectividad en sedes piloto.

---

#### Supuestos de Usuario

- **¿Quién es el usuario?** Personal operativo de almacenes farmacéuticos (operarios, técnicos y responsables de control), además de gestores sanitarios que supervisan cumplimiento.
- **¿Dónde encaja el producto?** En la operación diaria de conservación y en la supervisión gerencial/auditora de condiciones ambientales.
- **¿Qué problemas resuelve?** Falta de visibilidad en tiempo real, detección tardía de anomalías y ausencia de alertas automáticas.
- **¿Cuándo y cómo se usa?** De forma continua durante la jornada, desde web y dispositivos móviles, con dashboards y notificaciones.
- **¿Qué características son indispensables?** Telemetría en tiempo real, alertas por umbral, gestión multi-sede y reportes históricos.
- **¿Cómo debe comportarse?** Interfaz clara, con semántica visual de estados (por ejemplo, normal / advertencia / crítico) y baja carga cognitiva.

---

#### Supuestos de Tecnología

- **Creemos que** las entidades objetivo están dispuestas a adoptar sensores IoT y una plataforma centralizada, siempre que la integración operativa sea gradual y confiable.
- **Creemos que** es factible consolidar telemetría e históricos en una arquitectura cloud con acceso multi-dispositivo.
- **Creemos que** la plataforma puede evolucionar hacia integración con sistemas de inventario existentes sin interrumpir la operación.
- **Creemos que** los sensores pueden operar en rangos ambientales exigentes presentes en ciertos almacenes.
- **Creemos que** la arquitectura debe ser escalable para agregar sedes y dispositivos. *(completar)*: definir criterios de calidad experimental (latencia de alerta, disponibilidad, tasa de falsos positivos) a evaluar en el pipeline de pruebas.

---

#### Supuestos del Mercado

- **Creemos que** la presión por cumplimiento sanitario y digitalización favorece la adopción de soluciones de monitoreo ambiental.
- **Creemos que** el nicho de monitoreo IoT farmacéutico aún presenta espacio para posicionamiento temprano.
- **Creemos que** los clientes valoran soluciones configurables, auditables y fáciles de incorporar a procesos existentes.
- **Creemos que** iniciativas públicas de mejora logística sanitaria refuerzan la pertinencia de productos como KairoLabs. *(completar)*: actualizar el mapa competitivo con fuentes vigentes en el Capítulo II.

### 1.2.2.3. Lean UX Hypothesis Statements

En coherencia con la naturaleza experimental del curso, las hipótesis se expresan de forma verificable y se tratarán como candidatos a evaluación mediante observación, instrumentación de producto y pruebas de software.

**Hipótesis 1 — Decisión operativa oportuna**

**Creemos que lograremos** mejorar la capacidad de decisión del personal de almacén para prevenir deterioro  
**Si** dicho personal accede a KairoLabs con monitoreo en tiempo real de condiciones ambientales  
**Alcanzan** decisiones oportunas ante desviaciones  
**Con** dashboards de telemetría y alertas de temperatura, humedad y luz

> Criterio de verificación propuesto: reducción ≥ 30 % de incidentes de deterioro atribuibles a condiciones ambientales en los primeros tres meses. *(completar)*: protocolo de medición y línea base.

---

**Hipótesis 2 — Respuesta ante alertas**

**Creemos que lograremos** reducir el riesgo asociado a almacenamiento inadecuado  
**Si** las entidades reciben alertas automáticas ante variaciones fuera de rango  
**Alcanzan** tiempos de respuesta más cortos ante eventos críticos  
**Con** un motor de alertas basado en umbrales configurables

> Criterio de verificación propuesto: mejora ≥ 25 % en indicadores de respuesta oportuna durante los primeros tres meses. *(completar)*.

---

**Hipótesis 3 — Trazabilidad y soporte a cumplimiento**

**Creemos que lograremos** fortalecer la trazabilidad y el soporte a auditorías  
**Si** los usuarios disponen de históricos y reportes de condiciones de conservación  
**Alcanzan** mayor eficiencia en la reconstrucción de evidencia ante revisiones  
**Con** módulos de histórico y generación de reportes

> Criterio de verificación propuesto: mejora ≥ 20 % en eficiencia de preparación de auditorías en tres meses. *(completar)*.

---

**Hipótesis 4 — Reducción de error humano por automatización**

**Creemos que lograremos** disminuir la dependencia de registros manuales y los errores asociados  
**Si** se integra telemetría IoT con registro automático en la plataforma  
**Alcanzan** mayor precisión y menor carga operativa de monitoreo  
**Con** captura continua y persistencia automatizada de mediciones

> Criterio de verificación propuesto: mejora ≥ 25 % en precisión de monitoreo y reducción ≥ 30 % de errores operativos de registro en tres meses. *(completar)*.

---

**Hipótesis 5 — Eficiencia multi-sede**

**Creemos que lograremos** optimizar la gestión de recursos en redes con múltiples almacenes  
**Si** las entidades operan un panel centralizado multi-sede  
**Alcanzan** mejor coordinación y menor merma agregada  
**Con** una vista consolidada de telemetría y estados por sede

> Criterio de verificación propuesto: mejora ≥ 30 % en eficiencia operativa percibida/medida y reducción ≥ 20 % de pérdidas económicas asociadas en seis meses. *(completar)*.

### 1.2.2.4. Lean UX Canvas

**1. Business Problem**

La gestión de conservación farmacéutica fue concebida para preservar la calidad de los medicamentos a lo largo del almacenamiento y el transporte. No obstante, la ausencia de monitoreo continuo y la prevalencia de controles manuales debilitan ese propósito: variables críticas permanecen insuficientemente observadas, lo que eleva el riesgo de deterioro, merma y déficits de evidencia ante auditorías.

¿Cómo podría KairoLabs mejorar el sistema de gestión de conservación para que las entidades de salud reduzcan en torno a un 30 % los incidentes de deterioro asociados a condiciones ambientales, aceleren la respuesta ante desviaciones y fortalezcan el soporte al cumplimiento normativo?

---

**2. Business Outcomes**

1. **Contexto de valor.** KairoLabs busca garantizar conservación y trazabilidad, mejorar eficiencia operativa y sostener evidencia para cumplimiento.
2. **Observación del problema actual.** El control insuficiente y la detección tardía incrementan pérdidas, brechas de cumplimiento y fragmentación de información entre sedes.
3. **Resultados de negocio deseados (medibles):**
   - Reducir la pérdida de medicamentos por condiciones inadecuadas en un 30 %.
   - Reducir tiempos de gestión operativa asociados al monitoreo en un 20 % en seis meses.
   - Disminuir el tiempo de respuesta ante incidencias ambientales (meta ilustrativa: de 15 a 10 minutos).
   - Incrementar la proporción de sedes con telemetría activa y auditable (meta ilustrativa: 80 % de almacenes prioritarios conectados).
   - *(completar)*: ajustar metas con línea base empírica post-entrevistas.

---

**3. Users**

1. **Personal operativo de almacenes farmacéuticos**  
   Compra: hospitales, clínicas y centros de distribución.  
   Uso: operarios y técnicos de almacén.  
   Configuración: administradores y soporte técnico.

2. **Gestores sanitarios (farmacéuticos y administradores)**  
   Compra: instituciones que requieren control de conservación.  
   Uso: supervisión de condiciones y revisión de alertas/reportes.  
   Configuración: administradores técnicos del sistema.

3. **Actores con función de supervisión/auditoría**  
   Compra/uso: instancias que requieren evidencia de cumplimiento.  
   Configuración: administradores de red o responsables de gobernanza de datos.  
   *(completar)*: precisar roles tras el análisis de entrevistas.

---

**4. User Benefits**

1. **Operarios de almacén:** visibilidad continua, alertas accionables y menor dependencia de bitácoras manuales; comportamiento esperado: respuesta sistemática ante estados críticos.
2. **Gestores sanitarios:** mayor confianza en la conservación y mejor soporte a decisiones de cumplimiento; comportamiento esperado: consulta recurrente de telemetría y reportes.
3. **Supervisión/auditoría:** acceso a evidencia histórica consolidada; comportamiento esperado: verificación basada en registros digitales.
4. **Pacientes (beneficio indirecto):** mayor probabilidad de recibir medicamentos conservados adecuadamente; impacto social alineado a SO4.

---

**5. Solutions**

1. Plataforma web con dashboards de condiciones ambientales en tiempo real.
2. Integración con sensores IoT para captura de temperatura, humedad y luz.
3. Motor de alertas automáticas ante umbrales fuera de rango.
4. Módulo de históricos y reportes para auditoría.
5. Gestión centralizada multi-sede.
6. *(completar)*: aplicación móvil nativa para respuesta operativa en campo y pipeline experimental de pruebas automatizadas asociado a entrega continua.

---

**6. Hypotheses**

1. El monitoreo en tiempo real reduce el deterioro si habilita detección temprana.
2. Las alertas automáticas reducen latencia de respuesta ante eventos críticos.
3. La consolidación multi-sede mejora control y eficiencia agregada.
4. La digitalización de registros mejora trazabilidad y reduce error humano.
5. Una interfaz de baja fricción favorece la adopción frente a métodos manuales.

---

**7. What’s the most important thing we need to learn first?**

Determinar si el personal operativo y los gestores sanitarios están dispuestos a adoptar una solución de monitoreo continuo, qué fricciones de uso anticipan y qué métricas consideran evidencia creíble de valor.

---

**8. What’s the least amount of work we need to do to learn the next most important thing?**

Ejecutar entrevistas estructuradas con personal de almacén y gestores sanitarios, evaluar prototipos de baja/media fidelidad (wireframes y mockups de dashboard) y publicar una landing page para captar señales de interés. *(completar)*: instrumento de entrevista, muestra objetivo y rúbrica de análisis (Capítulo II).

## 1.3. Segmentos objetivo

**1. Personal operativo de almacenes farmacéuticos**  
Operarios, técnicos y responsables de conservación en hospitales, clínicas y centros de distribución en el Perú.

**Características demográficas (estimación inicial):**
- Edad: 25 – 50 años
- Ubicación: Lima Metropolitana y principales regiones
- Nivel socioeconómico: NSE B y C
- Ocupación: técnicos en farmacia, operarios logísticos, encargados de almacén

**Necesidad prioritaria:**  
Herramientas simples de monitoreo en tiempo real, alertas automáticas y reducción de registros manuales.

**Sustento:**  
Reportes de control público han documentado deficiencias de almacenamiento y debilidades en el control ambiental en establecimientos de salud, lo que respalda la relevancia de este segmento. *(completar)*: actualizar referencias y contrastar con hallazgos de needfinding.

---

**2. Entidades de salud y gestores farmacéuticos**  
Instituciones públicas y privadas responsables de gestionar, supervisar y distribuir medicamentos (hospitales, clínicas, redes de distribución y áreas de gestión farmacéutica).

**Características organizacionales (estimación inicial):**
- Tipo: entidades del sector salud (públicas y privadas)
- Cobertura: local, regional o nacional
- Responsables: químicos farmacéuticos, administradores y gestores logísticos

**Necesidad prioritaria:**  
Visibilidad multi-sede, evidencia de conservación durante almacenamiento/transporte y soporte a cumplimiento normativo.

**Sustento:**  
Iniciativas estatales de mejora de infraestructura logística farmacéutica y hallazgos de control institucional evidencian brechas persistentes en la gestión de condiciones de conservación. *(completar)*: incorporar fuentes actualizadas y validación cualitativa en Capítulo II.
