# Capítulo I: Introducción

## 1.1. Startup Profile

### 1.1.1. Descripción de la Startup

**Aether System** es un equipo académico de la Universidad Peruana de Ciencias Aplicadas, constituido en el marco del curso *Diseño de Experimentos de Ingeniería de Software* (1ASI0732), cuyo propósito es concebir, validar experimentalmente y evolucionar soluciones de software con criterios de verificación, validación y entrega continua.

La misión de la startup es diseñar plataformas digitales que permitan a organizaciones del sector salud garantizar la conservación adecuada de medicamentos mediante el monitoreo continuo de variables ambientales críticas —temperatura, humedad y exposición a la luz—, fortaleciendo la trazabilidad, la toma de decisiones oportuna y el cumplimiento de estándares sanitarios.

La visión institucional consiste en contribuir a la modernización de la gestión logística farmacéutica en el Perú, impulsando la adopción de tecnologías IoT, arquitectura de software orientada a dominios y pipelines de DevOps que habiliten observación, experimentación y mejora incremental del producto.

El producto principal es **KairoLabs**, una plataforma digital (aplicación web responsive y aplicación móvil nativa) orientada a clínicas, farmacias, hospitales y operadores de distribución. KairoLabs centraliza la supervisión en tiempo real de las condiciones de almacenamiento y transporte, genera alertas ante desviaciones, conserva históricos auditables y reduce la dependencia de controles manuales. En el contexto del presente curso, el producto se trata además como objeto de experimentación: se formularán hipótesis, se definirán métricas de calidad y se implementarán mecanismos de verificación y validación asociados a un entorno de entrega continua.

### 1.1.2. Perfiles de integrantes del equipo

| Código     | Descripción | Foto |
|:-----------|:---|:---|
| u202319440 | **Mallqui Vilca, Dhilsen Armil**<br>Ingeniería de Software<br><br>Estudiante de Ingeniería de Software con énfasis en el desarrollo de soluciones escalables, la aplicación de buenas prácticas de ingeniería y la configuración de entornos de despliegue continuo. Orienta su aporte al cumplimiento de hitos técnicos del equipo, a la documentación rigurosa del proceso experimental y a la integración entre evidencia de campo, diseño de producto y pipelines de verificación. | ![Foto](../assets/dhilsen-malqui.png) |

> *(completar)*: los demás integrantes del equipo Aether System incorporarán sus perfiles de manera individual en versiones posteriores del informe.

## 1.2. Solution Profile

### 1.2.1. Antecedentes y problemática

### Contexto del mercado y oportunidad

En el Perú, el sector salud presenta brechas recurrentes en la gestión del almacenamiento de medicamentos. Evidencias documentadas en establecimientos de salud —incluyendo casos reportados en los que productos farmacéuticos se conservaron en condiciones inadecuadas, con exposición solar y sin control efectivo de temperatura y humedad— ilustran un problema sistémico que compromete la eficacia terapéutica y la seguridad del paciente.

Paralelamente, existe una oportunidad de mercado para soluciones tecnológicas que trasciendan la mera gestión de inventarios o facturación. El problema central no es únicamente administrativo: es la **ausencia de visibilidad en tiempo real** sobre condiciones ambientales críticas a lo largo de la cadena de conservación. Iniciativas de digitalización impulsadas por el sector público y la creciente disponibilidad de sensores IoT configuran un escenario favorable para plataformas como KairoLabs, capaces de combinar telemetría, alertas y evidencia histórica auditables.

Desde la perspectiva del curso, dicha oportunidad no se asume como válida *a priori*; se formula como conjunto de supuestos e hipótesis que deberán someterse a verificación experimental (pruebas de software, observación de uso y métricas de calidad) en un entorno de entrega continua.

---

#### Who (¿Quiénes son los involucrados?)

Los actores principales comprenden hospitales, clínicas, farmacias, almacenes farmacéuticos, distribuidores, personal operativo de conservación y entidades regulatorias vinculadas a la vigilancia sanitaria. Los pacientes constituyen stakeholders indirectos, en tanto dependen de que los medicamentos preserven su integridad fisicoquímica hasta el punto de dispensación.

#### What (¿Qué se necesita?)

Se requiere un sistema de software que permita monitorear de forma continua las condiciones de almacenamiento y transporte de medicamentos —en particular temperatura, humedad y exposición lumínica—, emitir alertas ante desviaciones y conservar registros históricos para auditoría, aprendizaje organizacional y cumplimiento normativo.

#### Where (¿Dónde ocurre el problema?)

El problema se manifiesta en establecimientos de salud, almacenes farmacéuticos y nodos de distribución a nivel nacional, con especial criticidad en provincias e instalaciones con infraestructura limitada. También se expresa durante el transporte, donde la exposición a condiciones no controladas suele carecer de telemetría confiable.

#### When (¿Cuándo surge esta necesidad?)

La necesidad es permanente a lo largo del ciclo logístico: desde el ingreso a almacén hasta la entrega final. Cada intervalo sin monitoreo introduce incertidumbre y riesgo de deterioro no detectado oportunamente.

#### Why (¿Por qué existe esta necesidad?)

Persisten limitaciones de infraestructura, escasa automatización del control ambiental y dependencia de registros manuales. Dichas condiciones elevan la probabilidad de incidencias, pérdidas económicas y exposición del paciente a productos con calidad comprometida.

#### How (¿Cómo se manifiesta el problema?)

Se observa conservación en ambientes no acondicionados, ausencia de umbrales alertables, demoras en la detección de anomalías y dificultad para reconstruir trazas históricas ante auditorías o eventos adversos.

#### How Much (¿Cuánto cuesta o qué magnitud tiene el problema?)

El impacto combina merma económica por productos inutilizables, costos de remediación operativa y, de mayor gravedad ética, riesgos sobre la efectividad terapéutica. La magnitud es nacional y afecta tanto al sector público como al privado, lo que justifica una intervención de ingeniería con evaluación explícita de impactos sociales y profesionales (ABET SO4).

---

### Descripción de la Solución Propuesta

**KairoLabs** propone un ecosistema de monitoreo continuo basado en sensores IoT integrados a una plataforma digital multiplataforma. Los sensores capturan variables ambientales críticas; la plataforma presenta dashboards en tiempo real, gestiona alertas, almacena históricos y soporta la supervisión multi-sede.

La solución busca reducir la latencia de respuesta ante desviaciones, mejorar la trazabilidad y disminuir la dependencia de controles manuales. En el marco experimental del curso, cada capacidad clave se asociará a hipótesis verificables, métricas de calidad (por ejemplo, tasa de detección oportuna, precisión de alertas, cobertura de trazabilidad) y evidencias de verificación/validación dentro de un pipeline de entrega continua. *(completar)*: definir formalmente el conjunto inicial de métricas experimentales y el protocolo de medición tras el Needfinding.

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
