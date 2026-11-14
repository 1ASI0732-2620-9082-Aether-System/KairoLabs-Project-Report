# Student Outcome

El curso **1ASI0732 – Diseño de Experimentos de Ingeniería de Software** contribuye al cumplimiento del siguiente resultado de aprendizaje ABET:

**ABET – EAC – Student Outcome 4**

Criterio: la capacidad de reconocer responsabilidades éticas y profesionales en situaciones de ingeniería, y formular juicios informados que consideren el impacto de las soluciones de ingeniería en contextos globales, económicos, ambientales y sociales.

En el marco del presente informe, el Student Outcome 4 se interpreta como la obligación del equipo **Aether System** de diseñar, validar y documentar el producto **KairoLabs** considerando no únicamente la viabilidad técnica, sino también las implicancias éticas, regulatorias y sociales asociadas al monitoreo de condiciones críticas en la cadena de conservación de productos farmacéuticos.

#### 4.1. ABET Student Outcome 4: Ethical and professional responsibility

| Criterio específico | Acciones realizadas | Conclusiones |
| :--- | :--- | :--- |
| **Reconoce responsabilidades éticas y profesionales en el diseño y validación de soluciones de ingeniería.** | **Mallqui Vilca, Dhilsen Armil**<br>**AV1:** Definió el Startup Profile y el Solution Profile de KairoLabs explicitando riesgos sanitarios, trazabilidad y cumplimiento normativo como dimensiones éticas del problema. Incorporó hipótesis Lean UX con criterios de verificación medibles, alineadas a un enfoque experimental de verificación y validación de software. | **Mallqui Vilca, Dhilsen Armil**<br>**AV1:** La formulación temprana de supuestos, hipótesis y resultados de negocio medibles facilita juicios profesionales informados sobre el impacto de KairoLabs en la seguridad del paciente, la eficiencia operativa y el cumplimiento sanitario. |
| **Formula juicios informados considerando impactos globales, económicos, ambientales y sociales.** | **Mallqui Vilca, Dhilsen Armil**<br>**AV1:** Analizó antecedentes del sector salud peruano (deficiencias de almacenamiento, exposición a condiciones ambientales adversas y dependencia de procesos manuales) y vinculó la propuesta de valor de KairoLabs con la reducción de pérdidas económicas, la mitigación de riesgos sociales sobre la población usuaria de medicamentos y la mejora de la gobernanza de datos operativos. Las evidencias de validación posteriores se documentan en el capítulo VI; no se atribuyen a AV1 métricas experimentales de impacto no medidas. | **Mallqui Vilca, Dhilsen Armil**<br>**AV1:** El análisis contextual sostiene que una plataforma de monitoreo continuo no es solo una mejora tecnológica, sino una intervención de ingeniería con efectos económicos (menor merma), sociales (mayor seguridad terapéutica) y profesionales (auditoría y accountability). Estas conclusiones iniciales se contrastan con el Needfinding y la validación de avances posteriores, sin afirmar resultados experimentales de impacto en esta etapa. |

---

## AV2 — Student Outcome 4: aportes personales

**Versión 3.0 — 13 de noviembre de 2026.** Curso: Diseño de Experimentos de Ingeniería de Software; sección 9082; docente Juan Fernando Ysen Paiba.

Esta actualización presenta reflexiones personales vinculadas a los criterios **4.c.1** (responsabilidades éticas y profesionales) y **4.c.2** (juicios informados sobre impactos globales, económicos, ambientales y sociales). Las conclusiones distinguen evidencia técnica, inspección y opinión de usuarios; no atribuyen mejoras clínicas o comerciales no medidas.

Los aportes del capítulo VII se registran conforme a la distribución del equipo. El [capítulo VII](71-chapter-VII-devops-practices.md) está integrado al informe y enlazado desde el índice; sus notas distinguen implementación comprobada de planificación y evidencias todavía pendientes. Los apartados no asignados inicialmente se distribuyeron como responsabilidad documental complementaria: 6.1 y 6.3.3 a Sebastián; 6.4 y sus subapartados a Rodrigo.

### Distribución individual de aportes AV2

| Integrante | Capítulo VI | Capítulo VII / estado |
| :--- | :--- | :--- |
| Mallqui Vilca, Dhilsen Armil | 6.1.3 y 6.1.4 | Participación de apoyo a la coherencia entre pruebas de aceptación y pipeline; no se asigna otra sección de VII como finalizada. |
| Diaz Mendoza, Sebastian Victor Andre | 6.1, 6.1.1, 6.1.2 y 6.3.3 | 7.1, 7.1.1 y 7.1.2: CI documentado y ejecutado en GitHub Actions, integrado al informe. |
| Ramirez Escalante, Carlo Patricio | 6.2.1, 6.2.1.1 y 6.2.1.2 | 7.4 a 7.4.4: documentación de monitoreo, alertas y notificaciones integrada al informe. |
| Oblitas Alcalde, Rodrigo | 6.4, 6.4.1 a 6.4.1.3 y 6.4.2 a 6.4.2.4 | 7.2, 7.2.1 y 7.2.2: documentación de entrega continua integrada; el staging y la aprobación de entrega siguen pendientes de evidencia. |
| Dinklange Arevalo, Sandro | 6.2.2, 6.3, 6.3.1 y 6.3.2 | 7.3, 7.3.1 y 7.3.2: documentación de despliegue continuo integrada al informe. |

### 4.c.1. Responsabilidades éticas y profesionales

| Integrante | Acciones realizadas — reflexión personal | Conclusiones personales |
| :--- | :--- | :--- |
| **Mallqui Vilca, Dhilsen Armil** | Desarrollé la documentación BDD y de pruebas de sistema de 6.1.3 y 6.1.4. Identifiqué escenarios, herramientas, resultados y límites de la emulación móvil para no presentar una prueba responsive como validación de un dispositivo físico. Conservo las fuentes y las evidencias para que otro integrante pueda revisar lo entregado. | Reconozco mi responsabilidad de comunicar qué se probó y qué falta comprobar. La trazabilidad y la atribución de fuentes permiten una revisión profesional sin confundir resultados funcionales con ausencia total de riesgos. |
| **Diaz Mendoza, Sebastian Victor Andre** | Desarrollé las pruebas unitarias de 6.1.1 y las de integración de 6.1.2, y consolidé la estrategia de 6.1 y la evaluación heurística de 6.3.3. Documenté defectos y revalidación, manteniendo las expectativas de las pruebas y diferenciando hallazgos confirmados de observaciones pendientes. En 7.1 preparé y ejecuté CI con resultados y artefactos verificables. | Asumo la responsabilidad de no atribuir aprobación a actividades sin evidencia. Los resultados 20/20 unitarios y 14/14 de integración acreditan sus casos, pero no equivalen a certificar toda la aplicación ni a cerrar la seguridad pendiente. |
| **Ramirez Escalante, Carlo Patricio** | Desarrollé el análisis estático, las convenciones de código y la evaluación de calidad y seguridad de 6.2.1 a 6.2.1.2. Identifiqué herramientas, métricas y avisos de dependencias sin presentar una compilación aprobada como ausencia de vulnerabilidades. Mi aporte de 7.4 organiza la documentación de monitoreo y sus componentes. | Reconozco que una presentación responsable debe conservar los hallazgos abiertos y explicar los criterios de cada herramienta. Las convenciones y métricas facilitan la colaboración y el mantenimiento, pero requieren revisión profesional contextual. |
| **Oblitas Alcalde, Rodrigo** | Organicé la documentación de la auditoría realizada y recibida en 6.4, diferenciando equipos, productos y fuentes. Conservé las severidades preliminares y los casos que requieren confirmación, y separé las recomendaciones de modificaciones efectivamente verificadas. Documenté 7.2 sobre entrega continua y sus etapas, distinguiendo las pruebas existentes de la preparación de staging y aprobación aún no acreditadas. | Reconozco el deber de evaluar a otros equipos con criterios explícitos, respetar sus evidencias y no atribuirles cambios o resultados no comprobados. Registrar el origen de cada observación fortalece la originalidad y la rendición de cuentas del trabajo. |
| **Dinklange Arevalo, Sandro** | Desarrollé la revisión de 6.2.2 y la documentación de validación de 6.3 a 6.3.2: diseño y registro de entrevistas. Distinguí la opinión de los participantes, los hallazgos documentales y las comprobaciones técnicas. En 7.3 organicé la descripción de herramientas y etapas del despliegue continuo. | Reconozco que debo representar fielmente las entrevistas y no inventar aprobación por pares, participantes o actas. La revisión debe dejar identificados sus límites y pendientes para permitir decisiones éticas e informadas. |

### 4.c.2. Evaluación de impactos y juicios informados

| Integrante | Acciones realizadas — reflexión personal | Conclusiones personales |
| :--- | :--- | :--- |
| **Mallqui Vilca, Dhilsen Armil** | Relacioné los recorridos de acceso y consulta con las tareas del personal de almacén y de los gestores farmacéuticos. La repetición de escenarios en escritorio y móvil emulado permite examinar barreras de uso en diferentes contextos, aunque no mide por sí sola la reducción de incidentes o mermas. | Concluyo que la compatibilidad de la interfaz puede favorecer el acceso de usuarios en distintos dispositivos. Para estimar beneficios sociales, ambientales o económicos necesito medir adopción, tiempos y pérdidas con usuarios y datos representativos. |
| **Diaz Mendoza, Sebastian Victor Andre** | Vinculé la interpretación de lecturas ausentes, la autenticación y la comunicación entre componentes con decisiones que afectan la conservación y la confianza de los usuarios. En CI procuré que la verificación fuera reproducible y que los recursos de prueba fueran temporales, sin usar información de producción. | Concluyo que detectar regresiones antes de integrar cambios puede reducir retrabajo y errores operativos. Su impacto económico o ambiental debe medirse; las pruebas técnicas no demuestran por sí solas ahorro, seguridad clínica ni reducción de residuos. |
| **Ramirez Escalante, Carlo Patricio** | Relacioné complejidad, duplicación, dependencias y observabilidad con el costo de mantenimiento y la continuidad del servicio. La documentación de alertas y notificaciones permite plantear cómo identificar incidentes que afecten a usuarios de diferentes establecimientos. | Concluyo que calidad y monitoreo aportan indicadores para priorizar riesgos y esfuerzo. La disponibilidad sostenida, el costo de incidentes y el consumo de recursos deben comprobarse con registros operativos; no los doy por demostrados por definir un umbral. |
| **Oblitas Alcalde, Rodrigo** | Relacioné las observaciones de accesibilidad, navegación y claridad con usuarios que pueden operar con distintas habilidades y condiciones de conectividad. La priorización de los hallazgos permite plantear mejoras con mayor utilidad y menor retrabajo para ambos equipos. | Concluyo que una auditoría puede orientar decisiones sobre inclusión, confianza y esfuerzo de corrección. El efecto real de las recomendaciones requiere revalidación y pruebas con usuarios; no infiero beneficios medidos a partir de una inspección visual. |
| **Dinklange Arevalo, Sandro** | Relacioné las necesidades de los dos segmentos con la utilidad y comprensión de KairoLabs. Las entrevistas ayudan a identificar barreras de adopción y prioridades, mientras que el análisis de despliegue plantea continuidad y capacidad de mantenimiento en el contexto de uso. | Concluyo que escuchar a los usuarios permite discutir impactos sociales y costos de adopción con mayor fundamento. Una muestra limitada no demuestra aceptación general ni beneficios económicos o ambientales; esos resultados requieren mediciones posteriores. |

### Evidencias de referencia

- [Capítulo VI: verificación, validación, heurísticas y auditorías](61-chapter-VI-Verification%26Validation.md).
- [Capítulo VII: aportes y evidencias CI](71-chapter-VII-devops-practices.md).
- Runs CI de 7.1: [frontend](https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Frontend/actions/runs/43542409469) y [plataforma](https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Platform/actions/runs/43542367043).
