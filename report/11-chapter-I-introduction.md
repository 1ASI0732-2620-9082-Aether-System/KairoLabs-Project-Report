# Capítulo I: Introducción

## 1.1. Startup Profile

### 1.1.1. Descripción de la Startup

Aether System nace como una propuesta tecnológica enfocada en mejorar la conservación de medicamentos y otros productos termosensibles dentro de organizaciones del sector salud. Su objetivo principal es brindar a clínicas, farmacias, hospitales y operadores logísticos una herramienta digital que les permita anticiparse a desviaciones en las condiciones de almacenamiento y transporte, antes de que estas comprometan la calidad e inocuidad del producto.

La solución, denominada KairoLabs, consiste en una plataforma compuesta por una aplicación web responsive y una aplicación móvil nativa que integran diversas funcionalidades orientadas a la trazabilidad sanitaria, tales como el monitoreo continuo de variables ambientales críticas (temperatura, humedad y exposición a la luz), la generación de alertas automáticas ante desviaciones respecto a los rangos permitidos y un histórico auditable de las condiciones de conservación por lote.

El valor diferencial de la propuesta radica en centralizar, dentro de una sola plataforma, tanto mecanismos de supervisión preventiva como de reacción ante incidentes de conservación. Esto es especialmente relevante en un contexto regulatorio donde el almacenamiento de productos termolábiles debe mantenerse dentro de rangos estrictos —usualmente entre 2 °C y 8 °C para cadena de frío— conforme a la normativa nacional de Buenas Prácticas de Almacenamiento (DIGEMID, 2015). Al automatizar este control, KairoLabs reduce la dependencia de registros manuales de temperatura, uno de los puntos críticos identificados en los procesos de fiscalización sanitaria.

Asimismo, la plataforma busca fortalecer la coordinación entre los distintos actores de la cadena de suministro farmacéutica, almacenes, transportistas y puntos de dispensación, promoviendo una gestión logística más trazable, oportuna y alineada con los estándares sanitarios vigentes en el país.

### 1.1.2. Perfiles de integrantes del equipo

<table border="1" cellspacing="0" cellpadding="2">
<thead>
<tr>
<th>Foto</th>
<th>Apellido y nombre</th>
<th>Carrera</th>
<th>Acerca de</th>
</tr>
</thead>

<tbody>

<tr>
<td><img src="../assets/images/team/dhilsen.png" alt="Foto"></td>
<td>Mallqui Vilca, Dhilsen Armil</td>
<td>Ingeniería de Software</td>
<td>Código: U202319440. Estudiante de Ingeniería de Software con énfasis en el desarrollo de soluciones escalables, la aplicación de buenas prácticas de ingeniería y la configuración de entornos de despliegue continuo. Aporte al equipo: Orienta su aporte al cumplimiento de hitos técnicos del equipo, a la documentación rigurosa del proceso experimental y a la integración entre evidencia de campo, diseño de producto y pipelines de verificación.</td>
</tr>

<tr>
<td><img src="../assets/images/team/sebastian.jpg" alt="Foto"></td>
<td>Diaz Mendoza, Sebastian Victor Andre</td>
<td>Ingeniería de Software</td>
<td>Código: U202415638. Soy Sebastian Diaz, actualmente estudio la carrera de Ingeniería de Software y para el presente proyecto me he enfocado en diseño de experiencia de usuario (UX/UI), además soy responsable de la interacción y usabilidad. Cuento con dominio en estructura de datos, algoritmos y base de datos. Con una capacidad de razonamiento lógico y ordenado, con conocimiento en paradigmas como la programación orientada a objetos y técnicas de aplicación en la complejidad algorítmica.</td>
</tr>

<tr>
<td><img src="../assets/images/team/PLACEHOLDER.png" alt="Foto"></td>
<td>[Apellidos, Nombres]</td>
<td>[Carrera]</td>
<td>Código: [Código de estudiante]. [Descripción de formación técnica y habilidades]. Aporte al equipo: .</td>
</tr>

<tr>
<td><img src="../assets/images/team/PLACEHOLDER.png" alt="Foto"></td>
<td>[Apellidos, Nombres]</td>
<td>[Carrera]</td>
<td>Código: [Código de estudiante]. [Descripción de formación técnica y habilidades]. Aporte al equipo:.</td>
</tr>

<tr>
<td><img src="../assets/images/team/PLACEHOLDER.png" alt="Foto"></td>
<td>[Apellidos, Nombres]</td>
<td>[Carrera]</td>
<td>Código: [Código de estudiante]. [Descripción de formación técnica y habilidades]. Aporte al equipo:.</td>
</tr>

</tbody>
</table>

**Nota:** Información de los integrantes del equipo de desarrollo de Aether System (proyecto KairoLabs).

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

#### 1.2.2.4. Lean UX Canvas

El Lean UX Canvas presentado a continuación sintetiza los principales elementos del modelo de negocio y la propuesta de valor de la solución KairoLabs. En este se integran el problema identificado, los resultados de negocio esperados, los segmentos de usuarios, los beneficios percibidos, las soluciones propuestas, las hipótesis formuladas y las prioridades de aprendizaje, permitiendo visualizar de manera estructurada la relación entre las necesidades del negocio, del usuario y las funcionalidades del producto. Este canvas sirve como base para la validación continua del proyecto mediante la experimentación y el enfoque iterativo propio de Lean UX.

**1. Business Problem**

La gestión del almacenamiento de medicamentos en el sistema de salud fue diseñada para conservar los productos farmacéuticos en condiciones seguras y garantizar su calidad durante el almacenamiento y transporte. Sin embargo, hemos observado que la falta de monitoreo en tiempo real y el uso de procesos manuales están afectando la eficacia de este sistema. Variables críticas como temperatura, humedad y exposición a la luz no están siendo controladas adecuadamente, lo que genera riesgos en la calidad de los medicamentos, tanto en los almacenes como durante su transporte.

¿Cómo podríamos mejorar el sistema de gestión de almacenamiento de medicamentos para que las entidades de salud sean más exitosas, evidenciado por una reducción del 30 % en incidentes relacionados con el deterioro de los medicamentos, una mejora en la respuesta a desviaciones de condiciones ambientales y un aumento en el cumplimiento de las normativas de conservación?

**2. Business Outcomes**

Nuestro producto fue diseñado para lograr la conservación y trazabilidad de los medicamentos en condiciones óptimas dentro de los almacenes farmacéuticos, mejorando la eficiencia operativa y asegurando el cumplimiento de las normativas sanitarias.

Hemos observado que el almacenamiento inadecuado y la falta de monitoreo en tiempo real están llevando a un aumento en las pérdidas económicas por medicamentos deteriorados, incumplimiento de las normativas de conservación y baja eficiencia en la gestión de los almacenes, lo que también afecta la trazabilidad y el control en múltiples sedes.

¿Cómo podríamos mejorar el producto para que nuestros clientes sean más exitosos, según estos cambios medibles en su comportamiento?

- Resultado de negocio 1: Reducir la pérdida de medicamentos por condiciones inadecuadas de almacenamiento en un 30 %.
- Resultado de negocio 2: Mejorar la eficiencia en la gestión de almacenes farmacéuticos, alcanzando una reducción del 20 % en los tiempos de gestión operativa dentro de los primeros 6 meses.
- Resultado de negocio 3: Disminuir el tiempo de respuesta ante incidencias relacionadas con condiciones ambientales de 15 a 10 minutos, mejorando la capacidad de reacción ante problemas críticos.
- Resultado de negocio 4: Asegurar el cumplimiento del 100 % de las normativas sanitarias relacionadas con el almacenamiento de medicamentos dentro de los primeros 6 meses de uso.
- Resultado de negocio 5: Optimizar la trazabilidad y control de los productos farmacéuticos en múltiples sedes, garantizando que el 80 % de los almacenes estén conectados y monitorizados en tiempo real.

**3. Users**

*Personal encargado de almacenes farmacéuticos*
- ¿Quién compra el producto? Hospitales, clínicas y centros de distribución que necesitan optimizar el almacenamiento y monitoreo de medicamentos.
- ¿Quién usa el producto? El personal operativo de los almacenes farmacéuticos: operarios, técnicos y encargados de la gestión de los productos.
- ¿Quién configura el producto? Los administradores de las entidades de salud y el personal de soporte técnico en los almacenes.

*Personal de salud (farmacéuticos, administradores hospitalarios)*
- ¿Quién compra el producto? Hospitales, farmacias y clínicas que necesitan asegurar la conservación de medicamentos en condiciones óptimas.
- ¿Quién usa el producto? Farmacéuticos y administradores hospitalarios que supervisan la distribución de medicamentos.
- ¿Quién configura el producto? Técnicos y administradores encargados de configurar el sistema de supervisión y gestión del almacenamiento.

*Entidades regulatorias (MINSA y redes de salud)*
- ¿Quién compra el producto? Instituciones gubernamentales o entidades regulatorias encargadas de supervisar las normativas sanitarias de almacenamiento y distribución de medicamentos.
- ¿Quién usa el producto? Entidades gubernamentales que monitorean el cumplimiento de las normativas en centros de salud y almacenes farmacéuticos.
- ¿Quién configura el producto? Administradores de las redes de salud que supervisan y regulan el cumplimiento normativo a nivel nacional.

**4. User Benefits**

*Personal encargado de almacenes farmacéuticos*
- ¿Por qué buscan nuestro producto? Necesitan una solución eficiente para monitorear las condiciones de almacenamiento y evitar la pérdida de productos.
- ¿Qué beneficio obtienen? Reducción de la pérdida de medicamentos y mejora de la eficiencia operativa en la gestión de almacenes.
- Cambio de comportamiento observable: El personal adoptará prácticas más diligentes y sistemáticas en el monitoreo ambiental, registrando y respondiendo oportunamente ante desviaciones.

*Personal de salud (farmacéuticos, administradores hospitalarios)*
- ¿Por qué buscan nuestro producto? Buscan una herramienta confiable para asegurar el correcto almacenamiento de medicamentos, respetando las normativas sanitarias.
- ¿Qué beneficio obtienen? Aseguran condiciones óptimas de conservación, cumpliendo con las normativas y mejorando la seguridad de los pacientes.
- Cambio de comportamiento observable: El personal usará el sistema para verificar condiciones ambientales en tiempo real, asegurando que los productos no se deterioren.

*Entidades regulatorias (MINSA y redes de salud)*
- ¿Por qué buscan nuestro producto? Necesitan garantizar que las normativas sanitarias se sigan de manera efectiva en centros de salud y almacenes farmacéuticos.
- ¿Qué beneficio obtienen? Mejora del cumplimiento normativo a nivel nacional, con capacidad de auditar y verificar fácilmente las condiciones de almacenamiento.
- Cambio de comportamiento observable: Las entidades podrán verificar y reportar el cumplimiento normativo en tiempo real, evitando sanciones y mejorando la supervisión.

*Pacientes*
- ¿Por qué buscan nuestro producto? Aunque no usan el producto directamente, se benefician indirectamente al recibir medicamentos almacenados y distribuidos bajo condiciones controladas.
- ¿Qué beneficio obtienen? Garantía de que los medicamentos consumidos sean efectivos y seguros.
- Cambio de comportamiento observable: Mayor confianza en la seguridad de los medicamentos que consumen.

**5. Solutions**

- Plataforma web con dashboards para visualizar en tiempo real las condiciones ambientales (temperatura, humedad y exposición a la luz) de forma sencilla y continua.
- Integración con sensores IoT para capturar y registrar en tiempo real las condiciones ambientales críticas de los almacenes farmacéuticos.
- Sistema de alertas automáticas que notifique a los usuarios cuando las condiciones se desvíen de los parámetros establecidos.
- Módulo de reportes y almacenamiento de datos históricos que facilite auditorías y el cumplimiento normativo.
- Gestión centralizada para múltiples almacenes o sedes, con visibilidad completa y en tiempo real sobre toda la organización.

**6. Hypotheses**

- Creemos que la reducción del deterioro de medicamentos se logrará si el personal de almacenes detecta problemas antes de que afecten los medicamentos, mediante un sistema de monitoreo en tiempo real.
- Creemos que la reducción del riesgo de deterioro se logrará si el personal recibe alertas automáticas ante condiciones críticas, reduciendo la falta de respuesta oportuna.
- Creemos que la mejora del control y la eficiencia operativa se logrará si las entidades de salud centralizan la información de múltiples almacenes en una plataforma de monitoreo.
- Creemos que la reducción de errores humanos y la mejora de la trazabilidad se lograrán si se digitalizan los registros de almacenamiento y se optimiza el seguimiento histórico.
- Creemos que la adopción de la tecnología se logrará si el personal encuentra fácil de usar el sistema y reemplaza los métodos manuales mediante una interfaz intuitiva y accesible.

**7. What's the most important thing we need to learn first?**

Primero necesitamos entender si el personal encargado de almacenes y las entidades de salud están dispuestos a adoptar una solución tecnológica para el monitoreo en tiempo real, así como identificar sus necesidades específicas y limitaciones en el uso de estas herramientas.

**8. What's the least amount of work we need to do to learn the next most important thing?**

Realizar entrevistas con personal de almacenes y profesionales de salud, además de pruebas de prototipos simples (mockups o dashboards básicos), para validar la utilidad del monitoreo en tiempo real y la aceptación del sistema. También se debe crear una landing page para obtener retroalimentación sobre el interés en la solución propuesta.

**Figura 1:**

*Lean UX Canvas*

<p align="center">
  <img src="" alt="Lean UX Canvas" width="700"><br>
  Nota: Lean UX Canvas del proyecto KairoLabs, donde se resumen el problema, los resultados de negocio, los segmentos de usuarios, las soluciones propuestas, las hipótesis y las prioridades de aprendizaje.
</p>

A continuación, se presenta el Lean UX Canvas del proyecto (ver enlace): ...

### 1.3. Segmentos objetivo

Los segmentos presentados en esta sección se derivan del análisis realizado en el Lean UX Process, donde se identificaron los principales grupos afectados por la problemática de conservación de medicamentos. A continuación, se detallan sus características demográficas, geográficas y organizacionales, así como información estadística relevante que sustenta la necesidad de la solución propuesta.

- **Segmento 1: Personal operativo de almacenes farmacéuticos**

  - **Descripción:**
  Operarios, técnicos y responsables del almacenamiento de medicamentos en hospitales, clínicas y centros de distribución en el Perú, encargados directos de supervisar las condiciones en las que se conservan los productos farmacéuticos.
  - **Características demográficas:**
    - Edad: 25 – 50 años
    - Sexo: Masculino y femenino
    - Nivel socioeconómico: B y C
    - Ocupación: Técnicos en farmacia, operarios logísticos, encargados de almacén
  - **Características geográficas:**
    - Ubicación: Lima Metropolitana y principales regiones del país
    - Regiones: Concentración en centros logísticos estratégicos (ej. Lurín) y ciudades con mayor densidad de establecimientos de salud
  - **Características psicográficas:**
    - Uso constante de dispositivos móviles y computadoras en el entorno laboral
    - Preocupación por evitar pérdidas económicas y sanciones por incumplimiento normativo
    - Interés en herramientas simples que no requieran capacitación técnica extensa
    - Valoración de la tecnología como apoyo para reducir la carga operativa manual
  - **Sustento estadístico:**
  Según el diagnóstico del sector salud del Ministerio de Salud, el 97.7 % de los establecimientos de salud del primer nivel de atención presenta capacidad instalada inadecuada, cifra que llega a 97.6 % en hospitales (MINSA, 2023). A esto se suma que la Contraloría General de la República ha detectado de forma recurrente ambientes de cadena de frío sin condiciones restringidas ni adecuadas en distintas regiones del país (Contraloría General de la República, 2026b), evidenciando la necesidad de herramientas que compensen estas brechas de infraestructura mediante monitoreo automatizado.

- **Segmento 2: Entidades de salud y gestores farmacéuticos (MINSA, hospitales y clínicas)**

  - **Descripción:**
  Instituciones públicas y privadas responsables de la gestión, supervisión y distribución de medicamentos a nivel nacional, incluyendo el MINSA, hospitales, clínicas y centros de distribución.
  - **Características organizacionales:**
    - Tipo de entidad: Instituciones del sector salud, públicas y privadas
    - Cobertura: Local, regional y nacional
    - Ubicación: Principalmente zonas urbanas y centros logísticos
    - Responsables: Químicos farmacéuticos, administradores, gestores logísticos
  - **Sustento estadístico:**
  El Perú cuenta con 24 839 IPRESS registradas, de las cuales el 62 % son privadas, e incluye 247 hospitales de segundo y tercer nivel de atención (MINSA, 2023). Asimismo, según el Repositorio Único Nacional de Información en Salud, a agosto de 2024 el 13.4 % de los establecimientos de salud públicos del país no alcanzaba el umbral mínimo de disponibilidad de medicamentos esenciales establecido por el MINSA (ComexPerú, 2024), lo que evidencia brechas en la gestión y trazabilidad que una plataforma de monitoreo centralizado podría contribuir a cerrar.

A continuación, se presenta un dato estadístico que evidencia la magnitud de la problemática de infraestructura en el sector salud peruano, la cual impacta directamente en los segmentos identificados.

<p align="center">
  <img src="../assets/images/statistics/figura1_infraestructura.png" alt="Figura 1" width="450">
</p>

**Nota:** Porcentaje de establecimientos de salud con capacidad instalada inadecuada, por tipo de establecimiento (Perú, 2023).
Fuente: Elaboración propia a partir de datos del Ministerio de Salud (MINSA, 2023).

Como se observa en el gráfico, más del 95 % de los establecimientos de salud en cada categoría presenta condiciones de infraestructura inadecuadas, lo que evidencia una brecha estructural que compromete la conservación óptima de los medicamentos. Esta situación refuerza la necesidad de una solución tecnológica que permita compensar dichas limitaciones mediante monitoreo automatizado y trazabilidad en tiempo real.
