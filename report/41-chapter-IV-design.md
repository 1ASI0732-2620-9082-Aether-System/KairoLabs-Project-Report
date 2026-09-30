# Capítulo IV: Product Design

En este capítulo se desarrolla la propuesta de diseño del producto KairoLabs, considerando tanto la experiencia de usuario como la arquitectura de software necesaria para representar y soportar las funcionalidades definidas previamente. Para ello, se toman como base las User Stories, el Product Backlog, los To-Be Scenario Maps y el Impact Mapping desarrollados en el capítulo anterior.

KairoLabs es una solución tecnológica orientada al monitoreo de las condiciones ambientales relacionadas con el almacenamiento y transporte de medicamentos y otros productos termosensibles. La plataforma busca facilitar la supervisión de variables como temperatura, humedad y exposición a la luz, permitiendo identificar desviaciones, generar alertas y mantener registros históricos que contribuyan con la trazabilidad de las condiciones de conservación.

A partir de este contexto, el diseño del producto busca mantener coherencia entre las necesidades identificadas en los usuarios y las diferentes experiencias digitales propuestas. Para ello, se desarrollan lineamientos visuales, arquitectura de información, propuestas UX/UI para las aplicaciones móvil y web, prototipos y diagramas de arquitectura de software.

---

## 4.1. Style Guidelines

En esta sección se establecen los lineamientos visuales y de interacción que serán utilizados en los diferentes productos digitales de KairoLabs. El objetivo es disponer de una referencia común para todo el equipo que permita mantener una presentación consistente entre la Landing Page, la Web Application y la Mobile Application.

Los Style Guidelines reúnen elementos como identidad de marca, tipografía, colores, espaciado y criterios de comunicación. De esta manera, el equipo puede utilizar un mismo conjunto de recursos visuales durante el diseño y desarrollo de las distintas interfaces.

La propuesta visual de KairoLabs busca transmitir precisión, confiabilidad y tecnología, debido a que la solución se encuentra orientada al monitoreo de condiciones ambientales dentro del sector farmacéutico y de salud.

Asimismo, se prioriza una presentación clara de los datos para facilitar la interpretación de métricas, estados, alertas y demás información generada por los sensores IoT.

---

### 4.1.1. General Style Guidelines

Los lineamientos generales de KairoLabs definen los criterios visuales que deben mantenerse en todos los productos digitales de la plataforma. Estas decisiones permiten construir una identidad consistente independientemente del dispositivo desde el cual el usuario acceda a la solución.

**Branding**

La identidad de KairoLabs se encuentra relacionada con los conceptos de monitoreo inteligente, conservación de medicamentos, trazabilidad y tecnología IoT.

La propuesta visual busca transmitir una imagen profesional y tecnológica, debido a que los principales usuarios del sistema pertenecen a hospitales, clínicas, farmacias, almacenes farmacéuticos y otras organizaciones vinculadas con la conservación de medicamentos.

KairoLabs busca diferenciarse visualmente mediante una interfaz limpia, con una cantidad reducida de elementos decorativos y una mayor prioridad sobre la información funcional. De esta manera, métricas como temperatura, humedad, iluminación y estados de los dispositivos pueden identificarse rápidamente.

El nombre KairoLabs representa una identidad vinculada con la tecnología y la oportunidad de actuar ante desviaciones ambientales. El término “Kairo” se relaciona conceptualmente con el momento oportuno, mientras que “Labs” permite asociar la marca con entornos tecnológicos, científicos y de monitoreo.

<p align="center">
  <img src="../assets/Logo-KairoLabs.png" alt="Logo KairoLabs" width="240"><br>
  <em>Nota: Logotipo principal utilizado en la identidad visual de KairoLabs.</em>
</p>

**Typography**

La tipografía utilizada en KairoLabs es **Outfit**, seleccionada por su apariencia geométrica, moderna y legible en interfaces digitales.

Esta fuente permite mantener consistencia tanto en títulos como en contenido general, formularios, tarjetas y elementos de navegación.

Se utilizan diferentes pesos tipográficos para establecer una jerarquía visual clara:

| Elemento | Configuración | Aplicación |
| :--- | :--- | :--- |
| **Títulos principales** | Bold 700 | Hero, encabezados principales y títulos de pantalla. |
| **Subtítulos** | SemiBold 600 | Secciones y componentes principales. |
| **Títulos secundarios** | Medium 500 | Tarjetas, formularios y agrupaciones de información. |
| **Texto general** | Regular 400 | Contenido descriptivo y datos generales. |
| **Texto secundario** | Light 300 / Regular 400 | Etiquetas, ayudas y datos complementarios. |
| **Botones** | Medium 500 / SemiBold 600 | Acciones principales y secundarias. |

En el caso de las métricas ambientales, los valores numéricos reciben una mayor jerarquía visual que sus respectivas etiquetas. Esto permite que el usuario identifique rápidamente información como la temperatura actual, humedad o intensidad lumínica.

<p align="center">
  <img src="../assets/Tipografia-example.png" alt="Tipografía utilizada en KairoLabs" width="700"><br>
  <em>Nota: Ejemplo de aplicación de la tipografía Outfit en KairoLabs.</em>
</p>

**Colors**

La paleta de colores de KairoLabs combina tonos institucionales con colores funcionales utilizados para representar métricas y estados del sistema.

Los colores principales son el naranja y el azul marino, los cuales permiten mantener una identidad tecnológica y profesional.

| Color | Muestra | Código HEX | Uso |
| :--- | :---: | :---: | :--- |
| **Naranja Energía** | <span style="display:inline-block;width:90px;height:22px;background:#F37021;border:1px solid #d9d9d9;border-radius:4px;"></span> | `#F37021` | Acciones principales, elementos destacados y representación de temperatura. |
| **Azul Marino Profundo** | <span style="display:inline-block;width:90px;height:22px;background:#112433;border:1px solid #d9d9d9;border-radius:4px;"></span> | `#112433` | Navegación, títulos y elementos institucionales. |
| **Blanco** | <span style="display:inline-block;width:90px;height:22px;background:#FFFFFF;border:1px solid #d9d9d9;border-radius:4px;"></span> | `#FFFFFF` | Fondos principales y tarjetas. |
| **Gris Carbón** | <span style="display:inline-block;width:90px;height:22px;background:#333333;border:1px solid #d9d9d9;border-radius:4px;"></span> | `#333333` | Texto principal y contenido descriptivo. |

Además, se utilizan colores específicos para facilitar la identificación de las variables monitoreadas:

| Variable | Color principal | Fondo de apoyo | Aplicación |
| :--- | :---: | :---: | :--- |
| **Temperatura** | `#F37021` | `#FFF5F1` | Métricas y elementos relacionados con temperatura. |
| **Humedad** | `#3B82F6` | `#EFF6FF` | Métricas relacionadas con humedad. |
| **Luz / Iluminación** | `#FBBF24` | `#FFFBEB` | Métricas relacionadas con exposición lumínica. |
| **Estado positivo** | `#10B981` | `#ECFDF5` | Condiciones normales o estados correctos. |

Para los estados del sistema se consideran colores que facilitan una interpretación rápida de las condiciones monitoreadas.

- Verde: condición normal.
- Amarillo: condición de advertencia.
- Rojo: condición crítica.
- Azul: información complementaria.

Los colores de estado deben utilizarse junto con textos o iconos para evitar que la interpretación de una condición dependa únicamente del color.

<p align="center">
  <img src="../assets/escala-colores.png" alt="Paleta de colores de KairoLabs" width="700"><br>
  <em>Nota: Paleta cromática empleada en la identidad visual y métricas de KairoLabs.</em>
</p>

**Spacing**

El espaciado utilizado en KairoLabs se basa principalmente en múltiplos de 8 píxeles. Esta decisión permite mantener consistencia visual entre tarjetas, botones, formularios y diferentes contenedores de información.

Se considera una unidad mínima de 4 píxeles para separaciones pequeñas y una estructura progresiva basada en 8, 16, 24, 32 y 48 píxeles.

| Espaciado | Aplicación |
| :--- | :--- |
| **4 px** | Separación mínima entre iconos y etiquetas. |
| **8 px** | Padding interno y separación entre elementos relacionados. |
| **16 px** | Separación entre tarjetas y grupos de información. |
| **24 px** | Espacio entre bloques principales de una pantalla. |
| **32–48 px** | Separación entre grandes grupos de contenido. |

Este sistema permite organizar la interfaz de manera uniforme y evitar una concentración excesiva de información dentro de los dashboards.

<p align="center">
  <img src="../assets/escala-medidas.png" alt="Sistema de espaciado de KairoLabs" width="700"><br>
  <em>Nota: Sistema de espaciado utilizado en las interfaces de KairoLabs.</em>
</p>

**Tono de Comunicación y Lenguaje Aplicado**

El tono de comunicación utilizado por KairoLabs busca mantener coherencia con el contexto en el que será utilizada la solución.

La plataforma adopta un tono principalmente:

- **Serio**, debido a que se trabaja con información relacionada con la conservación de medicamentos.
- **Formal**, para mantener una comunicación apropiada con organizaciones del sector salud.
- **Respetuoso**, especialmente en mensajes relacionados con alertas, incidencias y usuarios.
- **Sereno**, evitando el uso de mensajes innecesariamente alarmistas.
- **Directo**, para facilitar la interpretación de estados y acciones.
- **Técnico pero comprensible**, utilizando términos del dominio sin presentar conceptos técnicos innecesarios para el usuario final.

Los mensajes relacionados con el monitoreo deben ser breves y permitir comprender rápidamente la situación presentada.

Algunos ejemplos son:

- “Temperatura fuera del rango configurado”.
- “Humedad próxima al límite permitido”.
- “Dispositivo sin conexión”.
- “Lecturas actualizadas correctamente”.
- “Alerta atendida”.
- “No se encontraron resultados”.

De esta manera, la comunicación busca convertir la información generada por los sensores en mensajes comprensibles y accionables para los usuarios.

---

### 4.1.2. Web Style Guidelines

Los Web Style Guidelines de KairoLabs establecen los criterios visuales y de interacción aplicados a la Landing Page y a la Web Application.

La propuesta adopta un diseño responsive que busca mantener claridad y consistencia en computadoras de escritorio, tablets y navegadores móviles. Los elementos se reorganizan según el espacio disponible sin modificar la jerarquía principal de la información.

La interfaz web utiliza un sistema de rejilla de 12 columnas que permite distribuir de forma flexible tarjetas, formularios, tablas, gráficos y demás componentes.

| Componente | Descripción | Aplicación |
| :--- | :--- | :--- |
| **Grid de 12 columnas** | Estructura principal para distribuir contenido. | Landing Page, dashboards y módulos administrativos. |
| **Cards** | Agrupan información relacionada dentro de un mismo bloque. | Métricas, dispositivos, establecimientos, alertas y planes. |
| **Sidebar** | Navegación lateral para usuarios autenticados. | Acceso a los módulos principales de la Web Application. |
| **Navbar** | Navegación principal superior. | Landing Page. |
| **Tablas** | Permiten organizar registros y datos administrativos. | Establecimientos, operadores, dispositivos y demás listados. |

La jerarquía visual prioriza la información que requiere una interpretación inmediata. Dentro de los dashboards, las métricas y alertas principales se muestran antes que los datos administrativos o históricos.

Los botones mantienen una apariencia consistente. Las acciones principales utilizan el naranja `#F37021`, mientras que las acciones secundarias poseen menor peso visual.

Los formularios presentan campos claramente identificados y mensajes de validación comprensibles. Cuando el usuario realiza una acción, el sistema proporciona retroalimentación mediante confirmaciones, mensajes de error o cambios visuales de estado.

En la Landing Page se utiliza una navegación superior que permite acceder a las principales secciones del contenido. En la Web Application se utiliza principalmente un menú lateral que facilita el acceso constante a los módulos disponibles según el rol del usuario.

El comportamiento responsive se plantea de la siguiente manera:

| Dispositivo | Breakpoint referencial | Comportamiento |
| :--- | :---: | :--- |
| **Mobile** | `≤ 480 px` | Organización principal en una columna y navegación compacta. |
| **Tablet** | `481–768 px` | Distribución de una o dos columnas según el contenido. |
| **Desktop** | `≥ 1024 px` | Uso completo del grid de 12 columnas y visualización ampliada de información. |

En pantallas de escritorio se aprovecha una mayor cantidad de espacio para presentar indicadores, gráficos y tablas simultáneamente. En dispositivos con menor resolución, la información se reorganiza priorizando las métricas y acciones de mayor relevancia.

Las siguientes vistas muestran la aplicación del estilo web definido para KairoLabs.

<p align="center">
  <img src="../assets/navMU.png" alt="Navegación de la Landing Page de KairoLabs" width="700"><br>
  <em>Nota: Aplicación de la navegación y jerarquía visual de KairoLabs.</em>
</p>

<p align="center">
  <img src="../assets/sobrePlataformaMU.png" alt="Presentación de la plataforma KairoLabs" width="700"><br>
  <em>Nota: Aplicación de la identidad visual en la presentación de la plataforma.</em>
</p>

<p align="center">
  <img src="../assets/tecMU.png" alt="Tecnología de KairoLabs" width="700"><br>
  <em>Nota: Aplicación de los lineamientos visuales en la sección tecnológica.</em>
</p>

<p align="center">
  <img src="../assets/paraQuienMU.png" alt="Sectores objetivo de KairoLabs" width="700"><br>
  <em>Nota: Presentación visual de los sectores objetivo de KairoLabs.</em>
</p>

<p align="center">
  <img src="../assets/comoFuncionaMU.png" alt="Funcionamiento de KairoLabs" width="700"><br>
  <em>Nota: Organización visual utilizada para explicar el funcionamiento de la plataforma.</em>
</p>

<p align="center">
  <img src="../assets/quienesSomosMU.png" alt="Equipo KairoLabs" width="700"><br>
  <em>Nota: Aplicación del sistema visual en la presentación institucional.</em>
</p>

<p align="center">
  <img src="../assets/planesPagosMU.png" alt="Planes de KairoLabs" width="700"><br>
  <em>Nota: Presentación de los planes mediante componentes visualmente consistentes.</em>
</p>

<p align="center">
  <img src="../assets/contactoMU.png" alt="Contacto de KairoLabs" width="700"><br>
  <em>Nota: Aplicación del estilo de formularios y acciones principales.</em>
</p>

<p align="center">
  <img src="../assets/footerMU.png" alt="Footer de KairoLabs" width="700"><br>
  <em>Nota: Aplicación de la identidad visual en el pie de página.</em>
</p>

---

### 4.1.3. Mobile Style Guidelines

Los Mobile Style Guidelines establecen la adaptación de los lineamientos generales de KairoLabs para las interfaces móviles.

La aplicación móvil debe conservar la identidad visual definida anteriormente, utilizando la misma tipografía, paleta de colores, sistema de espaciado, iconografía y tono de comunicación.

Sin embargo, debido al menor espacio disponible en dispositivos móviles, la información debe presentarse de manera más compacta y priorizada.

Las métricas principales, alertas y estados deben ocupar posiciones de mayor jerarquía, mientras que la información secundaria puede presentarse en pantallas de detalle.

La estructura móvil debe priorizar:

- Información principal del estado del sistema.
- Alertas.
- Métricas ambientales.
- Dispositivos.
- Historial.
- Perfil del usuario.

Los botones y controles deben contar con dimensiones apropiadas para la interacción táctil y mantener una separación suficiente para evitar acciones involuntarias.

Los elementos de navegación deben permanecer claramente identificados mediante texto e iconografía. Asimismo, la interfaz debe mantener los mismos conceptos y etiquetas utilizados en la experiencia web para reducir la curva de aprendizaje entre plataformas.

En la versión actual del material del proyecto todavía no se incluyen evidencias gráficas específicas del Mobile Style Guidelines. Estas deberán mantener la misma identidad establecida en los General Style Guidelines cuando se incorporen los correspondientes wireframes y mock-ups móviles.

---

#### 4.1.3.1. iOS Mobile Style Guidelines

Para la versión iOS de KairoLabs se mantiene la identidad visual definida en los lineamientos generales, adaptando la organización de la interfaz al entorno móvil.

La tipografía, colores, iconografía y estados visuales deben permanecer consistentes con el resto del producto para que el usuario reconozca que se encuentra dentro del mismo ecosistema digital.

La navegación debe priorizar la simplicidad y permitir acceder rápidamente a las principales funciones relacionadas con monitoreo, alertas, dispositivos e historial.

Los formularios y controles deben organizarse verticalmente para facilitar su utilización en pantallas pequeñas. Asimismo, las vistas secundarias deben proporcionar mecanismos claros para regresar a la pantalla anterior.

La información crítica, como una alerta o una condición ambiental fuera del rango esperado, debe mantener la misma representación semántica utilizada en la Web Application mediante colores, iconos y etiquetas.

Actualmente, el material base del proyecto no presenta todavía mock-ups específicos de la aplicación para iOS. Por ello, estos lineamientos funcionarán como referencia para mantener la consistencia visual cuando se elaboren las evidencias correspondientes de la aplicación móvil.

---

#### 4.1.3.2. Android Mobile Style Guidelines

La versión Android de KairoLabs mantiene la misma identidad visual utilizada en la Landing Page, Web Application y variante móvil para iOS.

Los componentes deben conservar la tipografía Outfit, la paleta cromática institucional, los estados visuales y el sistema de espaciado establecidos previamente.

La interfaz debe facilitar el acceso a las funciones principales del sistema desde dispositivos móviles, priorizando la consulta de métricas, alertas, dispositivos e información histórica.

La distribución del contenido debe adaptarse a una estructura principalmente vertical, utilizando tarjetas y agrupaciones de información que permitan identificar rápidamente los elementos más relevantes.

Las acciones principales deben encontrarse claramente diferenciadas de las acciones secundarias, mientras que operaciones que puedan modificar o eliminar información deben requerir una confirmación comprensible antes de ejecutarse.

Al igual que en iOS, los estados relacionados con las condiciones ambientales deben mantener la misma representación utilizada en la experiencia web, permitiendo que un usuario pueda cambiar de plataforma sin tener que aprender nuevamente el significado de los colores o etiquetas.

En la versión actual del material base todavía no se presentan evidencias gráficas específicas para Android. Estas deberán incorporarse posteriormente manteniendo los mismos criterios visuales y de comunicación establecidos para KairoLabs.

## 4.2. Information Architecture

La arquitectura de información de KairoLabs define la manera en que se organiza, etiqueta, presenta y permite localizar la información dentro de la Landing Page, la Web Application y la Mobile Application.

El objetivo principal es facilitar que los visitantes y usuarios puedan comprender rápidamente la estructura de la plataforma y encontrar las funcionalidades o datos que necesitan sin realizar recorridos innecesarios.

Debido a que KairoLabs maneja información relacionada con monitoreo ambiental, dispositivos IoT, establecimientos, alertas, registros históricos y reportes, es necesario establecer una estructura clara que reduzca la carga cognitiva y permita priorizar la información de mayor relevancia.

Las decisiones de arquitectura de información se basan en los segmentos definidos previamente, considerando principalmente al personal operativo de almacenes farmacéuticos y a los gestores o responsables de entidades de salud.

La estructura propuesta combina sistemas de organización jerárquica y secuencial, etiquetas breves y comprensibles, mecanismos de búsqueda mediante filtros y distintos patrones de navegación según el tipo de experiencia.

---

### 4.2.1. Organization Systems

En KairoLabs se emplean distintos sistemas de organización de contenido con el objetivo de optimizar la supervisión y gestión de las condiciones ambientales en almacenes farmacéuticos.

La organización de la información busca que los usuarios puedan identificar rápidamente datos críticos, acceder a funcionalidades específicas y completar procesos de manera ordenada.

**Organización jerárquica**

La organización jerárquica se utiliza principalmente en dashboards, paneles de monitoreo, módulos de dispositivos y vistas de alertas.

La información se presenta de acuerdo con su nivel de relevancia. Los elementos que requieren atención inmediata, como alertas activas o condiciones ambientales fuera del rango esperado, reciben una mayor jerarquía visual que los datos secundarios.

Dentro de un dashboard, la información puede organizarse siguiendo una estructura similar a la siguiente:

- Estado general.
- Alertas activas.
- Métricas ambientales.
- Dispositivos monitoreados.
- Información histórica.
- Acciones administrativas.

Esta jerarquía facilita que el usuario identifique primero los elementos que requieren una acción o supervisión.

**Organización secuencial**

La organización secuencial se aplica en aquellas tareas que requieren completar varios pasos.

Dentro de KairoLabs, esta estructura puede utilizarse en procesos como:

- Registro de usuarios.
- Registro de establecimientos.
- Registro de dispositivos.
- Configuración de elementos del sistema.
- Gestión y atención de alertas.

La información se presenta siguiendo un orden lógico que permite al usuario avanzar progresivamente hasta completar la tarea.

**Organización por audiencia**

KairoLabs distingue principalmente dos segmentos de usuarios.

El personal operativo de almacenes farmacéuticos utiliza funcionalidades relacionadas con:

- Monitoreo de condiciones ambientales.
- Visualización de métricas.
- Consulta de dispositivos.
- Recepción y revisión de alertas.
- Consulta de registros históricos.

Por otro lado, las entidades de salud y gestores farmacéuticos requieren funcionalidades relacionadas con:

- Supervisión de múltiples establecimientos.
- Gestión de operadores.
- Gestión de dispositivos.
- Consulta de información consolidada.
- Reportes históricos.
- Alertas globales.
- Administración de suscripciones.

La interfaz adapta las opciones disponibles de acuerdo con el rol del usuario, evitando presentar funcionalidades que no sean necesarias para sus actividades.

**Organización por tópicos**

El contenido también se agrupa mediante categorías funcionales.

Entre las principales categorías consideradas en KairoLabs se encuentran:

- Monitoreo ambiental.
- Establecimientos.
- Operadores.
- Dispositivos.
- Alertas.
- Transportes.
- Historial.
- Reportes.
- Suscripciones.
- Perfil y configuración.

Esta categorización permite que cada grupo de información pueda ser identificado con facilidad dentro de la navegación.

**Organización cronológica**

La organización cronológica se utiliza principalmente en información generada a lo largo del tiempo.

Se aplica en elementos como:

- Lecturas de sensores.
- Historial de alertas.
- Registros de monitoreo.
- Incidencias.
- Información histórica.
- Reportes.

Los registros pueden presentarse desde los eventos más recientes hacia los más antiguos, facilitando la consulta del estado actual y la revisión posterior de eventos anteriores.

La combinación de estos sistemas permite que KairoLabs mantenga una estructura adaptable a distintos tipos de contenido y usuarios.

La organización jerárquica facilita interpretar rápidamente la información crítica, mientras que la organización secuencial guía al usuario en procesos específicos. La categorización por audiencia y tópicos permite adaptar la experiencia a cada perfil y la organización cronológica facilita consultar información histórica.

---

### 4.2.2. Labeling Systems

El sistema de etiquetado de KairoLabs busca representar la información mediante términos breves, claros y consistentes.

Las etiquetas utilizadas dentro de la plataforma deben permitir que los visitantes y usuarios comprendan rápidamente qué información encontrarán al seleccionar una opción, evitando utilizar terminología técnica innecesaria o nombres ambiguos.

Para la Landing Page se consideran etiquetas orientadas principalmente a comunicar la propuesta de valor del producto.

| Etiqueta | Descripción |
| :--- | :--- |
| **Inicio** | Presenta la sección principal y la propuesta de valor de KairoLabs. |
| **Plataforma** | Explica las características principales de la solución. |
| **Tecnología** | Presenta información relacionada con sensores IoT y monitoreo ambiental. |
| **Sectores** | Muestra los tipos de instituciones a los que se encuentra orientado el producto. |
| **Cómo funciona** | Explica de manera resumida el funcionamiento de la solución. |
| **Nosotros** | Presenta información relacionada con el proyecto y el equipo responsable. |
| **Planes** | Presenta las alternativas de suscripción disponibles. |
| **Contacto** | Permite acceder a los canales de comunicación con el equipo. |

Dentro de la Web Application, las etiquetas se orientan a representar funcionalidades operativas y administrativas.

| Etiqueta | Descripción |
| :--- | :--- |
| **Dashboard** | Presenta una visión general del estado del sistema. |
| **Establecimientos** | Agrupa la información de las sedes registradas. |
| **Operadores** | Permite consultar y gestionar al personal asociado a los establecimientos. |
| **Dispositivos** | Agrupa los dispositivos IoT registrados dentro del sistema. |
| **Monitoreo** | Presenta las condiciones ambientales registradas. |
| **Alertas** | Muestra las desviaciones o eventos que requieren atención. |
| **Transportes** | Agrupa la información correspondiente al monitoreo durante transporte. |
| **Historial** | Permite consultar información registrada previamente. |
| **Reportes** | Presenta información consolidada y reportes del sistema. |
| **Planes** | Permite consultar información relacionada con la suscripción. |
| **Perfil** | Contiene la información del usuario. |
| **Configuración** | Agrupa las preferencias y opciones generales disponibles. |

Además, KairoLabs utiliza etiquetas específicas para representar estados del sistema.

| Estado | Significado |
| :--- | :--- |
| **Normal** | Las condiciones se encuentran dentro de los rangos establecidos. |
| **Advertencia** | Existe una condición cercana a un límite y requiere supervisión. |
| **Crítico** | Una condición se encuentra fuera del rango esperado y requiere atención. |
| **Sin conexión** | El dispositivo no se encuentra disponible o conectado. |
| **Atendida** | La alerta o incidencia ya fue gestionada. |

Las etiquetas deben mantenerse consistentes entre las diferentes plataformas. Por ejemplo, si una sección se denomina “Alertas” dentro de la Web Application, la Mobile Application debe utilizar el mismo término siempre que represente la misma funcionalidad.

Esta consistencia facilita que los usuarios puedan cambiar entre plataformas sin necesidad de aprender una nueva nomenclatura.

---

### 4.2.3. SEO Tags and Meta Tags

KairoLabs utiliza SEO Tags y Meta Tags en las principales páginas de la experiencia web con el objetivo de describir correctamente el contenido del producto y facilitar su identificación en motores de búsqueda.

Estas etiquetas se aplican principalmente a la Landing Page y a las páginas públicas relacionadas con la plataforma.

Las principales etiquetas consideradas son Title, Description, Keywords y Author.

| Página | Title | Description | Keywords | Author |
| :--- | :--- | :--- | :--- | :--- |
| **Inicio** | KairoLabs - Monitoreo inteligente de medicamentos | KairoLabs permite monitorear condiciones ambientales relacionadas con el almacenamiento de medicamentos mediante sensores IoT. | KairoLabs, monitoreo farmacéutico, sensores IoT, medicamentos, temperatura, humedad | Equipo KairoLabs |
| **Tecnología** | Tecnología IoT - KairoLabs | Conoce la tecnología utilizada por KairoLabs para monitorear temperatura, humedad y luz en entornos de almacenamiento. | IoT salud, sensores IoT, monitoreo ambiental, temperatura, humedad | Equipo KairoLabs |
| **Sectores** | Sectores - KairoLabs | Conoce los sectores e instituciones para los que está orientada la plataforma KairoLabs. | hospitales, clínicas, farmacias, almacenes farmacéuticos, monitoreo IoT | Equipo KairoLabs |
| **Planes** | Planes - KairoLabs | Consulta las alternativas de suscripción disponibles para utilizar KairoLabs. | planes KairoLabs, suscripción, monitoreo IoT, plataforma farmacéutica | Equipo KairoLabs |
| **Contacto** | Contacto - KairoLabs | Ponte en contacto con el equipo KairoLabs para solicitar información sobre la plataforma. | contacto KairoLabs, monitoreo medicamentos, IoT salud | Equipo KairoLabs |

Además, se utilizan Meta Tags básicas para garantizar una correcta visualización del sitio.

### 4.2.4. Searching Systems

En KairoLabs, se implementa un sistema de búsqueda y filtrado que permite a los usuarios acceder rápidamente a información relevante relacionada con el monitoreo ambiental de medicamentos. Este sistema busca reducir el tiempo de búsqueda, facilitar la supervisión de condiciones críticas y mejorar la toma de decisiones dentro de la plataforma.

El sistema está diseñado considerando los dos segmentos principales de usuarios: personal operativo de almacenes farmacéuticos y entidades de salud o gestores farmacéuticos, adaptando las opciones de búsqueda según sus necesidades específicas.

**Búsqueda y filtros en monitoreo de almacenes**

Para el personal operativo de almacenes farmacéuticos, se consideran las siguientes opciones:

- **Búsqueda por almacén o área:** permite localizar rápidamente un almacén, sala o zona específica dentro de la institución.
- **Filtrar por estado ambiental:** permite visualizar áreas según su estado actual, como “Normal”, “Alerta” o “Crítico”.
- **Filtrar por tipo de variable:** facilita consultar registros relacionados con temperatura, humedad o exposición a la luz.
- **Filtrar por rango de fechas:** permite revisar incidencias o registros históricos dentro de un periodo determinado.
- **Historial de alertas:** permite acceder a eventos previos relacionados con variaciones ambientales y condiciones fuera de rango.

Para las entidades de salud y gestores farmacéuticos, se consideran las siguientes opciones:

- **Filtrar por sede o institución:** permite supervisar múltiples almacenes o establecimientos desde un único entorno centralizado.
- **Filtrar por estado de monitoreo:** permite visualizar rápidamente sedes con incidencias activas o condiciones críticas.
- **Filtrar por rango de fechas:** facilita el análisis histórico y la generación de reportes para auditorías o control interno.
- **Búsqueda de registros históricos:** permite acceder a datos almacenados relacionados con temperatura, humedad y luz en diferentes sedes.
- **Filtrar por tipo de incidencia:** permite identificar eventos específicos asociados a fallas ambientales o incumplimientos de condiciones de almacenamiento.

**Búsqueda en módulos adicionales**

Además de las funciones de búsqueda relacionadas con el monitoreo de almacenes, KairoLabs incorpora mecanismos de búsqueda y filtrado en otros módulos de la plataforma.

- **Alertas:** permite buscar y filtrar alertas según prioridad, fecha o estado.
- **Reportes:** permite localizar reportes históricos por sede, fecha o tipo de variable monitoreada.
- **Usuarios y sedes:** permite buscar usuarios registrados o almacenes asociados a la institución.

**Visualización de resultados**

Los resultados de búsqueda se presentan mediante tablas y paneles organizados que muestran información clave como estado ambiental, fecha del registro, sede asociada y nivel de alerta.

Cada resultado permite acceder a una vista detallada donde el usuario puede revisar información específica sobre las condiciones monitoreadas y el historial relacionado.

En caso de no existir coincidencias, el sistema muestra mensajes informativos como “No se encontraron resultados”, evitando confusión y facilitando la comprensión del estado de la búsqueda.

**Flujo de búsqueda**

El sistema de búsqueda se encuentra integrado dentro de los módulos principales de monitoreo, alertas y reportes mediante barras de búsqueda y filtros visibles.

Los usuarios pueden aplicar, combinar o eliminar filtros según sus necesidades, permitiendo una navegación más fluida y facilitando el acceso rápido a la información relevante dentro de la plataforma.

---

### 4.2.5. Navigation Systems

En KairoLabs, la navegación ha sido diseñada para ser clara, intuitiva y eficiente tanto en la Landing Page como en la Web Application. La estructura de navegación busca facilitar el acceso rápido a información crítica relacionada con el monitoreo ambiental de medicamentos, reduciendo la complejidad operativa y mejorando la experiencia de uso para los distintos segmentos del sistema.

**Navegación en la Landing Page**

La Landing Page guía a los visitantes a través de la propuesta de valor de KairoLabs, permitiéndoles comprender rápidamente el problema, la solución tecnológica y los beneficios del sistema.

El menú de navegación superior incluye accesos directos a las principales secciones de la página:

- Inicio
- Tecnología
- Beneficios
- Sectores
- Nosotros
- Planes
- Contacto

Asimismo, se implementan llamadas a la acción visibles orientadas a incentivar la interacción del usuario, tales como:

- “Solicitar información”
- “Conocer más”
- “Ver planes”

La navegación entre secciones se realiza mediante desplazamiento continuo dentro de la misma página, permitiendo una experiencia fluida y evitando interrupciones innecesarias durante la exploración del contenido.

**Navegación en la Web Application**

La navegación dentro de la aplicación web se adapta según las necesidades de los dos segmentos principales de usuarios: personal operativo de almacenes farmacéuticos y entidades de salud o gestores farmacéuticos.

Para el personal operativo de almacenes farmacéuticos, se considera un menú lateral fijo con las siguientes opciones principales:

- Dashboard
- Monitoreo en tiempo real
- Alertas
- Historial de registros
- Reportes
- Configuración

Además, se incorporan botones de acceso inmediato para acciones frecuentes como:

- Revisar alertas críticas.
- Visualizar condiciones actuales.
- Consultar historial reciente.

Para las entidades de salud y gestores farmacéuticos, se utiliza un menú lateral de supervisión centralizada con opciones como:

- Dashboard general
- Gestión de sedes
- Reportes históricos
- Alertas globales
- Usuarios
- Configuración institucional

El sistema permite alternar rápidamente entre diferentes almacenes o sedes monitoreadas mediante filtros y paneles de selección.

Asimismo, las entidades pueden acceder a vistas generales que resumen el estado ambiental de múltiples almacenes en tiempo real, facilitando la supervisión integral.

**Interacción con el sistema**

La navegación utiliza etiquetas claras, iconografía comprensible y estructuras visuales organizadas para facilitar el uso de la plataforma por distintos perfiles de usuario.

También se integran filtros rápidos y barras de búsqueda para localizar sedes, alertas, registros o reportes específicos de manera eficiente.

Finalmente, la plataforma incorpora secciones de asistencia y orientación para apoyar al usuario en la comprensión de las funcionalidades principales del sistema y reducir la dificultad de adopción tecnológica.

## 4.3. Landing Page UI Design

El diseño de la interfaz de usuario de la Landing Page de KairoLabs tiene como propósito comunicar de manera clara la propuesta de valor del producto: el monitoreo de las condiciones ambientales asociadas al almacenamiento de medicamentos.

La propuesta traduce los lineamientos definidos previamente en los Style Guidelines y en la Information Architecture hacia una experiencia visual estructurada, comprensible y orientada a los segmentos objetivo.

La Landing Page organiza la información mediante una secuencia progresiva de contenidos que permite al visitante comprender qué problema aborda KairoLabs, cómo funciona la solución, qué tecnología utiliza, a qué sectores se dirige y cuáles son las alternativas disponibles para acceder al producto.

---

### 4.3.1. Landing Page Wireframe

El wireframe de la Landing Page de KairoLabs define la estructura base de la experiencia de entrada al producto. Su propósito es organizar la información de manera progresiva, permitiendo que el visitante comprenda la propuesta de valor, identifique los segmentos atendidos y encuentre rutas claras hacia el registro, contacto o exploración de planes.

El diseño se plantea como una secuencia de bloques independientes conectados por una narrativa común: presentar el problema de conservación de medicamentos, explicar las capacidades tecnológicas de la solución, reforzar la confianza institucional y guiar al usuario hacia una acción concreta.

Esta distribución facilita la lectura y permite validar la jerarquía de contenidos antes de aplicar la identidad visual final.

**Landing / Hero**

La sección inicial concentra los elementos de mayor prioridad para la primera impresión del usuario. Incluye una barra de navegación con accesos a las secciones principales, un espacio destinado al logotipo, selector de idioma y una llamada a la acción visible.

El área Hero presenta el mensaje principal de la propuesta de valor: alertas en tiempo real para hospitales, farmacias y distribución. El wireframe reserva un bloque visual amplio para reforzar el contexto del producto y acompaña el mensaje con información relacionada con temperatura, humedad, luz, merma, trazabilidad y cumplimiento.

<p align="center">
  <img src="../assets/landing-wireframe-hero.png" alt="Wireframe Landing Hero KairoLabs" width="700"><br>
  <em>Nota: Wireframe de la sección inicial y Hero de la Landing Page de KairoLabs.</em>
</p>

**Nosotros / Proyecto**

Esta sección funciona como bloque de credibilidad y explicación institucional. El wireframe organiza la información mediante una columna de tarjetas para misión, visión, equipo académico y verificación continua, junto con un bloque principal donde se resume el enfoque del proyecto.

La disposición permite presentar a KairoLabs como una solución tecnológica respaldada por un equipo, un propósito y un proceso de desarrollo.

<p align="center">
  <img src="../assets/landing-wireframe-nosotros.png" alt="Wireframe Nosotros Proyecto KairoLabs" width="700"><br>
  <em>Nota: Wireframe de la sección Nosotros de la Landing Page de KairoLabs.</em>
</p>

**Tecnología Inteligente**

El bloque de tecnología presenta las principales capacidades del sistema IoT en formato de tarjetas. La estructura permite identificar funciones relacionadas con temperatura, humedad, iluminación, conectividad, alertas, trazabilidad y operación multi-sede.

El uso de tarjetas facilita el escaneo visual y permite separar cada capacidad sin sobrecargar la interfaz.

<p align="center">
  <img src="../assets/landing-wireframe-tecnologia-inteligente.png" alt="Wireframe Tecnologia Inteligente KairoLabs" width="700"><br>
  <em>Nota: Wireframe de la sección Tecnología Inteligente de KairoLabs.</em>
</p>

**Sectores Objetivo**

Esta sección organiza la solución considerando los principales públicos identificados para el producto: personal operativo de almacenes y gestores responsables de farmacia.

Para el personal operativo se priorizan funciones relacionadas con monitoreo y alertas, mientras que para los gestores se destaca la supervisión de sedes y la consulta de información consolidada.

<p align="center">
  <img src="../assets/landing-wireframe-sector-objetivo.png" alt="Wireframe Sectores Objetivo KairoLabs" width="700"><br>
  <em>Nota: Wireframe de la sección Sectores Objetivo de KairoLabs.</em>
</p>

**Equipo**

El bloque de equipo se organiza mediante tarjetas destinadas a presentar a los integrantes responsables del proyecto.

Esta sección aporta confianza al visitante y permite identificar a las personas vinculadas con el desarrollo de KairoLabs.

<p align="center">
  <img src="../assets/landing-wireframe-equipo.png" alt="Wireframe Equipo KairoLabs" width="700"><br>
  <em>Nota: Wireframe de la sección Equipo de KairoLabs.</em>
</p>

**Planes**

La sección de planes organiza la oferta del producto mediante tarjetas de suscripción.

El wireframe contempla las alternativas Piloto, Básico, Profesional, Hospitalario y Premium, permitiendo comparar precios, características y llamadas a la acción.

<p align="center">
  <img src="../assets/landing-wireframe-planes.png" alt="Wireframe Planes KairoLabs" width="700"><br>
  <em>Nota: Wireframe de la sección Planes de KairoLabs.</em>
</p>

**CTA Final / Footer**

El cierre de la Landing Page combina una llamada a la acción con el footer institucional.

El footer agrupa accesos rápidos a las secciones principales, enlaces de navegación secundaria y elementos institucionales.

<p align="center">
  <img src="../assets/landing-wireframe-footer.png" alt="Wireframe Footer KairoLabs" width="700"><br>
  <em>Nota: Wireframe del CTA final y footer de KairoLabs.</em>
</p>

En conjunto, estos wireframes permiten validar la arquitectura de información de la Landing Page antes de desarrollar la propuesta visual definitiva.

---

### 4.3.2. Landing Page Mock-up

Los mock-ups de la Landing Page de KairoLabs representan la versión de alta fidelidad del diseño, incorporando la identidad visual final del producto, la paleta cromática, la jerarquía tipográfica, los componentes de interfaz y los elementos gráficos definidos previamente.

A diferencia del wireframe, que se centra principalmente en estructura y distribución, el mock-up permite validar la experiencia visual completa.

La propuesta utiliza una composición limpia, con predominio de tonos azul oscuro y fondos claros, complementados por acentos naranjas para destacar acciones principales y elementos relevantes.

**Landing / Hero**

El mock-up del Hero presenta la primera experiencia visual del usuario con KairoLabs. La navegación superior integra el logotipo, accesos principales, selector de idioma y botón de acceso.

<p align="center">
  <img src="../assets/landing-mockup-hero.png" alt="Mockup Landing Hero KairoLabs" width="700"><br>
  <em>Nota: Mock-up del Hero de la Landing Page de KairoLabs.</em>
</p>

**Nosotros / Proyecto**

La sección consolida la presentación institucional del proyecto mediante tarjetas que organizan información relacionada con misión, visión, equipo académico y verificación continua.

<p align="center">
  <img src="../assets/landing-mockup-nosotros.png" alt="Mockup Nosotros Proyecto KairoLabs" width="700"><br>
  <em>Nota: Mock-up de la sección Nosotros de KairoLabs.</em>
</p>

**Tecnología Inteligente**

El mock-up de tecnología presenta las capacidades del sistema IoT mediante tarjetas visuales de fácil lectura.

<p align="center">
  <img src="../assets/landing-mockup-tecnologia.png" alt="Mockup Tecnologia Inteligente KairoLabs" width="700"><br>
  <em>Nota: Mock-up de la sección Tecnología Inteligente de KairoLabs.</em>
</p>

**Sectores Objetivo**

La sección presenta los principales perfiles atendidos por la solución, diferenciando visualmente las necesidades operativas y de gestión.

<p align="center">
  <img src="../assets/landing-mockup-sectores-objetivo.png" alt="Mockup Sectores Objetivo KairoLabs" width="700"><br>
  <em>Nota: Mock-up de la sección Sectores Objetivo de KairoLabs.</em>
</p>

**Planes**

El mock-up de planes organiza la oferta comercial mediante tarjetas comparables correspondientes a Piloto, Básico, Profesional, Hospitalario y Premium.

<p align="center">
  <img src="../assets/landing-mockup-planes.png" alt="Mockup Planes KairoLabs" width="700"><br>
  <em>Nota: Mock-up de la sección Planes de KairoLabs.</em>
</p>

**CTA Final / Footer**

El cierre de la Landing Page combina una llamada a la acción final con el footer institucional.

<p align="center">
  <img src="../assets/landing-mockup-footer.png" alt="Mockup Footer KairoLabs" width="700"><br>
  <em>Nota: Mock-up del CTA final y footer de KairoLabs.</em>
</p>

En conjunto, los mock-ups permiten comprobar cómo la estructura definida en los wireframes se transforma en una interfaz visual consistente con el Design System de KairoLabs.

---

## 4.4. Mobile Applications UX/UI Design

Esta sección presenta la propuesta de experiencia de usuario e interfaz correspondiente a la aplicación móvil nativa de KairoLabs.

La experiencia móvil debe mantener consistencia con los Style Guidelines y con la arquitectura de información establecidos previamente, adaptando la organización de los contenidos al espacio y patrones de interacción de dispositivos móviles.

En el material actual proporcionado para el capítulo no se encuentran todavía incorporados los artefactos gráficos correspondientes a la Mobile Application. Por ello, las siguientes subsecciones deberán completarse con los wireframes, wireflows, mock-ups y user flows desarrollados específicamente para la aplicación móvil.

### 4.4.1. Mobile Applications Wireframes

En esta sección se deben presentar y explicar los wireframes correspondientes a las principales vistas de la Mobile Application de KairoLabs.

Los wireframes deberán representar la estructura y distribución funcional de las pantallas antes de aplicar los elementos visuales finales del Design System.

**Pendiente:** incorporar los wireframes correspondientes a la aplicación móvil.

---

### 4.4.2. Mobile Applications Wireflow Diagrams

En esta sección se deberán presentar los Wireflow Diagrams de la Mobile Application.

Cada wireflow deberá representar el recorrido de un User Goal y mostrar cómo las diferentes pantallas se relacionan a medida que el usuario realiza acciones dentro de la aplicación.

**Pendiente:** incorporar los Wireflow Diagrams correspondientes a la Mobile Application.

---

### 4.4.3. Mobile Applications Mock-ups

En esta sección se deberán presentar los mock-ups de alta fidelidad correspondientes a la Mobile Application de KairoLabs.

Los mock-ups deberán aplicar la tipografía, paleta cromática, componentes, estados e iconografía definidos en los Style Guidelines.

**Pendiente:** incorporar los mock-ups correspondientes a la Mobile Application.

---

### 4.4.4. Mobile Applications User Flow Diagrams

En esta sección se deberán presentar los User Flow Diagrams correspondientes a las tareas principales realizadas dentro de la Mobile Application.

Los diagramas deberán mantener consistencia con los Wireflow Diagrams y representar tanto los recorridos esperados como las posibles rutas alternativas.

**Pendiente:** incorporar los User Flow Diagrams correspondientes a la Mobile Application.

---

## 4.5. Mobile Applications Prototyping

Esta sección debe presentar los prototipos interactivos desarrollados para la Mobile Application de KairoLabs.

Los prototipos deberán permitir comprobar los principales recorridos de navegación definidos previamente mediante los User Flow Diagrams.

En el material actual del capítulo todavía no se encuentra incorporado el prototipo correspondiente a la Mobile Application.

---

### 4.5.1. Android Mobile Applications Prototyping

En esta sección se deberá presentar el prototipo interactivo correspondiente a la versión Android de KairoLabs, incluyendo evidencia visual y el enlace correspondiente al prototipo.

**Pendiente:** incorporar evidencia y enlace del prototipo Android.

---

### 4.5.2. iOS Mobile Applications Prototyping

En esta sección se deberá presentar el prototipo interactivo correspondiente a la versión iOS de KairoLabs, manteniendo consistencia funcional con la propuesta general de la Mobile Application.

**Pendiente:** incorporar evidencia y enlace del prototipo iOS.

---

## 4.6. Web Applications UX/UI Design

Esta sección presenta la propuesta visual y de interacción de la Web Application de KairoLabs.

La aplicación web concentra las funcionalidades administrativas y operativas relacionadas con autenticación, establecimientos, operadores, navegación entre sedes, perfiles y planes.

Las diferentes vistas mantienen consistencia con los Style Guidelines y la Information Architecture definidos previamente.

---

### 4.6.1. Web Applications Wireframes

Los wireframes de la Web Application de KairoLabs definen la estructura funcional de las principales pantallas antes de aplicar el diseño visual final.

La propuesta utiliza un layout administrativo con barra lateral, encabezado superior y área principal de trabajo.

**Login**

La pantalla de Login concentra el acceso inicial al sistema mediante correo electrónico y contraseña.

<p align="center">
  <img src="../assets/web-wireframe-login.png" alt="Wireframe Login Web Application KairoLabs" width="500"><br>
  <em>Nota: Wireframe de la pantalla de Login.</em>
</p>

**Registro**

El wireframe de registro presenta un formulario adaptable según el perfil del usuario.

<p align="center">
  <img src="../assets/web-wireframe-registro.png" alt="Wireframe Registro Web Application KairoLabs" width="500"><br>
  <em>Nota: Wireframe de la pantalla de registro.</em>
</p>

**Inicio**

La pantalla de inicio funciona como Dashboard de entrada luego de la autenticación.

<p align="center">
  <img src="../assets/web-wireframe-inicio.png" alt="Wireframe Inicio Web Application KairoLabs" width="700"><br>
  <em>Nota: Wireframe del Dashboard inicial.</em>
</p>

**Establecimientos**

El módulo organiza la información correspondiente a las sedes registradas y permite realizar búsquedas por nombre o ciudad.

<p align="center">
  <img src="../assets/web-wireframe-establecimientos.png" alt="Wireframe Establecimientos Web Application KairoLabs" width="700"><br>
  <em>Nota: Wireframe del módulo de establecimientos.</em>
</p>

**Asignar Operador**

La pantalla permite relacionar personal operativo con establecimientos específicos.

<p align="center">
  <img src="../assets/web-wireframe-asignar-operador.png" alt="Wireframe Asignar Operador Web Application KairoLabs" width="700"><br>
  <em>Nota: Wireframe de asignación de operadores.</em>
</p>

**Agregar Establecimiento**

La pantalla permite registrar nuevos establecimientos dentro de la plataforma.

<p align="center">
  <img src="../assets/web-wireframe-agregar-establecimiento.png" alt="Wireframe Agregar Establecimiento Web Application KairoLabs" width="700"><br>
  <em>Nota: Wireframe para registrar establecimientos.</em>
</p>

**Mapa de Establecimientos**

La vista ofrece una representación geográfica de las sedes registradas.

<p align="center">
  <img src="../assets/web-wireframe-mapa-establecimientos.png" alt="Wireframe Mapa de Establecimientos Web Application KairoLabs" width="700"><br>
  <em>Nota: Wireframe del mapa de establecimientos.</em>
</p>

**Perfil**

La pantalla reúne los principales datos del usuario o entidad.

<p align="center">
  <img src="../assets/web-wireframe-perfil.png" alt="Wireframe Perfil Web Application KairoLabs" width="700"><br>
  <em>Nota: Wireframe de la pantalla de perfil.</em>
</p>

**Planes y Billing**

La sección permite seleccionar un plan y gestionar la información correspondiente a la suscripción.

<p align="center">
  <img src="../assets/web-wireframe-planes-billing.png" alt="Wireframe Planes y Billing Web Application KairoLabs" width="700"><br>
  <em>Nota: Wireframe del proceso de planes y suscripción.</em>
</p>

**Elige un plan**

La pantalla presenta las diferentes opciones de suscripción disponibles.

<p align="center">
  <img src="../assets/web-wireframe-elige-plan.png" alt="Wireframe Elige un Plan Web Application KairoLabs" width="700"><br>
  <em>Nota: Wireframe de selección de plan.</em>
</p>

En conjunto, los wireframes permiten validar la estructura funcional de la aplicación antes de desarrollar los mock-ups finales.

---

### 4.6.2. Web Applications Wireflow Diagrams

Los Wireflow Diagrams de la Web Application de KairoLabs permiten visualizar la relación entre pantallas, acciones y rutas de navegación.

El recorrido principal comienza con el Login o registro y continúa hacia el Dashboard y los módulos principales.

El diagrama permite comprobar que las pantallas no funcionan como vistas aisladas, sino como partes de un flujo de interacción conectado.

<p align="center">
  <img src="../assets/web-application-wireflow.png" alt="Wireflow de la Web Application de KairoLabs" width="700"><br>
  <em>Nota: Wireflow principal de la Web Application de KairoLabs.</em>
</p>

El wireflow permite validar que los procesos de autenticación, registro, suscripción, perfil y navegación entre módulos se encuentren conectados de forma coherente.

---

### 4.6.3. Web Applications Mock-ups

Los mock-ups de la Web Application representan la versión visual de alta fidelidad de las principales pantallas de KairoLabs.

La propuesta mantiene consistencia con la Landing Page mediante fondos claros, paneles blancos, navegación lateral, acentos naranjas y elementos azul oscuro.

**Login**

<p align="center">
  <img src="../assets/web-mockup-login.png" alt="Mockup Login Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up de Login.</em>
</p>

**Registro**

<p align="center">
  <img src="../assets/web-mockup-registro.png" alt="Mockup Registro Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up de registro.</em>
</p>

**Inicio Dashboard**

<p align="center">
  <img src="../assets/web-mockup-inicio.png" alt="Mockup Inicio Dashboard Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up del Dashboard.</em>
</p>

**Ver Establecimientos**

<p align="center">
  <img src="../assets/web-mockup-ver-establecimientos.png" alt="Mockup Ver Establecimientos Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up de establecimientos.</em>
</p>

**Agregar Establecimiento**

<p align="center">
  <img src="../assets/web-mockup-agregar-establecimiento.png" alt="Mockup Agregar Establecimiento Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up de registro de establecimientos.</em>
</p>

**Asignar Operador**

<p align="center">
  <img src="../assets/web-mockup-asignar-operador.png" alt="Mockup Asignar Operador Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up de asignación de operador.</em>
</p>

**Mapa de Establecimientos**

<p align="center">
  <img src="../assets/web-mockup-mapa-establecimientos.png" alt="Mockup Mapa de Establecimientos Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up del mapa de establecimientos.</em>
</p>

**Elige un Plan**

<p align="center">
  <img src="../assets/web-mockup-elige-plan.png" alt="Mockup Elige un Plan Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up de selección de plan.</em>
</p>

**Perfil de Usuario**

<p align="center">
  <img src="../assets/web-mockup-perfil.png" alt="Mockup Perfil Usuario Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up del perfil de usuario.</em>
</p>

**Edición de Perfil**

<p align="center">
  <img src="../assets/web-mockup-edicion-perfil.png" alt="Mockup Edicion de Perfil Web Application KairoLabs" width="700"><br>
  <em>Nota: Mock-up de edición de perfil.</em>
</p>

En conjunto, estos mock-ups consolidan la experiencia visual de la Web Application de KairoLabs.

---

### 4.6.4. Web Applications User Flow Diagrams

Los User Flow Diagrams representan los principales recorridos que realizan los usuarios dentro de la Web Application.

Cada flujo permite visualizar las decisiones, rutas principales y posibles alternativas relacionadas con los objetivos de los usuarios.

**User Flow – Autenticación, registro, planes y Dashboard**

El flujo representa el acceso inicial a la plataforma, diferenciando entre usuarios registrados y nuevos usuarios.

<p align="center">
  <img src="../assets/web-userflow-autenticacion.png" alt="User Flow Autenticacion Registro Planes y Dashboard KairoLabs" width="700"><br>
  <em>Nota: User Flow de autenticación y acceso al Dashboard.</em>
</p>

**User Flow – Dashboard y navegación principal**

Representa el acceso desde el Dashboard hacia los diferentes módulos de la aplicación.

<p align="center">
  <img src="../assets/web-userflow-dashboard.png" alt="User Flow Dashboard y Navegacion Principal KairoLabs" width="700"><br>
  <em>Nota: User Flow de navegación principal.</em>
</p>

**User Flow – Gestión de establecimientos**

Representa el proceso de consulta, búsqueda, registro y ubicación de establecimientos.

<p align="center">
  <img src="../assets/web-userflow-gestion-establecimientos.png" alt="User Flow Gestion de Establecimientos KairoLabs" width="700"><br>
  <em>Nota: User Flow de gestión de establecimientos.</em>
</p>

**User Flow – Asignación de operador**

Representa el proceso mediante el cual un gestor asigna un operador a una sede.

<p align="center">
  <img src="../assets/web-userflow-asignacion-operador.png" alt="User Flow Asignacion de Operador KairoLabs" width="700"><br>
  <em>Nota: User Flow de asignación de operadores.</em>
</p>

**User Flow – Perfil, planes y suscripción**

Representa las acciones relacionadas con la edición del perfil y actualización del plan.

<p align="center">
  <img src="../assets/web-userflow-perfil.png" alt="User Flow Perfil Planes y Suscripcion KairoLabs" width="700"><br>
  <em>Nota: User Flow de perfil y planes.</em>
</p>

**User Flow – Monitoreo operativo desde Dashboard**

Representa la navegación entre el Dashboard, establecimientos y mapa.

<p align="center">
  <img src="../assets/web-userflow-monitoreo-operativo.png" alt="User Flow Monitoreo Operativo KairoLabs" width="700"><br>
  <em>Nota: User Flow de monitoreo operativo.</em>
</p>

En conjunto, los User Flow Diagrams permiten comprobar que las tareas principales poseen recorridos definidos dentro de la aplicación.

---

## 4.7. Web Applications Prototyping

En esta etapa se desarrolló el prototipo interactivo de la Web Application de KairoLabs en Figma.

El prototipo conecta las pantallas principales dentro de un flujo continuo que permite evaluar la navegación desde el acceso inicial hasta las principales funciones administrativas.

El recorrido incluye:

- Login.
- Registro.
- Dashboard.
- Gestión de establecimientos.
- Asignación de operadores.
- Mapa.
- Selección de plan.
- Perfil.
- Edición de perfil.

<p align="center">
  <img src="../assets/web-application-prototype.png" alt="Prototipo interactivo Web Application KairoLabs" width="700"><br>
  <em>Nota: Vista general del prototipo interactivo de la Web Application.</em>
</p>

El prototipo permite revisar la continuidad entre mock-ups y comprobar que las acciones principales mantengan una ruta clara dentro de la aplicación.

> [Ver prototipo interactivo en Figma](https://www.figma.com/proto/fFGcLQGnLVFJOYDHAIwktD/Untitled?node-id=49-17&t=BzflcHXXl3OzPg6e-0&scaling=contain&content-scaling=fixed&page-id=3%3A2&starting-point-node-id=49%3A17)

---

## 4.8. Domain-Driven Software Architecture

La arquitectura de software de KairoLabs se plantea a partir del dominio identificado durante el análisis del producto.

La propuesta busca organizar las responsabilidades del sistema de manera coherente con conceptos como identidad, establecimientos, operadores, dispositivos, monitoreo, transportes y suscripciones.

Los diagramas presentados a continuación permiten analizar la arquitectura en distintos niveles de abstracción, comenzando con la relación general entre usuarios y sistemas externos, continuando con los contenedores principales y finalizando con los componentes internos.

---

### 4.8.1. Software Architecture Context Diagram

El diagrama de contexto presenta a KairoLabs como sistema central y muestra su relación con los principales actores y elementos externos.

Entre ellos se consideran el personal operativo, los gestores farmacéuticos y los dispositivos IoT responsables de proporcionar información de monitoreo.

<p align="center">
  <img src="../assets/Context-Diagram.png" alt="Software Architecture Context Diagram KairoLabs" width="700"><br>
  <em>Nota: Diagrama de contexto de KairoLabs.</em>
</p>

---

### 4.8.2. Software Architecture Container Diagrams

El diagrama de contenedores muestra las principales unidades ejecutables que conforman KairoLabs y la forma en que se comunican.

La propuesta actual considera una Web Application para la interacción con los usuarios, una API Application que centraliza la lógica del sistema y la persistencia de información.

<p align="center">
  <img src="../assets/Container-Diagram.png" alt="Software Architecture Container Diagram KairoLabs" width="700"><br>
  <em>Nota: Diagrama de contenedores de KairoLabs.</em>
</p>

---

### 4.8.3. Software Architecture Components Diagrams

El diagrama de componentes permite observar con mayor detalle la estructura interna de la API Application de KairoLabs.

En este nivel se representan los componentes encargados de autenticación, monitoreo, procesamiento de información y persistencia de datos, así como las relaciones internas necesarias para atender las solicitudes provenientes de las aplicaciones cliente.

<p align="center">
  <img src="../assets/Component-Diagram.png" alt="Software Architecture Components Diagram KairoLabs" width="700"><br>
  <em>Nota: Diagrama de componentes de KairoLabs.</em>
</p>

---

## 4.9. Software Object-Oriented Design

El diseño orientado a objetos de KairoLabs representa las principales entidades del dominio y sus relaciones.

Este modelo permite trasladar los conceptos identificados durante el análisis hacia una estructura que pueda ser utilizada como referencia durante la implementación del software.

---

### 4.9.1. Class Diagrams

El diagrama de clases de KairoLabs representa las clases principales, sus atributos, operaciones y relaciones.

Entre las principales clases representadas se encuentran Users, Operators, Admins, Establishments, Devices, Transports y Subscriptions.

<p align="center">
  <img src="../assets/kairolabs-class-diagram.jpg" alt="Class Diagram de KairoLabs" width="700"><br>
  <em>Nota: Diagrama de clases de KairoLabs.</em>
</p>

**Users**

Representa la información común asociada con los usuarios del sistema.

**Operators**

Representa al personal operativo asociado con establecimientos y encargado de interactuar con las funcionalidades relacionadas con supervisión y atención de alertas.

**Admins**

Representa a los gestores responsables de administrar establecimientos y suscripciones.

**Establishments**

Representa los establecimientos o sedes registradas dentro de KairoLabs y concentra información relacionada con ubicación y organización de dispositivos.

**Devices**

Representa los dispositivos utilizados para obtener información relacionada con las condiciones ambientales.

**Transports**

Representa los elementos asociados con el monitoreo durante los procesos de transporte.

**Subscriptions**

Representa la información correspondiente a los planes o suscripciones asociadas con las cuentas administrativas.

Las relaciones existentes entre estas clases permiten representar la organización funcional del sistema y servir como base para la definición posterior del modelo de datos.

---

### 4.9.2. Class Dictionary

El Class Dictionary complementa el diagrama de clases mediante una descripción resumida de las responsabilidades de cada clase principal del sistema.

| Clase | Responsabilidad |
| :--- | :--- |
| **Users** | Gestionar la información general de identidad y acceso de los usuarios. |
| **Operators** | Representar al personal operativo asociado con establecimientos. |
| **Admins** | Representar a los gestores responsables de la administración institucional. |
| **Establishments** | Representar las sedes o establecimientos registrados en la plataforma. |
| **Devices** | Representar los dispositivos utilizados para obtener información ambiental. |
| **Transports** | Representar los elementos relacionados con el monitoreo durante transporte. |
| **Subscriptions** | Representar la información relacionada con planes y suscripciones. |

El diccionario permite comprender de manera rápida la responsabilidad que cumple cada clase dentro del modelo orientado a objetos.

---

## 4.10. Database Design

El diseño de base de datos de KairoLabs representa la estructura utilizada para persistir la información correspondiente a usuarios, establecimientos, operadores, dispositivos, transportes y suscripciones.

El modelo busca mantener relaciones consistentes entre las principales entidades identificadas en el dominio y proporcionar soporte a las funcionalidades definidas para la plataforma.

---

### 4.10.1. Relational/Non-Relational Database Diagram

KairoLabs utiliza un modelo relacional para representar las principales entidades y relaciones de información del sistema.

Entre las tablas principales representadas se encuentran:

- `users`
- `admins`
- `operators`
- `establishments`
- `devices`
- `transports`
- `subscriptions`

<p align="center">
  <img src="../assets/kairolabs-database-diagram.png" alt="Relational Database Diagram de KairoLabs" width="700"><br>
  <em>Nota: Diagrama relacional de base de datos de KairoLabs.</em>
</p>

La tabla `users` concentra la información general relacionada con las cuentas del sistema.

Las tablas `admins` y `operators` permiten representar los perfiles específicos utilizados dentro de la plataforma.

La tabla `establishments` almacena la información correspondiente a las sedes registradas y funciona como elemento de relación para diferentes recursos operativos.

Las tablas `devices` y `transports` contienen información asociada con los elementos utilizados para el monitoreo de condiciones ambientales.

Finalmente, la tabla `subscriptions` almacena la información correspondiente a los planes asociados con los administradores.

Las relaciones definidas mediante claves permiten mantener consistencia entre las diferentes entidades y facilitar la consulta de información asociada con usuarios, sedes, dispositivos y demás elementos de KairoLabs.
