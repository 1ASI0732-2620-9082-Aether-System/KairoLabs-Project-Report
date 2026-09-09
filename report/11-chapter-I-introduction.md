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

#### 1.2.2.1. Lean UX Problem Statements

En esta sección se analiza el problema desde el enfoque Lean UX, identificando por cada segmento clave el dominio, los puntos de dolor y la oportunidad de solución, con el objetivo de definir una propuesta de valor clara para el desarrollo del producto (Gothelf, 2013). Se plantean dos Problem Statements, correspondientes a los dos segmentos con mayor relación directa con el problema identificado.

---

##### Problem Statement 1 — Personal encargado de almacenes farmacéuticos

**Domain (Dominio del problema)**
Conservación de medicamentos y productos termosensibles en almacenes farmacéuticos de hospitales, clínicas y centros de distribución del sector salud en el Perú.

**Customer Segments (Segmentos de clientes)**
Personal operativo responsable del almacenamiento y manipulación de medicamentos en almacenes farmacéuticos.

**Pain Points (Puntos de dolor)**
- Ausencia de un sistema de monitoreo en tiempo real para condiciones críticas como temperatura, humedad y luz.
- Dependencia de registros manuales, poco frecuentes y propensos a error.
- Detección tardía de desviaciones ambientales, lo que aumenta el riesgo de deterioro de los medicamentos.

**Gap (Brecha identificada)**
No existe una herramienta automatizada que permita al personal de almacenes monitorear en tiempo real las condiciones críticas de almacenamiento, lo que genera vulnerabilidades en el proceso y compromete la efectividad de los medicamentos.

**Vision / Strategy (Visión del producto)**
KairoLabs busca dotar al personal de almacenes de un sistema de monitoreo continuo, basado en sensores IoT, que centralice la visualización de condiciones ambientales y emita alertas automáticas ante desviaciones.

**Initial Segment (Segmento inicial)**
Personal operativo de almacenes farmacéuticos de hospitales y clínicas, por ser los usuarios con interacción directa y frecuente sobre el control de las condiciones de conservación.

**Problem Statement (Pregunta de diseño)**
¿Cómo podemos proporcionar a los encargados de almacenes una solución que permita monitorear las condiciones de almacenamiento de los medicamentos en tiempo real, reducir las incidencias operativas no detectadas y mejorar la trazabilidad de los productos en un 30 % durante los primeros 6 meses?

---

##### Problem Statement 2 — Personal de salud y entidades regulatorias

**Domain (Dominio del problema)**
Cumplimiento normativo de las condiciones de conservación de medicamentos, en el marco de la vigilancia sanitaria ejercida por entidades reguladoras del sector salud en el Perú.

**Customer Segments (Segmentos de clientes)**
Personal de salud responsable del cumplimiento normativo y entidades regulatorias vinculadas a la fiscalización de Buenas Prácticas de Almacenamiento.

**Pain Points (Puntos de dolor)**
- Carencia de un sistema automatizado que asegure y evidencie el cumplimiento de las normativas de conservación de medicamentos.
- Dependencia de procesos manuales ineficaces para verificar el cumplimiento sanitario.
- Dificultad para reconstruir evidencia histórica auditable ante fiscalizaciones.

**Gap (Brecha identificada)**
No existen herramientas automatizadas que permitan a las entidades de salud monitorear y garantizar, con evidencia auditable, el cumplimiento de las normativas de conservación de medicamentos, lo que pone en riesgo la calidad de los productos y la seguridad de los pacientes.

**Vision / Strategy (Visión del producto)**
KairoLabs busca ofrecer a las entidades de salud un registro histórico auditable y trazable de las condiciones de conservación, que facilite la verificación del cumplimiento normativo y la generación de reportes ante fiscalizaciones.

**Initial Segment (Segmento inicial)**
Personal de salud y responsables de cumplimiento normativo en hospitales y clínicas que forman parte del alcance inicial del producto.

**Problem Statement (Pregunta de diseño)**
¿Cómo podemos diseñar un sistema que permita a las entidades de salud cumplir con las normativas sanitarias de manera más eficiente, garantizando que el 100 % de los medicamentos se almacenen en condiciones adecuadas dentro de los primeros 12 meses de uso?

#### 1.2.2.2. Lean UX Assumptions

En el enfoque Lean UX, las assumptions (suposiciones) representan hipótesis iniciales sobre los usuarios, el problema, la solución, el valor percibido y el negocio, que orientan el desarrollo del producto antes de contar con evidencia validada. Estas suposiciones deben ser contrastadas posteriormente mediante pruebas con usuarios, prototipos y experimentación continua (Gothelf, 2013).

A continuación, se presentan las principales suposiciones identificadas para el desarrollo de la solución KairoLabs:

**1. Suposiciones sobre los usuarios**
- El personal encargado de almacenes farmacéuticos (operarios, técnicos y responsables de control de medicamentos en hospitales y centros de distribución) constituye el usuario principal del producto.
- Los usuarios utilizarán la plataforma durante toda la jornada operativa, tanto en dispositivos móviles como en computadoras, accediendo a un dashboard centralizado.
- Los usuarios requieren una interfaz simple y clara, con codificación por colores (verde, amarillo, rojo), que no exija capacitación técnica extensa.
- Los usuarios valoran contar con alertas automáticas que les permitan responder rápidamente ante condiciones fuera de rango.

**2. Suposiciones sobre el problema**
- La falta de visibilidad en tiempo real sobre las condiciones de almacenamiento de medicamentos incrementa el riesgo de deterioro de los productos.
- La detección tardía de anomalías ambientales impide una respuesta oportuna por parte del personal de almacenes.
- La ausencia de alertas automáticas ante condiciones no ideales limita la capacidad de prevención de pérdidas económicas.
- Las entidades de salud carecen de una solución automatizada que les permita cumplir de forma eficiente con las normativas sanitarias relacionadas con el almacenamiento de medicamentos.

**3. Suposiciones sobre la solución**
- Un dashboard en tiempo real, alimentado por sensores IoT, permitirá al personal visualizar de forma inmediata el estado de conservación de los medicamentos.
- Los sensores IoT podrán integrarse fácilmente a una plataforma centralizada, accesible desde cualquier dispositivo conectado, con datos históricos y en tiempo real.
- La plataforma será compatible con los sistemas actuales de gestión de inventarios, permitiendo su integración sin interrumpir las operaciones diarias.
- Los sensores IoT funcionarán de manera eficiente en condiciones ambientales extremas (temperaturas elevadas o alta humedad), comunes en algunos hospitales y almacenes.
- La mayoría de los almacenes clave del sector salud cuentan con conexión a internet suficiente para sincronizar datos operativos en tiempo real.

**4. Suposiciones sobre el valor del producto**
- El valor principal que los clientes buscan obtener es la seguridad de los medicamentos, evitando pérdidas económicas por deterioro o vencimiento.
- La ventaja competitiva de la solución radica en combinar monitoreo IoT en tiempo real con la gestión de condiciones ambientales, específicamente para el sector farmacéutico y de salud.
- Si no se evidencia una reducción de pérdidas operativas dentro de los primeros 3 meses de uso, los clientes perderán confianza en la solución y no renovarán la suscripción.

**5. Suposiciones sobre el negocio**
- El modelo de negocio se basará en un sistema de suscripción mensual escalable según la cantidad de almacenes y sensores IoT conectados, con soporte adicional para instalación y mantenimiento.
- La adopción de la tecnología será rápida en el sector, debido a la creciente demanda de soluciones que mejoren la seguridad del paciente y el cumplimiento normativo.
- Las entidades de salud están cada vez más dispuestas a invertir en tecnologías que optimicen costos y mejoren la eficiencia operativa a largo plazo.
- La competencia en el mercado de monitoreo IoT para el sector farmacéutico aún se encuentra en etapas tempranas, lo que representa una oportunidad de posicionamiento como líderes en el nicho.
- Entidades reguladoras como el MINSA promueven iniciativas digitales para la gestión de medicamentos, lo que facilita la adopción de soluciones tecnológicas como KairoLabs.
- La plataforma debe ser escalable para adaptarse al crecimiento de hospitales o redes de distribución, permitiendo agregar más sensores y almacenes sin dificultad.

**Conclusión de las assumptions**

Estas suposiciones guían el desarrollo inicial de KairoLabs y permiten identificar los principales riesgos del proyecto, tanto a nivel de usuario, tecnología, mercado y modelo de negocio. No obstante, deberán ser validadas mediante entrevistas, prototipos y experimentación continua con los segmentos identificados, siguiendo los principios del enfoque Lean UX (Gothelf, 2013).

#### 1.2.2.3. Lean UX Hypothesis Statements

A continuación, se presentan las hipótesis del proyecto KairoLabs, formuladas bajo el enfoque Lean UX, con el objetivo de validar las decisiones de diseño mediante métricas medibles (Gothelf, 2013).

**Hipótesis 1: Monitoreo en tiempo real y alertas para toma de decisiones**
Creemos que:
 Implementar una plataforma web con monitoreo en tiempo real de las condiciones de almacenamiento (temperatura, humedad y exposición a la luz) y alertas automáticas
Para:
 El personal encargado de almacenes farmacéuticos en hospitales y centros de distribución
Lograremos:
 Que el personal tome decisiones oportunas para evitar el deterioro de los productos farmacéuticos
Sabremos que hemos tenido éxito cuando veamos:
- Una mejora del 30 % en la reducción de incidentes relacionados con el deterioro de medicamentos durante los primeros 3 meses de uso de la plataforma.

**Hipótesis 2: Alertas automáticas para reducción de riesgos**
Creemos que:
 Generar alertas automáticas mediante sensores ante variaciones de temperatura, humedad o luz
Para:
 Las entidades de salud responsables de la conservación de medicamentos
Lograremos:
 Que tomen decisiones rápidas ante variaciones críticas en las condiciones de almacenamiento, reduciendo los riesgos asociados a un almacenamiento inadecuado
Sabremos que hemos tenido éxito cuando veamos:
- Una mejora del 25 % en la reducción de incidentes de deterioro de medicamentos durante los primeros 3 meses de uso del sistema de alertas.

**Hipótesis 3: Datos históricos y reportes para trazabilidad**
Creemos que:
 Habilitar la visualización de datos históricos y la generación de reportes automáticos sobre las condiciones de almacenamiento
Para:
 Los usuarios responsables de la trazabilidad y el cumplimiento normativo
Lograremos:
 Mejorar la trazabilidad y facilitar el cumplimiento de las normativas sanitarias de manera más eficiente
Sabremos que hemos tenido éxito cuando veamos:
- Una mejora del 20 % en la eficiencia de auditorías y cumplimiento normativo durante los primeros 3 meses de uso del sistema de reportes.

**Hipótesis 4: Sensores IoT para reducir la dependencia manual**
Creemos que:
 Integrar sensores IoT a la plataforma digital, con registro automático de las condiciones ambientales
Para:
 El personal operativo de almacenes farmacéuticos
Lograremos:
 Reducir la carga operativa y mejorar la precisión del monitoreo, disminuyendo la dependencia de procesos manuales y los errores humanos
Sabremos que hemos tenido éxito cuando veamos:
- Una mejora del 25 % en la precisión del monitoreo.
- Una reducción del 30 % en los errores operativos durante los primeros 3 meses de uso del sistema.

**Hipótesis 5: Plataforma centralizada multisede**
Creemos que:
 Ofrecer una plataforma centralizada para la gestión de múltiples almacenes o sedes, con acceso a datos en tiempo real
Para:
 Las entidades de salud con redes de distribución o múltiples establecimientos
Lograremos:
 Optimizar la gestión de recursos, reducir pérdidas económicas y mejorar la eficiencia operativa
Sabremos que hemos tenido éxito cuando veamos:
- Una mejora del 30 % en la eficiencia operativa.
- Una reducción del 20 % en pérdidas económicas durante los primeros 6 meses de uso del sistema centralizado.

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
