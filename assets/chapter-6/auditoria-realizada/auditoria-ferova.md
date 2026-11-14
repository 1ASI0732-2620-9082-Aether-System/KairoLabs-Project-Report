# Auditoría realizada de experiencia de usuario — Ferova

## Identificación de los equipos y productos

| Campo | Detalle |
|---|---|
| Tipo de auditoría | Realizada por Aether System al grupo SANUVI |
| Equipo auditor | Aether System |
| Producto del equipo auditor | KairoLabs |
| Responsable de la auditoría | Dhilsen Mallqui Vilca |
| Otros integrantes identificados del equipo auditor | Sebastián Víctor André Díaz Mendoza; Carlo Patricio Ramírez Escalante; Rodrigo Oblitas Alcalde |
| Grupo auditado | SANUVI |
| Producto auditado | Ferova Platform |
| Integrantes del grupo auditado | Quijandria Araneda, Vicente; Baca Camargo, Vitaly Arturo; Peñaranda Caldas, Gabriel Augusto; Apaza Bocanegra, Elizabeth Noelia; Damián Pereira, Luis Alberto |
| Alcance | Landing page, aplicación web para personal de salud y aplicación móvil Android de acceso para madres |
| Informe del proyecto | [sanuvi-report](https://github.com/SANUVI-Diseno-de-Experimentos-SW/sanuvi-report) |
| Landing page | [ferova-landing-page](https://github.com/SANUVI-Diseno-de-Experimentos-SW/ferova-landing-page) |
| Aplicación web | [WebApplication1](https://github.com/SANUVI-Diseno-de-Experimentos-SW/WebApplication1) |
| Aplicación Android | [ferova-mobile-android](https://github.com/SANUVI-Diseno-de-Experimentos-SW/ferova-mobile-android) |

## Alcance y método

La evaluación se organiza en este orden: landing page, aplicación web y aplicación móvil Android. La landing y la web se revisaron mediante capturas de las versiones en ejecución compartidas por el equipo; para la web se muestran cuentas y vistas distintas de paciente, coordinación/administración y atención clínica. Android se revisó mediante capturas de la app en ejecución. La app móvil mostrada permite el acceso de madres y la gestión de sus hijos.

Las tres plataformas cuentan con revisión visual de capturas, pero faltan pruebas completas de interacción y adaptación a distintos tamaños. La inspección directa de los repositorios remotos no pudo completarse desde este entorno. Las severidades son preliminares: 1 = cosmético, 2 = menor, 3 = mayor, 4 = crítico.

## Cronograma

| Fecha | Actividad | Participantes | Duración |
|---|---|---|---|
| 09/11/2026 | Inspección visual de landing, aplicación web y aplicación Android; revisión de los flujos y hallazgos observados. | Dhilsen Mallqui Vilca, responsable de auditoría de Aether System. | 1 hora y 30 minutos |

## 1. Auditoría de la landing page

**Evidencia analizada:** capturas de portada, sección “El problema”, funcionalidades, audiencias y flujo “Cómo funciona” compartidas por el equipo.

| # | Hallazgo observado | Severidad preliminar (1-4) | Heurística / principio | Recomendación |
|---|---|---:|---|---|
| LP-01 | La portada indica “1 de 3” y la sección del problema “80%” para abandono del tratamiento. Podrían referirse a poblaciones o causas distintas; la página no deja claras sus definiciones ni muestra la fuente del 80%. Además, “−10% menos abandonos con Ferova” no presenta fuente, periodo, población ni evidencia del resultado. | 3 | Consistencia; credibilidad; visibilidad de la fuente. | Especificar fuente, población, periodo y definición junto a cada cifra. Aclarar si el 1 de 3 y el 80% describen fenómenos diferentes. Sustentar el efecto atribuido a Ferova o reformularlo como objetivo, si aún no hay resultados medidos. |
| LP-02 | “Vence la anemia con cada dosis” puede entenderse como una promesa de resultado clínico garantizado. El resto del texto describe seguimiento y adherencia, pero no matiza que el resultado depende del tratamiento indicado y de la evaluación del personal de salud. | 3 | Correspondencia con el mundo real; lenguaje claro; comunicación responsable. | Describir el apoyo de Ferova a la adherencia y al seguimiento sin asegurar que cada dosis vence o cura la anemia. Revisar el texto con personal de salud. |
| LP-03 | La tarjeta “Madres y Cuidadores” invita también a cuidadores y menciona gestantes; según la comprobación reportada por el equipo, la app móvil permite el ingreso solo a madres. La elegibilidad que comunica la página no coincide claramente con el acceso disponible. | 2 | Consistencia entre plataformas; correspondencia con el mundo real. | Aclarar quién puede crear una cuenta y usar FerovaFamily. Si cuidadores o gestantes todavía no pueden ingresar, ajustar la descripción o explicar la limitación. |
| LP-04 | La tarjeta “Teleconsulta con tu enfermera” promete respuestas “en menos de 24 horas”. La página no especifica horario, días hábiles ni qué ocurre si la enfermera asignada no responde dentro del plazo. | 2 | Expectativas claras; visibilidad de condiciones del servicio; confianza. | Definir cómo se calcula el plazo y los canales de contingencia. Mantener esa promesa solo si el equipo puede cumplirla de manera sostenida. |
| LP-05 | La etiqueta “Sistema Oficial de Vigilancia y Control de Anemia Infantil” presenta FerovaClinic como sistema oficial. Las capturas no indican qué entidad lo reconoce o autoriza. | 3 (condicional) | Credibilidad; correspondencia con el contexto; transparencia. | Confirmar si existe autorización institucional. Si no es un sistema oficial, retirar esa etiqueta o atribuirla correctamente para no crear una impresión de aval gubernamental. |
| LP-06 | En “Cómo funciona” se afirma que la madre crea su perfil y el del hijo “en menos de 2 minutos”. No se aporta evidencia de una medición de tiempo. | 2 | Expectativas claras; credibilidad; eficiencia. | Verificar el tiempo mediante pruebas con madres del segmento objetivo o cambiarlo por una descripción sin promesa temporal. |

## 2. Auditoría de la aplicación web

**Evidencia analizada:** capturas de acceso y vistas separadas de coordinación/administración, administración de postas y atención clínica. Las cuentas son distintas; los conteos entre cuentas no se deben comparar como si compartieran datos.

| # | Hallazgo observado | Severidad preliminar (1-4) | Heurística / principio | Recomendación |
|---|---|---:|---|---|
| WEB-01 | La pantalla de acceso titula el formulario “Portal del Paciente”, mientras que el panel informativo describe funciones para enfermería y administración. Las capturas muestran cuentas distintas para coordinación/administración y atención clínica. No se observa si esos roles usan el mismo punto de entrada. | Pendiente de confirmar | Correspondencia con el sistema real; consistencia; reconocimiento de opciones. | Confirmar si los roles acceden desde esa misma pantalla. Si comparten la entrada, indicar cómo se dirige cada usuario a su portal; si no, aclarar el destino y el acceso de cada perfil. |
| WEB-02 | Los saludos y etiquetas de perfil muestran valores literales “string string” en las vistas de coordinación y enfermería. | 2 | Correspondencia con el mundo real; confianza; calidad de los datos. | Reemplazar los valores de prueba por datos válidos y definir una alternativa neutra cuando el nombre no esté disponible. Verificarlo en cada rol. |
| WEB-03 | El resumen del coordinador muestra 0% de adherencia junto con cero postas activas y el estado “No tienes postas asignadas”. Sin pacientes o mediciones, 0% puede interpretarse como una adherencia medida y deficiente. | 2 | Visibilidad del estado; comunicación de datos; prevención de interpretaciones erróneas. | Cuando no exista población para calcular la métrica, mostrar “Sin datos” o “No disponible” y explicar el denominador; reservar 0% para mediciones efectivamente realizadas. |
| WEB-04 | La pantalla de postas está mayormente en español, pero el buscador dice “Filter facilities…” y la tarjeta usa “ASSIGNED PERSONNEL”. | 1 | Consistencia y estándares; idioma de la interfaz. | Traducir esos textos (“Buscar postas…”, “Personal asignado”) y revisar las demás vistas por etiquetas sin traducir. |
| WEB-05 | La captura del historial médico muestra “Cargando pacientes…” a la vez que “0 registros disponibles” y un aviso de que el menor no figura en la base nominal. Si se muestran antes de terminar la carga, pueden comunicar un resultado vacío prematuro. | 2 | Visibilidad del estado; prevención de errores; estados de carga y vacío claros. | Mantener el estado de carga hasta completar la consulta y mostrar el estado vacío o el aviso solo tras recibir una respuesta definitiva. Confirmar si la combinación persiste después de cargar. |
| WEB-06 | En la captura del acceso aparece un documento de identidad completo. No se sabe si es un dato sintético o real. | 3 (condicional) | Privacidad; minimización de datos; confianza. | Antes de compartir evidencia, usar cuentas de prueba y ocultar documentos de identidad y cualquier dato personal real. Mantener el hallazgo condicionado hasta confirmar el origen del dato. |
| WEB-07 | El dashboard de coordinación informa cero postas activas y “No tienes postas asignadas”; la vista “Mis Postas” muestra una instalación. Como las capturas pueden corresponder a cuentas distintas, esta comparación no demuestra una inconsistencia. | Pendiente de validar | Consistencia de datos; visibilidad del estado. | Comparar ambas vistas usando la misma cuenta y momento. Si el total instalado y el activo difieren, mostrar el estado de cada posta y definir claramente ambos conteos. |
| WEB-08 | El diseño de formularios disponible no permite confirmar adaptación a móvil, legibilidad, foco, contraste ni mensajes de validación con teclado. | Pendiente de revisión | Accesibilidad; prevención y recuperación de errores; flexibilidad. | Revisar el sitio implementado con teclado, en móvil y con ampliación; comprobar foco visible, contraste, etiquetas y mensajes junto al campo afectado. |

**Fortaleza observada:** la navegación y el contenido principal cambian según el perfil: coordinación tiene Inicio/Mapa/Postas y atención clínica tiene Inicio/Pacientes/Consultas/Historial. También se explican los resultados vacíos de “Sin pacientes asignados” y de búsqueda sin coincidencias. Hay que comprobar las transiciones y permisos con cada cuenta.

## 3. Auditoría de la aplicación móvil Android

**Evidencia analizada:** capturas de inicio, selección de hijos, dosis, registro nutricional, búsqueda de postas y registro de paciente compartidas por el equipo.

| # | Hallazgo observado | Severidad preliminar (1-4) | Heurística / principio | Recomendación |
|---|---|---:|---|---|
| MOB-01 | En el encabezado de inicio aparece “¡Hola string!”, un valor de sustitución en lugar del nombre de la madre. | 2 | Correspondencia con el mundo real; prevención de errores; confianza. | Sustituir el valor de prueba por el nombre del perfil y definir un texto alternativo si no está disponible. |
| MOB-02 | La ficha de una posta muestra los valores genéricos “string” y una distancia de “0,0 km”. La captura no permite identificar con confianza el establecimiento ni confirmar si la distancia corresponde a la ubicación actual. | 3 | Correspondencia con el mundo real; visibilidad del estado; confianza y prevención de daño. | Mostrar nombre y dirección reales, calcular la distancia desde la ubicación autorizada y presentar estados claros cuando falten permisos o datos. |
| MOB-03 | Se ingresa una porción de 23 g de acelga cocida, cuyo catálogo indica 1,8 mg de hierro por 100 g. El resumen muestra “0,0 mg Fe” y 0,02 mg absorbidos. Si “0,0 mg Fe” representa el hierro total de esa porción, no coincide con el cálculo proporcional (aprox. 0,41 mg); además, no se explica la diferencia con el hierro absorbido. | 3 (por validar) | Correspondencia con el mundo real; precisión de datos; comunicación clara. | Confirmar fórmula, definición de cada indicador y reglas de redondeo con el responsable nutricional. Mostrar precisión suficiente y separar claramente hierro total del alimento e hierro absorbido. No declararlo error confirmado hasta validar la fórmula. |
| MOB-04 | La app permite seleccionar más de un niño, pero el equipo informa que el acceso está habilitado únicamente para madres. La interfaz y la auditoría deben dejar claro quién puede operar la cuenta y cómo se autoriza al apoderado. | Pendiente de aclarar | Consistencia; control y correspondencia con el modelo de usuario. | Confirmar la política de acceso y documentar si la madre puede registrar más de un hijo, añadir otro cuidador o transferir la cuenta. |
| MOB-05 | En el estado mostrado, el mensaje indica que la enfermera debe activar el tratamiento y “Confirmar Dosis” aparece deshabilitado. Ese estado sí está comunicado; no se confirma el problema de ambigüedad detectado antes en el mock-up. | Sin hallazgo en esta captura | Visibilidad del estado; prevención de errores. | Mantener el mensaje y la acción deshabilitada mientras no exista un tratamiento activo. Verificar también los estados con tratamiento activo y con dosis pendiente. |
| MOB-06 | Las capturas no permiten verificar adaptación a distintos tamaños, accesibilidad táctil, mensajes de error, permisos de ubicación, modo sin conexión ni flujos completos de citas y consultas. | Pendiente de revisión | Accesibilidad; control del usuario; prevención y recuperación de errores. | Probar los flujos completos en un dispositivo Android y registrar estados de carga, error, vacío, permisos denegados y confirmación de acciones. |

En una de las vistas de inicio, “Confirmar Dosis” queda parcialmente cubierto por la navegación inferior en la posición capturada; hay que verificar si el contenido puede desplazarse completamente y si existe espacio inferior suficiente antes de clasificarlo como defecto.

**Comportamiento móvil observado:** el mensaje indica que la enfermera debe activar el tratamiento y el botón “Confirmar Dosis” aparece deshabilitado. El estado y la acción no disponible son visibles en esa captura; queda pendiente probar los estados activos.

## Cierre y alcance de la auditoría

La auditoría realizada por Aether System se completó en una sesión de 1 hora y 30 minutos. Se revisaron visualmente las capturas disponibles de la landing page, FerovaClinic con cuentas de coordinación/administración y atención clínica, y FerovaFamily en Android. Los hallazgos están separados por producto y cada uno incluye severidad preliminar y recomendación.

La evaluación corresponde a una inspección visual de las pantallas compartidas. No se verificó desde esta revisión el destino de enlaces, todos los flujos posteriores a cada pantalla, el funcionamiento con teclado, la respuesta en otros tamaños de pantalla ni el comportamiento sin conexión. Las observaciones identificadas como condicionales o no concluyentes requieren contexto adicional para atribuir una causa; no se presentan como defectos confirmados.

No se insertaron imágenes en este documento. Las conclusiones se basan en el contenido visible de las capturas revisadas y en la información proporcionada por el equipo auditor.

## Referencias de los repositorios

- [Landing page](https://github.com/SANUVI-Diseno-de-Experimentos-SW/ferova-landing-page)
- [Aplicación web](https://github.com/SANUVI-Diseno-de-Experimentos-SW/WebApplication1)
- [Aplicación Android](https://github.com/SANUVI-Diseno-de-Experimentos-SW/ferova-mobile-android)
- [Ejemplo de auditoría — Restock](https://github.com/ui-topic-diseno-de-experimentos-10253/restock-report)
- [Ejemplo de auditoría — StockTrack](https://github.com/Inventiapp-Experimentos-16880/Report-stocktrack)
