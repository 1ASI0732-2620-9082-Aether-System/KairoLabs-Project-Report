# Capítulo V: Product Implementation

En este capítulo se presenta el proceso de implementación y despliegue de los productos digitales que conforman KairoLabs. Se documentan las decisiones relacionadas con la configuración del entorno de desarrollo, el control de versiones, las convenciones de código y la configuración utilizada para desplegar los diferentes componentes de la solución.

Asimismo, se presentan las evidencias correspondientes al desarrollo incremental del producto durante cuatro Sprints, considerando la Landing Page, la Frontend Web Application y los Web Services RESTful. Cada incremento se encuentra respaldado mediante registros de desarrollo, evidencias visuales, repositorios, despliegues y resultados obtenidos durante el ciclo de implementación.

La solución se encuentra organizada en diferentes productos de software que trabajan en conjunto: una Landing Page orientada a comunicar la propuesta de valor de KairoLabs, una Web Application desarrollada para soportar la operación de los usuarios y una RESTful API encargada de gestionar la lógica de negocio y persistencia de información.

---

## 5.1. Software Configuration Management

La Gestión de Configuración de Software permite mantener organizados y controlados los diferentes artefactos que forman parte de KairoLabs durante su ciclo de desarrollo.

En el proyecto se utilizan herramientas de gestión, diseño, desarrollo, documentación, control de versiones y despliegue que permiten mantener trazabilidad entre los cambios realizados por los integrantes del equipo.

Las decisiones de configuración buscan asegurar que todos los miembros utilicen entornos y convenciones compatibles, reduciendo problemas durante la integración de funcionalidades y facilitando la evolución de los diferentes productos digitales.

---

### 5.1.1. Software Development Environment Configuration

A continuación, se describen los principales productos de software empleados durante el desarrollo de KairoLabs. Las herramientas se organizan de acuerdo con la actividad del ciclo de vida en la cual son utilizadas.

**Project Management**

**Trello**

Trello se utiliza como herramienta principal para organizar las actividades correspondientes a los diferentes Sprints. Mediante tableros se distribuyen las User Stories y Work Items según estados como pendiente, en proceso, revisión y terminado.

Esta herramienta permite mantener visibilidad sobre el avance del equipo y facilita la asignación de actividades entre los integrantes.

Referencia: https://trello.com/

**Google Meet**

Google Meet se utiliza para realizar reuniones de coordinación, Sprint Planning, revisiones de avance y otras sesiones que requieren comunicación sincrónica entre los integrantes.

Referencia: https://meet.google.com/

---

**Requirements Management**

**Google Docs**

Google Docs se emplea como herramienta complementaria para redactar, revisar y coordinar información relacionada con requisitos y documentación antes de consolidarla dentro del Project Report.

Su capacidad de edición colaborativa permite que diferentes integrantes puedan realizar observaciones y modificaciones durante el proceso.

Referencia: https://docs.google.com/

**UXPressia**

UXPressia se utiliza para representar artefactos relacionados con investigación y experiencia de usuario, entre ellos User Personas, Journey Maps, Empathy Maps e Impact Mapping.

Referencia: https://uxpressia.com/

---

**Product UX/UI Design**

**Figma**

Figma se emplea para elaborar wireframes, mock-ups y prototipos interactivos de la Landing Page y Web Application.

La herramienta facilita el diseño colaborativo y permite validar la distribución visual de las interfaces antes de iniciar su implementación.

Referencia: https://www.figma.com/

**Miro**

Miro se utiliza como pizarra colaborativa para la construcción y organización de artefactos asociados con el dominio y la arquitectura del proyecto.

Dentro de KairoLabs fue utilizado para actividades relacionadas con EventStorming y la identificación de elementos del dominio.

Referencia: https://miro.com/

**Lucidchart**

Lucidchart se emplea para la creación de diagramas como Wireflows, User Flows, diagramas UML y Database Diagrams.

Referencia: https://www.lucidchart.com/

---

**Software Development**

**Visual Studio Code**

Visual Studio Code se utiliza como editor para el desarrollo y mantenimiento de diferentes artefactos del proyecto.

Permite trabajar con tecnologías como HTML5, CSS3, JavaScript, Vue.js y archivos Markdown.

Referencia: https://code.visualstudio.com/

**HTML5, CSS3 y JavaScript**

Estas tecnologías se utilizan principalmente en la implementación de la Landing Page.

HTML5 define la estructura semántica del contenido, CSS3 controla la presentación visual y JavaScript permite incorporar interacciones dinámicas.

**Vue.js 3**

Vue.js 3 se utiliza como framework principal para la construcción de la Frontend Web Application de KairoLabs.

Su arquitectura basada en componentes permite reutilizar elementos de interfaz y mantener una estructura organizada.

Referencia: https://vuejs.org/

**PrimeVue**

PrimeVue se utiliza como biblioteca de componentes para complementar la Web Application desarrollada con Vue.js.

Referencia: https://primevue.org/

**Vue Router**

Vue Router permite administrar las diferentes rutas y vistas que conforman la Web Application.

**Pinia**

Pinia se utiliza para gestionar el estado global de la aplicación frontend.

**Axios**

Axios facilita la comunicación entre la Web Application y los servicios proporcionados por la RESTful API.

**vue-i18n**

La aplicación incorpora vue-i18n para ofrecer soporte de internacionalización en español e inglés.

**ASP.NET Core**

ASP.NET Core se utiliza para implementar los Web Services RESTful que soportan la lógica de negocio de KairoLabs.

Referencia: https://dotnet.microsoft.com/apps/aspnet

**C#**

C# es el lenguaje principal empleado para implementar el backend de la solución.

Referencia: https://dotnet.microsoft.com/languages/csharp

**Entity Framework Core**

Entity Framework Core permite gestionar el acceso a datos desde los servicios desarrollados en ASP.NET Core.

Referencia: https://learn.microsoft.com/ef/core/

**PostgreSQL**

PostgreSQL se utiliza como sistema gestor de base de datos relacional para almacenar la información utilizada por KairoLabs.

La instancia utilizada por el backend se encuentra alojada mediante Filess.io.

**Git**

Git se utiliza como sistema distribuido de control de versiones para registrar y administrar los cambios realizados en el código fuente.

Referencia: https://git-scm.com/

**GitHub**

GitHub funciona como plataforma central para alojar los repositorios del proyecto y coordinar el trabajo mediante ramas, commits y merges.

Referencia: https://github.com/

---

**Software Deployment**

**Vercel**

Vercel se utiliza para desplegar la Landing Page y la Frontend Web Application.

Los proyectos se encuentran vinculados con sus respectivos repositorios de GitHub, permitiendo actualizar automáticamente los despliegues cuando se incorporan cambios a las ramas configuradas.

Referencia: https://vercel.com/

**Render**

Render se utiliza para desplegar la RESTful API desarrollada con ASP.NET Core.

El servicio mantiene el backend disponible públicamente y permite configurar variables de entorno necesarias para establecer la conexión con la base de datos.

Referencia: https://render.com/

**Filess.io**

Filess.io se utiliza para alojar la base de datos PostgreSQL utilizada por el backend de KairoLabs.

Las credenciales necesarias para establecer la conexión se configuran mediante variables de entorno en Render.

---

**Software Documentation**

**Swagger / OpenAPI**

Swagger se utiliza para generar la documentación interactiva de los Web Services RESTful.

Permite visualizar las operaciones disponibles, métodos HTTP, rutas, parámetros y estructuras de request y response.

Referencia: https://swagger.io/

**Markdown**

Markdown se utiliza para desarrollar el Project Report dentro del repositorio de documentación del proyecto.

Este formato permite mantener la documentación bajo control de versiones y facilitar su posterior exportación.

Referencia: https://www.markdownguide.org/

---

### 5.1.2. Source Code Management

En esta sección se establece el medio y esquema de organización utilizado por el equipo para realizar el seguimiento y control de las modificaciones efectuadas sobre el código fuente de KairoLabs. Para ello, se utiliza **GitHub** como plataforma de control de versiones y repositorio colaborativo.

La organización pública utilizada por el proyecto es:

`1ASI0732-2610-9082-TBL-KairoLabs`

Asimismo, el equipo aplica **GitFlow** como workflow de control de versiones, **Conventional Commits** para la escritura de mensajes de commit y **Semantic Versioning** para identificar las diferentes versiones liberadas de los productos.

Los productos que conforman KairoLabs se encuentran distribuidos en repositorios independientes, permitiendo mantener una separación clara entre documentación, Landing Page, Frontend Web Application y Web Services.

| Producto | Repositorio |
| :--- | :--- |
| **Project Report** | https://github.com/1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Project-Report.git |
| **Landing Page** | https://github.com/1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Landing-Page.git |
| **Frontend Web Application** | https://github.com/1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Frontend.git |
| **Web Services** | https://github.com/1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Backend.git |

**Project Report**

El repositorio `KairoLabs-Project-Report` contiene la documentación académica y técnica del proyecto. En este repositorio se mantiene el informe elaborado en Markdown, junto con las imágenes, diagramas, evidencias de implementación y demás recursos utilizados durante el ciclo de vida del producto.

**Landing Page**

El repositorio `KairoLabs-Landing-Page` contiene la implementación del sitio web público utilizado para presentar la propuesta de valor de KairoLabs. Incluye la estructura HTML, estilos CSS, scripts JavaScript y recursos multimedia correspondientes a las diferentes secciones de la página.

**Frontend Web Application**

El repositorio `KairoLabs-Frontend` contiene la implementación de la aplicación web desarrollada con Vue.js. En este repositorio se organizan las vistas, componentes, rutas, servicios, gestión de estado y lógica de interacción de la plataforma.

**Web Services**

El repositorio `KairoLabs-Backend` contiene la RESTful API implementada mediante ASP.NET Core y C#. Incluye la lógica de negocio, acceso a datos, autenticación, persistencia y los endpoints correspondientes a los diferentes Bounded Contexts de KairoLabs.

**GitFlow Workflow**

El equipo utiliza GitFlow como estrategia para organizar el desarrollo colaborativo. Este flujo permite mantener separadas las funcionalidades en desarrollo de las versiones estables del producto, facilitando la integración progresiva de cambios.

Las ramas principales utilizadas son:

| Rama | Descripción |
| :--- | :--- |
| **`main`** | Representa la versión estable del producto preparada para producción. |
| **`develop`** | Funciona como rama de integración donde se incorporan las funcionalidades completadas antes de preparar una nueva versión. |

Además, se utilizan ramas de soporte:

| Tipo de rama | Convención | Ejemplo |
| :--- | :--- | :--- |
| **Feature Branch** | `feature/<nombre-descriptivo>` | `feature/login-view` |
| **Release Branch** | `release/<version>` | `release/1.0.0` |
| **Hotfix Branch** | `hotfix/<descripcion>` | `hotfix/login-validation` |

Las ramas `feature/*` se crean a partir de `develop` para implementar funcionalidades específicas sin afectar directamente la rama de integración.

Ejemplos utilizados durante el proyecto:

`feature/login-view`

`feature/profile`

`feature/subscriptions`

`feature/monitoring`

`feature/establishments`

Una vez completada y revisada una funcionalidad, los cambios se integran nuevamente en `develop`.

Las ramas `release/*` se utilizan para preparar una versión antes de integrarla en `main`.

Ejemplo:

`release/1.0.0`

Las ramas `hotfix/*` se utilizan para resolver errores críticos identificados en versiones estables del producto.

Ejemplo:

`hotfix/login-validation`

**Conventional Commits**

Los mensajes de commit siguen la especificación **Conventional Commits**, con el objetivo de mantener un historial de cambios uniforme, comprensible y trazable.

La estructura utilizada es:

`<type>(<scope>): <description>`

Los tipos considerados por el equipo son los siguientes:

| Tipo | Uso |
| :--- | :--- |
| `feat` | Incorporación de una nueva funcionalidad. |
| `fix` | Corrección de errores o comportamientos inesperados. |
| `docs` | Modificaciones relacionadas con documentación. |
| `style` | Cambios de presentación que no alteran la lógica del sistema. |
| `refactor` | Reestructuración del código existente sin modificar su comportamiento externo. |
| `test` | Incorporación o modificación de pruebas. |
| `chore` | Tareas de configuración, mantenimiento o soporte. |

Entre los mensajes registrados durante la evolución del proyecto se encuentran:

`feat(profile): implement user profile management with editing capabilities`

`feat(dashboard): refactor fetchDashboardData to improve error handling`

`feat: connect control center to API and fix transport registration`

`fix: register health entity in single POST /users call`

`refactor(iam): align IAM bounded context with learning-center DDD pattern`

`docs: add Sprint 4 details including planning, backlog, and collaboration insights`

Estas convenciones permiten identificar rápidamente el propósito de cada modificación realizada en los repositorios.

**Semantic Versioning**

Para identificar las diferentes versiones liberadas del producto se utiliza **Semantic Versioning**, empleando la estructura:

`MAJOR.MINOR.PATCH`

Cada componente representa un tipo diferente de modificación:

- **MAJOR:** se incrementa cuando se introducen cambios incompatibles con versiones anteriores.
- **MINOR:** se incrementa cuando se incorporan nuevas funcionalidades manteniendo compatibilidad con la versión actual.
- **PATCH:** se incrementa cuando se realizan correcciones de errores o mejoras menores.

Ejemplos de versiones:

`v1.0.0`

`v1.1.0`

`v1.1.1`

La utilización conjunta de GitHub, GitFlow, Conventional Commits y Semantic Versioning permite mantener trazabilidad sobre la evolución de cada producto, facilita la integración del trabajo realizado por los diferentes integrantes y reduce conflictos durante el desarrollo colaborativo.

### 5.1.3. Source Code Style Guide & Conventions

En este apartado se definen los estándares de codificación y las convenciones adoptadas por el equipo para garantizar la legibilidad, mantenibilidad y consistencia del código fuente de KairoLabs.

Estas convenciones se aplican a los diferentes productos de software desarrollados durante el proyecto, incluyendo la Landing Page, la Frontend Web Application y los Web Services.

Como regla transversal, toda la nomenclatura técnica utilizada en el código fuente se redacta en **inglés**, incluyendo nombres de variables, funciones, métodos, clases, componentes, archivos y comentarios.

**Principios generales**

Las siguientes reglas se aplican de manera transversal a los diferentes lenguajes y tecnologías utilizadas dentro del proyecto:

- Los nombres técnicos deben escribirse en inglés.
- Los nombres de variables, funciones, clases y componentes deben ser descriptivos y representar claramente su responsabilidad.
- Se debe evitar la duplicación innecesaria de código.
- Se prioriza la creación de funciones, componentes y servicios reutilizables.
- Se mantiene una estructura consistente dentro de cada repositorio.
- El código debe mantener una indentación uniforme.
- Los comentarios deben utilizarse únicamente cuando sean necesarios para aclarar una parte de la lógica.
- Se busca mantener las responsabilidades de cada elemento claramente separadas.

**HTML**

HTML5 se utiliza principalmente para definir la estructura de la Landing Page.

Las principales convenciones adoptadas son:

- Utilizar HTML5 como estándar de marcado.
- Mantener etiquetas y atributos escritos en minúsculas.
- Utilizar comillas dobles para los valores de los atributos.
- Priorizar el uso de etiquetas semánticas.
- Incorporar el atributo `alt` en todas las imágenes.
- Declarar `<!DOCTYPE html>` al inicio del documento.
- Mantener una estructura jerárquica clara.
- Evitar el uso excesivo de elementos `<div>` cuando existe una etiqueta semántica adecuada.

Ejemplo:

    <section class="monitoring-section">
        <h2>Environmental Monitoring</h2>
        <img src="sensor.png" alt="Environmental sensor">
    </section>

Las etiquetas semánticas utilizadas incluyen principalmente:

`<header>`

`<nav>`

`<main>`

`<section>`

`<article>`

`<footer>`

Este criterio permite mantener una estructura HTML más comprensible y favorece la accesibilidad de la Landing Page.

**CSS**

CSS se utiliza para controlar la presentación visual de la Landing Page y complementar los estilos de las interfaces web.

Las principales convenciones utilizadas son:

- Mantener una indentación uniforme.
- Utilizar nombres descriptivos para las clases.
- Mantener las clases y selectores escritos en inglés.
- Evitar selectores excesivamente específicos.
- Evitar el uso innecesario de `!important`.
- Utilizar variables CSS para colores, tipografías y valores reutilizables.
- Mantener cada propiedad en una línea independiente.
- Agrupar las propiedades de forma coherente.
- Utilizar nombres de clases consistentes con la función que representa cada componente.

Ejemplo:

    :root {
        --primary-color: #f37021;
        --secondary-color: #112433;
        --background-color: #ffffff;
    }

    .monitoring-card {
        padding: 16px;
        border-radius: 8px;
        background-color: var(--background-color);
    }

Las variables CSS permiten mantener consistencia con el Design System definido previamente para KairoLabs y facilitan la modificación global de determinados estilos.

**JavaScript**

JavaScript se utiliza principalmente para implementar comportamiento dinámico en la Landing Page y para complementar determinadas funcionalidades del Frontend Web Application.

Las convenciones utilizadas son:

- Variables y funciones en `camelCase`.
- Clases y componentes en `PascalCase`.
- Constantes globales en `UPPER_SNAKE_CASE`.
- Utilizar `const` como declaración predeterminada.
- Utilizar `let` únicamente cuando una variable requiera reasignación.
- Evitar el uso de `var`.
- Mantener nombres descriptivos.
- Evitar funciones excesivamente extensas.
- Separar responsabilidades cuando una función realiza múltiples operaciones.

Ejemplo de constante:

    const API_BASE_URL = '/api/v1';

Ejemplo de función:

    function fetchSensorData() {
        // Implementation
    }

Ejemplo de nombres utilizados:

`fetchSensorData`

`loadEstablishments`

`updateUserProfile`

`validateCredentials`

`API_BASE_URL`

Estas convenciones facilitan la interpretación del código y permiten mantener uniformidad entre los diferentes integrantes del equipo.

**Vue.js**

La Frontend Web Application de KairoLabs se desarrolla utilizando Vue.js 3.

Los componentes utilizan nombres descriptivos en `PascalCase`, relacionados directamente con la funcionalidad que representan.

Ejemplos:

`MonitoringView.vue`

`EstablishmentsView.vue`

`SubscriptionsView.vue`

`UserProfile.vue`

`DashboardView.vue`

La estructura del frontend busca mantener separación entre vistas, componentes reutilizables, servicios, rutas y gestión de estado.

La lógica que puede reutilizarse en diferentes vistas debe mantenerse fuera de los componentes específicos cuando corresponda.

Asimismo, los componentes deben evitar concentrar demasiadas responsabilidades dentro de un único archivo.

La navegación entre vistas se administra mediante Vue Router y el estado compartido de la aplicación se gestiona mediante Pinia.

**C# / ASP.NET Core**

Para los Web Services desarrollados con ASP.NET Core y C# se utilizan las convenciones habituales del ecosistema .NET.

Las reglas principales son:

- Clases en `PascalCase`.
- Métodos en `PascalCase`.
- Propiedades en `PascalCase`.
- Interfaces en `PascalCase`, utilizando el prefijo `I`.
- Variables locales en `camelCase`.
- Parámetros en `camelCase`.
- Uso de nombres descriptivos.
- Mantener separación entre controladores, servicios, repositorios y entidades.
- Mantener métodos con responsabilidades claramente definidas.

Ejemplo:

    public class DeviceService
    {
        public async Task<Device> GetDeviceByIdAsync(long deviceId)
        {
            // Implementation
        }
    }

Ejemplo de interfaz:

    public interface IDeviceRepository
    {
        Task<Device> GetByIdAsync(long deviceId);
    }

La utilización de `PascalCase` para clases, métodos y propiedades mantiene coherencia con las convenciones del lenguaje C#.

**RESTful API**

Los endpoints implementados en la RESTful API siguen una estructura consistente basada en recursos.

Las rutas utilizan nombres en plural y minúsculas.

Ejemplos:

`/api/v1/users`

`/api/v1/devices`

`/api/v1/establishments`

`/api/v1/operators`

`/api/v1/transports`

`/api/v1/subscriptions`

Los métodos HTTP se utilizan de acuerdo con la operación realizada:

| Método | Uso |
| :--- | :--- |
| `GET` | Obtener uno o más recursos. |
| `POST` | Crear nuevos recursos. |
| `PUT` | Actualizar recursos existentes. |
| `DELETE` | Eliminar recursos. |

Ejemplos:

`GET /api/v1/devices`

`POST /api/v1/devices`

`PUT /api/v1/devices/{id}/sensor-data`

`DELETE /api/v1/establishments/{id}`

Esta estructura permite mantener consistencia entre los diferentes Bounded Contexts implementados en el backend.

**Organización de archivos y componentes**

La organización de los archivos se mantiene de acuerdo con la responsabilidad de cada componente.

En el Frontend Web Application, los archivos se distribuyen principalmente entre vistas, componentes, rutas, stores y servicios.

Una estructura referencial es:

    src/
    ├── components/
    ├── views/
    ├── router/
    ├── stores/
    ├── services/
    └── assets/

En los Web Services, la organización responde a las responsabilidades correspondientes a la arquitectura implementada.

Una estructura referencial es:

    Backend/
    ├── Controllers/
    ├── Domain/
    ├── Application/
    ├── Infrastructure/
    └── Persistence/

Esta organización facilita la localización de archivos y permite que los integrantes del equipo puedan identificar rápidamente la ubicación de una funcionalidad.

**Convenciones de control de versiones**

Las convenciones de estilo del código se complementan con el uso de Conventional Commits definido en la sección anterior.

Los mensajes deben ser breves, descriptivos y representar de manera clara el propósito de cada modificación.

Ejemplos:

`feat(profile): implement user profile management`

`fix(auth): correct sign-in validation`

`docs(report): update implementation evidence`

`refactor(iam): reorganize bounded context structure`

`style(landing): improve responsive layout`

En conjunto, estas convenciones permiten mantener una base de código coherente entre los diferentes productos de KairoLabs, facilitan las revisiones realizadas por el equipo y reducen inconsistencias durante la integración de nuevas funcionalidades.

### 5.1.4. Software Deployment Configuration

La configuración de despliegue de KairoLabs define las plataformas, servicios y configuraciones utilizadas para publicar los diferentes componentes que conforman la solución desarrollada.

Debido a que el producto está compuesto por una Landing Page, una Frontend Web Application y una RESTful API, cada componente cuenta con una configuración de despliegue independiente, permitiendo mantener una arquitectura modular y facilitar la actualización de cada servicio sin afectar al resto de componentes.

La estrategia de despliegue utilizada permite integrar los repositorios alojados en GitHub con plataformas cloud, logrando automatizar la publicación de nuevas versiones cuando se incorporan cambios en las ramas configuradas.

La infraestructura utilizada para el despliegue de KairoLabs se resume en la siguiente tabla:

| Componente | Tecnología | Plataforma de despliegue | Estado |
| :--- | :--- | :--- | :--- |
| Landing Page | HTML5, CSS3, JavaScript | Vercel | Desplegado |
| Frontend Web Application | Vue.js 3 | Vercel | Desplegado |
| RESTful API | ASP.NET Core / C# | Render | Desplegado |
| Base de datos | PostgreSQL | Filess.io | Configurada |

---

## Landing Page Deployment

La Landing Page de KairoLabs se encuentra desplegada utilizando la plataforma **Vercel**, la cual permite alojar aplicaciones frontend y sitios web estáticos mediante integración directa con repositorios GitHub.

El despliegue se encuentra vinculado al repositorio:

```text
KairoLabs-Landing-Page
```

La configuración utilizada es:

| Configuración | Valor |
| :--- | :--- |
| Plataforma | Vercel |
| Tecnología | HTML5, CSS3 y JavaScript |
| Repositorio | KairoLabs-Landing-Page |
| Rama utilizada | main |
| Tipo de despliegue | Automático mediante integración con GitHub |

La Landing Page permite presentar la propuesta de valor de KairoLabs, incluyendo información relacionada con la plataforma, tecnología utilizada, sectores objetivo, planes y medios de contacto.

La URL pública del despliegue es:

```text
https://KairoLabs-sensor.vercel.app/
```

<p align="center">
  <img src="../assets/landing-page-deployment.png" alt="Despliegue Landing Page KairoLabs" width="700"><br>
  <em>Nota: Evidencia del despliegue de la Landing Page mediante Vercel.</em>
</p>

---

## Frontend Web Application Deployment

La Frontend Web Application de KairoLabs se encuentra desarrollada utilizando **Vue.js 3** y desplegada mediante la plataforma **Vercel**.

La aplicación frontend mantiene comunicación con la RESTful API mediante solicitudes HTTP utilizando Axios, permitiendo consumir los servicios implementados en el backend.

El despliegue se encuentra conectado con el repositorio:

```text
KairoLabs-Frontend
```

La configuración utilizada es:

| Configuración | Valor |
| :--- | :--- |
| Plataforma | Vercel |
| Framework | Vue.js 3 |
| Repositorio | KairoLabs-Frontend |
| Rama utilizada | main |
| Gestor de paquetes | npm |
| Tipo de despliegue | Integración continua con GitHub |

La aplicación web se encuentra disponible mediante:

```text
https://kairolabs-frontend.vercel.app/login
```

Durante la configuración del despliegue se utilizan variables de entorno para definir la URL del backend.

La variable principal configurada es:

```text
VITE_API_BASE_URL
```

Esta variable permite modificar la dirección del servicio backend sin realizar cambios directamente dentro del código fuente.

<p align="center">
  <img src="../assets/frontend-deployment.png" alt="Despliegue Frontend Web Application KairoLabs" width="700"><br>
  <em>Nota: Evidencia del despliegue de la Frontend Web Application.</em>
</p>

---

## RESTful API Deployment

La RESTful API de KairoLabs fue implementada utilizando **ASP.NET Core** y **C#**, siendo responsable de manejar la lógica de negocio, comunicación con la base de datos y exposición de servicios utilizados por la aplicación frontend.

El backend se encuentra desplegado mediante la plataforma **Render**.

El repositorio asociado es:

```text
KairoLabs-Backend
```

La configuración utilizada es:

| Configuración | Valor |
| :--- | :--- |
| Plataforma | Render |
| Framework | ASP.NET Core |
| Lenguaje | C# |
| Tipo de servicio | Web Service |
| Repositorio | KairoLabs-Backend |
| Rama utilizada | main |

La URL pública del servicio es:

```text
https://kairolabs-platform.onrender.com
```

Para la ejecución del servicio se configuran variables de entorno relacionadas con el ambiente de ejecución y la conexión con PostgreSQL.

Las principales variables utilizadas son:

```text
ASPNETCORE_ENVIRONMENT

ConnectionStrings__DefaultConnection
```

La utilización de variables de entorno evita almacenar información sensible dentro del repositorio del proyecto.

<p align="center">
  <img src="../assets/backend-deployment.png" alt="Despliegue RESTful API KairoLabs" width="700"><br>
  <em>Nota: Evidencia del despliegue de la RESTful API mediante Render.</em>
</p>

---

## Database Deployment

La solución utiliza **PostgreSQL** como sistema gestor de base de datos relacional para almacenar la información utilizada por KairoLabs.

La base de datos se encuentra configurada mediante el servicio **Filess.io**, permitiendo la conexión remota desde la RESTful API desplegada en Render.

La configuración principal es:

| Configuración | Valor |
| :--- | :--- |
| Motor de base de datos | PostgreSQL |
| Plataforma | Filess.io |
| Acceso | Remoto mediante cadena de conexión |
| ORM utilizado | Entity Framework Core |

La conexión entre el backend y la base de datos se realiza mediante Entity Framework Core utilizando una cadena de conexión configurada como variable de entorno.

De esta manera, los datos sensibles como credenciales y parámetros de conexión no son almacenados directamente dentro del código fuente.

<p align="center">
  <img src="../assets/database-deployment.png" alt="Base de Datos PostgreSQL KairoLabs" width="700"><br>
  <em>Nota: Configuración de la base de datos PostgreSQL utilizada por KairoLabs.</em>
</p>

---

## Environment Configuration

Para mantener una configuración segura y adaptable entre ambientes, KairoLabs utiliza variables de entorno durante el despliegue.

Las variables principales utilizadas son:

| Variable | Componente | Función |
| :--- | :--- | :--- |
| `VITE_API_BASE_URL` | Frontend Web Application | Define la dirección pública de la RESTful API. |
| `ConnectionStrings__DefaultConnection` | RESTful API | Permite establecer conexión con PostgreSQL. |
| `ASPNETCORE_ENVIRONMENT` | RESTful API | Define el ambiente de ejecución del backend. |

Esta estrategia permite modificar parámetros de configuración sin realizar cambios directamente en el código fuente.

---

## Deployment Architecture

La arquitectura de despliegue final de KairoLabs se representa de la siguiente manera:

```text
                         Usuario
                            |
                            |
                    Landing Page
                         Vercel
                            |
                            |
             Frontend Web Application
                         Vercel
                            |
                            |
                    RESTful API
                         Render
                            |
                            |
                  PostgreSQL Database
                       Filess.io
```

La separación de componentes permite mantener responsabilidades independientes:

- La Landing Page gestiona la presentación pública del producto.
- La Frontend Web Application proporciona la interfaz utilizada por los usuarios.
- La RESTful API concentra la lógica de negocio y comunicación con datos.
- La Base de Datos PostgreSQL almacena la información persistente del sistema.

Esta configuración permite que cada componente pueda evolucionar y desplegarse de manera independiente, facilitando el mantenimiento y escalabilidad de KairoLabs.


### 5.2.1. Sprint 1

En este Sprint se desarrolló e implementó la primera versión de la **Landing Page de KairoLabs**, incluyendo su despliegue en un entorno accesible públicamente.

El objetivo principal fue establecer la primera versión funcional de la presencia digital del producto, permitiendo presentar la propuesta de valor de KairoLabs, explicar su funcionamiento, mostrar sus principales características y comunicar la solución a los segmentos objetivo.

Asimismo, durante este Sprint se desarrollaron actividades relacionadas con la definición de User Stories, entrevistas, User Personas, Journey Maps y el diseño de la experiencia visual del producto.

---

#### Sprint Planning 1

A continuación se presenta el resumen del Sprint Planning Meeting realizado para el Sprint 1.

| Sprint # | Sprint 1 |
| :--- | :--- |
| **Sprint Planning Background** |  |
| **Date** | 15/04/2026 |
| **Time** | 04:30 PM |
| **Location** | Reunión virtual vía Google Meet |
| **Prepared By** | Diaz Mendoza, Sebastian Victor Andre |
| **Attendees** | Mallqui Vilca, Dhilsen Armil; Diaz Mendoza, Sebastian Victor Andre; Ramirez Escalante, Carlo Patricio; Oblitas Alcalde, Rodrigo; Dinklange Arevalo, Sandro |
| **Sprint Goal & User Stories** |  |
| **Sprint 1 Goal** | Our goal is to lay the groundwork for the project and launch the first version of the Landing Page. We believe this page will allow healthcare providers and pharmacy managers to better understand KairoLabs, which measures the status of medications in their storage environment. This will be confirmed once the Landing Page is live and contains relevant content for both target groups. |
| **Sprint 1 Velocity** | 21 |
| **Sum of Story Points** | 21 |

---

#### Aspect Leaders and Collaborators

En esta sección se detalla la matriz de liderazgo y colaboración para el Sprint 1. Cada aspecto representa una fase relevante de la entrega, donde se designa un líder (L) responsable de orientar el desarrollo del entregable y colaboradores (C) que apoyan en su ejecución.

| Team Member (Last Name, First Name) | GitHub Username | Idea de Negocio y Bases | Diseño de App Web (Figma) | Contenido y Despliegue Landing | User Stories y Funciones | Análisis de Usuario y Needfinding |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **Mallqui Vilca, Dhilsen Armil** | `Dhilsen18` | C | C | **L** | C | **L** |
| **Diaz Mendoza, Sebastian Victor Andre** | `DiazDeveloper` | C | **L** | C | C | C |
| **Ramirez Escalante, Carlo Patricio** | `Dhilsen18` | **L** | C | C | **L** | C |
| **Oblitas Alcalde, Rodrigo** | `DiazDeveloper` | C | C | C | C | C |
| **Dinklange Arevalo, Sandro** | `Dhilsen18` | C | C | C | C | C |

**Sustento de los aspectos de liderazgo:**

- **Mallqui Vilca, Dhilsen Armil – Contenido y Despliegue Landing / Análisis de Usuario:** lideró la implementación de la Landing Page y su configuración para el despliegue en Vercel. Asimismo, participó en el análisis de los usuarios objetivo y en la elaboración de los artefactos relacionados con User Personas y Journey Maps.

- **Diaz Mendoza, Sebastian Victor Andre – Diseño de App Web (Figma):** lideró la organización visual de la propuesta, trabajando sobre los mock-ups y la definición de los elementos visuales utilizados como referencia para la implementación de la Landing Page.

- **Ramirez Escalante, Carlo Patricio – Idea de Negocio y Bases / User Stories y Funciones:** lideró la conceptualización de la propuesta de negocio y la organización de las User Stories que sirvieron como base para la planificación del Sprint.

- **Oblitas Alcalde, Rodrigo:** colaboró en las actividades de diseño, definición de funcionalidades y desarrollo de la Landing Page, participando en la integración de los diferentes elementos de la propuesta.

- **Dinklange Arevalo, Sandro:** colaboró en las actividades de diseño, documentación y revisión de los artefactos desarrollados durante el Sprint.

---

#### Sprint Backlog 1

Durante el primer Sprint, el equipo tuvo como objetivo principal desarrollar la Landing Page de KairoLabs y establecer las bases iniciales de la aplicación web.

Para la organización y gestión de las actividades se utilizó **Trello**, permitiendo dividir las User Stories en tareas manejables y asignarlas a los integrantes del equipo.

El propósito de este Sprint fue construir una primera versión funcional de la Landing Page, asegurando que fuera atractiva, funcional y alineada con la propuesta de valor de KairoLabs.

![Sprint Backlog 1](../assets/Sprint%20Backlog%201.png)

**Enlace de Trello:**

https://trello.com/invite/b/69e9e940d5d58b559007b0af/ATTIbc7fef21e3ae9af5f9b1524a8311a897E9406869/KairoLabs-sensor

A continuación se presenta la descomposición de User Stories en tareas correspondientes al Sprint 1:

| Sprint # | Sprint 1 | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **User Story** | | **Work-Item / Task** | | | | | |
| **Id** | **Title** | **Id** | **Title** | **Description** | **Estimation (Hours)** | **Assigned To** | **Status** |
| US25 | Adaptación a dispositivos | T01 | Implementar diseño responsive | Configurar media queries y hacer la Landing Page adaptable a móviles, tablets y desktop. | 8 | Mallqui Vilca, Dhilsen Armil | Done |
| US01 | Navegación clara | T02 | Desarrollar navbar sticky | Implementar barra de navegación fija con smooth scroll. | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| US06 | Mensaje principal claro | T03 | Implementar sección Hero | Desarrollar Hero Section con typing animation y tagline. | 5 | Mallqui Vilca, Dhilsen Armil | Done |
| US13 | Presentación profesional | T04 | Diseñar mock-ups en Figma | Crear el diseño visual profesional de las diferentes secciones. | 10 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US13 | Presentación profesional | T05 | Aplicar Design System | Implementar colores, tipografía Outfit y elementos visuales. | 6 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US10 | Botón de contacto visible | T06 | Implementar CTAs | Añadir botones de contacto en navbar y Hero. | 2 | Oblitas Alcalde, Rodrigo | Done |
| US11 | Acceso a contacto | T07 | Desarrollar formulario de contacto | Crear formulario con campos de nombre, empresa, email, teléfono y mensaje. | 4 | Oblitas Alcalde, Rodrigo | Done |
| US21 | Información de monitoreo | T08 | Implementar dashboard IoT simulado | Desarrollar tarjetas con datos simulados de temperatura, humedad y luz. | 6 | Ramirez Escalante, Carlo Patricio | Done |
| US02 | Acceso a sección de tecnología | T09 | Desarrollar sección Tecnología | Crear sección con explicación del sistema y features. | 4 | Ramirez Escalante, Carlo Patricio | Done |
| US03 | Acceso a sectores | T10 | Desarrollar sección Sectores | Implementar cards de hospitales, distribución y farmacias. | 5 | Ramirez Escalante, Carlo Patricio | Done |
| US16 | Contenido para almacenes | T11 | Redactar contenido segmento operativo | Escribir textos orientados a personal de almacén. | 3 | Dinklange Arevalo, Sandro | Done |
| US17 | Contenido para entidades | T12 | Redactar contenido segmento gestores | Escribir textos orientados a entidades de salud. | 3 | Dinklange Arevalo, Sandro | Done |
| US07 | Identificación del problema | T13 | Desarrollar sección Problema | Implementar floating cards con la problemática identificada. | 4 | Ramirez Escalante, Carlo Patricio | Done |
| US04 | Información del equipo | T14 | Desarrollar sección Nosotros | Crear sección con misión, visión y equipo KairoLabs. | 4 | Dinklange Arevalo, Sandro | Done |
| US22 | Incentivo a contacto | T15 | Implementar planes de suscripción | Desarrollar pricing cards con planes Básico, Profesional y Premium. | 5 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US15 | Coherencia visual | T16 | Implementar animaciones | Añadir reveal animations mediante IntersectionObserver. | 4 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US12 | Respuesta visual a interacción | T17 | Añadir efectos hover | Implementar transiciones y efectos en botones y cards. | 3 | Oblitas Alcalde, Rodrigo | Done |
| US26 | Carga eficiente | T18 | Optimizar assets | Comprimir imágenes y optimizar la carga de fuentes. | 3 | Oblitas Alcalde, Rodrigo | Done |
| US05 | Visualización de beneficios | T19 | Implementar sección Stats | Desarrollar contador animado con métricas clave. | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| US14 | Información estructurada | T20 | Organizar contenido | Estructurar las secciones en orden lógico y establecer una jerarquía visual. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| - | - | T21 | Configurar despliegue en Vercel | Conectar el repositorio y configurar el deployment automático. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| - | - | T22 | Definir User Stories | Documentar 27 User Stories con criterios de aceptación. | 6 | Ramirez Escalante, Carlo Patricio | Done |
| - | - | T23 | Realizar entrevistas | Conducir entrevistas con ambos segmentos objetivo. | 8 | Ramirez Escalante, Carlo Patricio / Dinklange Arevalo, Sandro | Done |
| - | - | T24 | Elaborar User Personas | Crear arquetipos basados en las entrevistas realizadas. | 4 | Dinklange Arevalo, Sandro | Done |
| - | - | T25 | Crear Journey Maps | Mapear la experiencia de los usuarios. | 4 | Dinklange Arevalo, Sandro | Done |

---

#### Development Evidence for Sprint Review

Durante el Sprint 1, el equipo utilizó GitHub como sistema de control de versiones, siguiendo el flujo de trabajo GitFlow para asegurar una integración ordenada del código.

La evidencia de desarrollo se concentra principalmente en el repositorio de la Landing Page, donde se registraron los cambios relacionados con la estructura, diseño, correcciones y preparación de la primera versión.

**Repository:**

`1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Landing-Page`

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `KairoLabs-Landing-Page` | `main` | `cf30ba5` | `feat: implement team section` | `Added specific content and layout for the startup team profiles.` | 19/04/2026 |
| `KairoLabs-Landing-Page` | `main` | `e6420c0` | `chore: finalize landing page structure` | `Final adjustments to the HTML structure for the initial release.` | 12/04/2026 |
| `KairoLabs-Landing-Page` | `main` | `965dc26` | `fix: resolve remaining layout issues` | `Ensured all sections are correctly aligned after final review.` | 11/04/2026 |
| `KairoLabs-Landing-Page` | `main` | `03e62cb` | `fix: clean up code and remove errors` | `General debugging of CSS and HTML validation issues.` | 11/04/2026 |
| `KairoLabs-Landing-Page` | `main` | `5d82cf0` | `docs: add project readme file` | `Initial documentation of the repository and project description.` | 11/04/2026 |
| `KairoLabs-Landing-Page` | `main` | `4c8156b` | `feat: update landing page and design` | `Applied general style updates and design refinements for UX.` | 11/04/2026 |
| `KairoLabs-Landing-Page` | `main` | `74dba14` | `chore: initial commit` | `Initial repository setup with base project files.` | 10/04/2026 |

Estos commits evidencian la evolución de la Landing Page desde la configuración inicial del repositorio hasta la implementación de sus principales secciones, corrección de problemas visuales, incorporación de documentación y preparación de la primera versión desplegable.

---

#### Execution Evidence for Sprint Review

En esta sección se presenta la evidencia de la ejecución del Sprint 1, demostrando el cumplimiento del objetivo establecido y el despliegue de la Landing Page en un entorno de producción accesible.

![Landing Page Evidence](../assets/Landing%20pAge%20EVIDENCE.png)

**Enlace de la Landing Page:**

https://KairoLabs-sensor.vercel.app/

**Evidencia de despliegue mediante Vercel:**

A continuación, se presenta la captura del dashboard de Vercel que confirma el despliegue exitoso de la Landing Page desde el repositorio oficial de GitHub.

![Deploy Landing](../assets/Deploy%20Landing.jpeg)

El resultado del Sprint permite disponer de una primera versión pública de KairoLabs en la que se presenta la propuesta de valor del producto y la información dirigida a sus segmentos objetivo.

---

#### Services Documentation Evidence for Sprint Review

Para el presente Sprint 1, el alcance se centró exclusivamente en la implementación y despliegue de la **Landing Page**, correspondiente a un sitio web estático.

Por lo tanto, durante esta etapa no se desarrollaron servicios RESTful API.

La documentación detallada de los endpoints mediante **OpenAPI (Swagger)** se incorporaría en los siguientes Sprints, una vez iniciada la fase de implementación de los Web Services.

---

#### Software Deployment Evidence for Sprint Review

El despliegue de la Landing Page se realizó utilizando Vercel y se configuró mediante el repositorio de GitHub correspondiente.

**Paso 1: Agregar el proyecto**

![Agregar proyecto](../assets/Agregar%20proyecto.png)

**Paso 2: Agregar el repositorio**

![Agregar repositorio](../assets/Agregar%20repositorio.png)

**Paso 3: Realizar el deploy con HTML, CSS y JavaScript**

![Deploy Landing](../assets/Deploy%20Landing.jpeg)

La configuración permitió publicar la Landing Page en un entorno accesible mediante Internet y establecer una conexión entre el repositorio de GitHub y la plataforma de despliegue.

---

#### Team Collaboration Insights during Sprint

La implementación del Sprint 1 fue un esfuerzo conjunto que integró el desarrollo técnico de la Landing Page, la definición de la propuesta de valor, el diseño de la interfaz, la investigación de usuarios y la elaboración del reporte de ingeniería.

El equipo aplicó un esquema de liderazgo compartido, distribuyendo responsabilidades entre los cinco integrantes de acuerdo con las principales áreas de trabajo del Sprint.

**Mallqui Vilca, Dhilsen Armil — `Dhilsen18`**

Participó principalmente en la implementación y despliegue de la Landing Page, además de colaborar en el análisis de usuarios. Sus actividades incluyeron la adaptación responsive, navegación, Hero, optimización de recursos y configuración del despliegue en Vercel.

**Diaz Mendoza, Sebastian Victor Andre — `DiazDeveloper`**

Participó principalmente en el diseño visual y la implementación de elementos relacionados con el Design System. Sus actividades incluyeron la elaboración de mock-ups, aplicación de la identidad visual, planes de suscripción y animaciones.

**Ramirez Escalante, Carlo Patricio — `Dhilsen18`**

Participó en la definición de la idea de negocio y User Stories, además de colaborar en la implementación de secciones relacionadas con tecnología, sectores, monitoreo y problemática.

**Oblitas Alcalde, Rodrigo — `DiazDeveloper`**

Participó en la implementación de elementos de interacción y contacto de la Landing Page, incluyendo CTAs, formulario de contacto, efectos hover y optimización de recursos.

**Dinklange Arevalo, Sandro — `Dhilsen18`**

Participó en la elaboración de contenido orientado a los segmentos objetivo, la sección institucional del equipo y actividades relacionadas con entrevistas, User Personas y Journey Maps.

**Evidencia de contribuciones en el código de la Landing Page:**

![Deploy Contributors del repositorio de la Landing Page](../assets/Deploy%20Contributors%20del%20repositorio%20de%20la%20Landing%20Page.png)

**Evidencia de contribuciones en el reporte:**

![Contributors del repositorio del informe](../assets/Contributors%20del%20repositorio%20del%20informe.png)

Estas evidencias permiten mostrar la participación del equipo tanto en el repositorio correspondiente al código fuente de la Landing Page como en el repositorio destinado a la documentación del proyecto.

### 5.2.2. Sprint 2

En esta sección se registra y explica el avance en términos de producto y trabajo colaborativo para el **Sprint 2**. Durante esta iteración, el equipo pasó de la primera versión de la Landing Page a la implementación de la primera versión funcional de la **Web Application de KairoLabs**, desarrollada con Vue.js.

El trabajo se organizó por bounded contexts, permitiendo avanzar en los módulos de autenticación, monitoreo, establecimientos, logística, suscripciones y perfil de usuario. Asimismo, se mantuvo la utilización de GitHub y GitFlow para organizar las ramas de desarrollo y posteriormente integrar los cambios.

---

#### 5.2.2.1. Sprint Planning 2

A continuación se presenta el resumen del Sprint Planning Meeting realizado para el Sprint 2.

| Sprint # | Sprint 2 |
| :--- | :--- |
| **Sprint Planning Background** |  |
| **Date** | 11/05/2026 |
| **Time** | Según planificación del Sprint 2 |
| **Location** | Reunión virtual |
| **Prepared By** | Diaz Mendoza, Sebastian Victor Andre |
| **Attendees** | Mallqui Vilca, Dhilsen Armil; Diaz Mendoza, Sebastian Victor Andre; Ramirez Escalante, Carlo Patricio; Oblitas Alcalde, Rodrigo; Dinklange Arevalo, Sandro |
| **Sprint 2 – Review Summary** | Sprint 1 was very well coordinated; however, we failed to meet the requirements, resulting in a noticeable decrease in the quality of the content and the software product delivered during this sprint. The Landing Page was of good quality; however, the established requirements regarding commits and product development were not followed. Team members are aware of these errors thanks to feedback provided by the Product Owner. |
| **Sprint 2 – Retrospective Summary** | The team admits that the development of the previous sprint was not fully aligned with the requested requirements. We recognize that the software products were correctly oriented in terms of the stated objectives; however, its implementation and development presented deficiencies. The Product Owner provided important support through constant feedback, which allowed the team to identify errors and make the necessary corrections to improve the quality of the product. |
| **Sprint Goal & User Stories** |  |
| **Sprint 2 Goal** | Our goal is to develop our first version of the frontend of our web application. We believe that this application will allow entity pharmacy administrators to manage data within the establishments belonging to the health entity, as well as its operators and devices. Likewise, operators will be able to manage the data received by the devices and transports according to the metrics received by them. |
| **Sprint 2 Velocity** | 20 |
| **Sum of Story Points** | 20 |

Como acción de mejora derivada de la retrospectiva, durante el Sprint 2 se reforzó el uso de **GitFlow, Conventional Commits y las evidencias de trabajo en GitHub**. El resultado fue una primera versión funcional del frontend desplegada en Vercel, incorporando los principales módulos definidos para la aplicación.

---

#### 5.2.2.2. Aspect Leaders and Collaborators

En esta sección se presenta la matriz de liderazgo y colaboración para el Sprint 2. Cada aspecto corresponde a una actividad relevante del desarrollo del frontend y se identifica un líder (L) y los colaboradores (C) que participaron en la actividad.

| Team Member (Last Name, First Name) | GitHub Username | Frontend Development | IAM Module | Subscriptions Module | Monitoring Module | Establishment Module | Logistics Module | Frontend UI/Design | Report & Documentation |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Mallqui Vilca, Dhilsen Armil** | `Dhilsen18` | C | C | **L** | **L** | **L** | C | C | C |
| **Diaz Mendoza, Sebastian Victor Andre** | `DiazDeveloper` | C | **L** | C | C | C | **L** | C | C |
| **Ramirez Escalante, Carlo Patricio** | `Dhilsen18` | **L** | C | C | C | C | C | C | **L** |
| **Oblitas Alcalde, Rodrigo** | `DiazDeveloper` | C | C | C | C | C | **L** | **L** | C |
| **Dinklange Arevalo, Sandro** | `Dhilsen18` | C | C | C | C | C | C | C | C |

**Sustento de los aspectos de liderazgo:**

- **Mallqui Vilca, Dhilsen Armil – Subscriptions, Monitoring y Establishment:** dirigió la implementación de los módulos de planes y suscripciones, monitoreo y establecimientos, participando en la construcción de las vistas, indicadores y elementos de interacción de cada módulo.

- **Diaz Mendoza, Sebastian Victor Andre – IAM y Frontend UI/Design:** lideró la estructuración visual de la aplicación y participó en el módulo de autenticación, contribuyendo a la coherencia visual entre las diferentes vistas del frontend.

- **Ramirez Escalante, Carlo Patricio – Frontend Development y Report & Documentation:** coordinó actividades de integración general del frontend y participó en la organización de la documentación correspondiente al Sprint.

- **Oblitas Alcalde, Rodrigo – Logistics y Frontend UI/Design:** lideró las actividades relacionadas con logística y transportes, además de participar en la adaptación visual y responsive de los componentes.

- **Dinklange Arevalo, Sandro:** colaboró en las actividades de implementación, revisión visual, documentación y pruebas funcionales de los diferentes módulos.

---

#### 5.2.2.3. Sprint Backlog 2

Durante el segundo Sprint, el equipo tuvo como objetivo principal desarrollar la primera versión funcional de la **Aplicación Web de KairoLabs**. Para organizar el trabajo se utilizó Trello, permitiendo dividir las User Stories en tareas manejables y asignarlas a los integrantes de acuerdo con las áreas funcionales del sistema.

El propósito de este Sprint fue construir parcialmente la aplicación web, incorporando los principales módulos de monitoreo, autenticación, establecimientos, logística, suscripciones y elementos responsive.

![Sprint Backlog 2](../assets/Sprint%20Backlog%202.png)

**Enlace de Trello:**

https://trello.com/invite/b/6a02a35d4f75f7ddabeabe1c/ATTIbbc3193b48f5acf5194c54a2233ca38e2EFFB77A/KairoLabs

| Sprint # | Sprint 2 | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **User Story** | | **Work-Item / Task** | | | | | |
| **Id** | **Title** | **Id** | **Title** | **Description** | **Estimation (Hours)** | **Assigned To** | **Status** |
| US29 | Monitoreo de temperatura en dashboard | TS-US29-001 | Crear widget de temperatura | Desarrollar componente visual para mostrar temperatura en tiempo real. | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| US29 | Monitoreo de temperatura en dashboard | TS-US29-003 | Mostrar timestamp de última lectura | Implementar visualización de fecha y hora de la última actualización del sensor. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US30 | Monitoreo de luz | TS-US30-001 | Crear widget de intensidad lumínica | Desarrollar componente visual para mostrar niveles de luz. | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| US42 | Identificación de desviaciones visuales | TS-US42-002 | Resaltar sensores críticos con colores de alerta | Aplicar indicadores visuales para sensores fuera de rango. | 3 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US33 | Identificación por ubicación | TS-US33-005 | Validar legibilidad de ubicaciones en móviles | Verificar la correcta visualización responsive de ubicaciones. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US25 | Adaptación a dispositivos | TS-US25-001 | Implementar media queries principales | Configurar estilos responsive para dashboard y módulos. | 5 | Mallqui Vilca, Dhilsen Armil | Done |
| US25 | Adaptación a dispositivos | TS-US25-002 | Adaptar navbar para dispositivos móviles | Ajustar navegación responsive para smartphones y tablets. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| US25 | Adaptación a dispositivos | TS-US25-007 | Realizar pruebas responsive en múltiples resoluciones | Validar funcionamiento visual en distintos tamaños de pantalla. | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| US28 | Visualización de sensores activos | TS-US28-005 | Integrar estilos responsive | Aplicar diseño adaptable al panel de sensores. | 3 | Oblitas Alcalde, Rodrigo | Done |
| US30 | Monitoreo de luz | TS-US30-004 | Implementar indicador visual de rango seguro | Mostrar estado seguro o crítico de niveles lumínicos. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| US34 | Estado general del sistema | TS-US34-002 | Mostrar total de sensores activos | Implementar contador general de sensores conectados. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US37 | Visualización de gráficos | TS-US37-001 | Crear gráfico de temperatura | Desarrollar gráfico dinámico de tendencias de temperatura. | 5 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US42 | Identificación de desviaciones visuales | TS-US42-001 | Crear lógica visual para valores fuera de rango | Implementar detección visual de valores críticos. | 4 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US28 | Visualización de sensores activos | TS-US28-007 | Validar visualización responsive de sensores | Verificar correcta adaptación responsive de tarjetas de sensores. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US29 | Monitoreo de temperatura en dashboard | TS-US29-006 | Validar visualización en dispositivos móviles | Probar visualización responsive del módulo de temperatura. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US34 | Estado general del sistema | TS-US34-004 | Implementar indicador general de estado | Mostrar estado global mediante indicadores visuales. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| US42 | Identificación de desviaciones visuales | TS-US42-001 | Crear lógica visual para valores fuera de rango | Revisar funcionamiento de detección visual de alertas. | 4 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US30 | Monitoreo de luz | TS-US30-006 | Validar adaptación responsive del módulo | Validar adaptación responsive del widget lumínico. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US37 | Visualización de gráficos | TS-US37-002 | Diseñar estilos responsive para gráficos | Corregir problemas visuales y adaptación responsive de gráficos. | 3 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US28 | Visualización de sensores activos | TS-US28-003 | Mostrar nombre y estado del sensor | Implementar visualización de información principal de sensores. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US28 | Visualización de sensores activos | TS-US28-004 | Implementar indicador visual activo/inactivo | Mostrar estado activo o desconectado mediante colores e íconos. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| US28 | Visualización de sensores activos | TS-US28-005 | Consumir datos mock de sensores | Integrar datos simulados para pruebas del dashboard. | 3 | Oblitas Alcalde, Rodrigo | Done |
| US28 | Visualización de sensores activos | TS-US28-006 | Aplicar estilos al panel de sensores | Diseñar interfaz visual del módulo de sensores. | 3 | Oblitas Alcalde, Rodrigo | Done |
| US29 | Monitoreo de temperatura en dashboard | TS-US29-002 | Mostrar valor actual en °C | Implementar lectura actual de temperatura con unidad. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US29 | Monitoreo de temperatura en dashboard | TS-US29-005 | Actualizar estilos visuales según rango | Aplicar estilos dinámicos según valores críticos o normales. | 3 | Diaz Mendoza, Sebastian Victor Andre | Done |
| US34 | Estado general del sistema | TS-US34-001 | Diseñar sección resumen del dashboard | Crear layout general del resumen del sistema. | 4 | Ramirez Escalante, Carlo Patricio | Done |
| US33 | Identificación por ubicación | TS-US33-001 | Mostrar ubicación física de sensores | Implementar etiquetas de ubicación física de sensores. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US33 | Identificación por ubicación | TS-US33-002 | Diseñar etiqueta visual de ubicación | Crear estilos visuales para etiquetas de ubicación. | 2 | Ramirez Escalante, Carlo Patricio | Done |
| US33 | Identificación por ubicación | TS-US33-003 | Implementar agrupación visual por ubicación | Agrupar sensores visualmente según su área física. | 3 | Ramirez Escalante, Carlo Patricio | Done |

---

#### 5.2.2.4. Development Evidence for Sprint Review

Durante el Sprint 2, el equipo utilizó **GitHub** como sistema de control de versiones, siguiendo la estrategia **GitFlow** para organizar el trabajo mediante branches asociadas a los diferentes bounded contexts.

El desarrollo se concentró en el repositorio:

`1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Frontend`

![Development Evidence TB1](../assets/Development%20Evidence%20TB1.png)

**Link del despliegue en Vercel:**

https://kairolabs-frontend.vercel.app/login

Los principales commits registrados durante el Sprint fueron:

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `KairoLabs-Frontend` | `feature/iam` | `385fda5` | `Merge branch 'feature/iam' into develop` | Integración del módulo IAM con autenticación y registro de usuarios. | 12/05/2026 |
| `KairoLabs-Frontend` | `feature/monitoring` | `fa859b5` | `feat(monitoring): finalize devices view with data integration and premium UI` | Vista de dispositivos con integración de datos y UI premium. | 12/05/2026 |
| `KairoLabs-Frontend` | `feature/monitoring` | `33911c5` | `feat(control-center): implement control center panel with KPI charts` | Panel de control central con gráficos KPI y visualización de datos. | 12/05/2026 |
| `KairoLabs-Frontend` | `feature/monitoring` | `7b10919` | `feat(monitoring): add dashboard styles and responsive design configuration` | Estilos del dashboard y configuración responsive. | 12/05/2026 |
| `KairoLabs-Frontend` | `feature/establishments` | `642bdf1` | `Merge branch 'feature/establishments' into develop` | Integración del módulo de gestión de establecimientos. | 12/05/2026 |
| `KairoLabs-Frontend` | `feature/establishments` | `d2a12e6` | `feat(establishments): rename and refactor establishment detail view` | Refactorización de la vista de detalle de establecimientos. | 12/05/2026 |
| `KairoLabs-Frontend` | `feature/logistics` | `8d2c1b8` | `Merge branch 'feature/logistics' into develop` | Integración del módulo de logística y transportes. | 12/05/2026 |
| `KairoLabs-Frontend` | `feature/subscriptions` | `4b851ae` | `feat: Implement plans selection view with plan management` | Vista de selección de planes con gestión de suscripción. | 12/05/2026 |
| `KairoLabs-Frontend` | `feature/profile` | `d0dc7f4` | `feat(profile): implement user profile management with editing capabilities` | Gestión de perfil de usuario con edición y UI mejorada. | 12/05/2026 |
| `KairoLabs-Frontend` | `develop` | `327a143` | `feat: update routing, styles, and multi-language support` | Actualización de rutas, estilos y soporte multiidioma mediante vue-i18n. | 13/05/2026 |
| `KairoLabs-Frontend` | `develop` | `f3d3b34` | `feat(vercel): add initial configuration for URL rewrites` | Configuración inicial de despliegue en Vercel. | 12/05/2026 |
| `KairoLabs-Frontend` | `develop` | `1515e1a` | `feat(dashboard): refactor fetchDashboardData to improve error handling` | Mejora del manejo de errores en consumo de datos del dashboard. | 12/05/2026 |
| `KairoLabs-Frontend` | `release/1.0.0` | `cc5b4f6` | `Merge branch 'release/1.0.0'` | Consolidación de release del Sprint 2 con todos los módulos integrados. | 12/05/2026 |

Estos registros evidencian la evolución del frontend mediante branches independientes por funcionalidad y su posterior integración en las ramas de desarrollo y release.

---

#### 5.2.2.5. Execution Evidence for Sprint Review

Después de finalizar el Sprint 2, se implementó la primera versión funcional del **frontend de KairoLabs**.

Esta entrega consolida las principales pantallas definidas en los wireframes y mock-ups del capítulo de diseño, permitiendo una navegación coherente entre autenticación, visualización de información y gestión operativa para los segmentos objetivo del sistema.

A continuación se presentan las principales evidencias de ejecución.

**1. Login y registro**

Pantalla de acceso para que los usuarios puedan iniciar sesión y autenticarse dentro de la plataforma.

![Login y registro](../assets/login_front.png)

*Figura 5.2.2.5-1. Pantalla de login y registro del frontend de KairoLabs.*

---

**2. Dashboard principal**

Panel central donde se visualiza el estado general del sistema y los indicadores más relevantes del monitoreo.

![Dashboard principal](../assets/dashboard_front.png)

*Figura 5.2.2.5-2. Vista principal del dashboard del frontend de KairoLabs.*

![Dashboard secundario](../assets/dashboard2_front.png)

*Figura 5.2.2.5-3. Vista complementaria del dashboard con información operativa adicional.*

---

**3. Gestión de establecimientos**

Sección orientada a registrar y consultar la información de las sedes o almacenes farmacéuticos vinculados a la entidad.

![Gestión de establecimientos](../assets/gestion_estable_front.png)

*Figura 5.2.2.5-4. Vista de gestión de establecimientos del frontend de KairoLabs.*

![Gestión de establecimientos 2](../assets/gestion_estable2_front.png)

*Figura 5.2.2.5-5. Vista complementaria de gestión de establecimientos con información ampliada.*

---

**4. Gestión de dispositivos y transportes**

Espacio destinado al control de los equipos y unidades asociadas al seguimiento de las condiciones ambientales.

![Gestión de dispositivos](../assets/gestion_dispo.png)

*Figura 5.2.2.5-6. Vista de gestión de dispositivos del frontend de KairoLabs.*

![Gestión de transportes](../assets/gestion_transp_front.png)

*Figura 5.2.2.5-7. Vista de gestión de transportes del frontend de KairoLabs.*

![Gestión de transportes 2](../assets/gestion_transp2_front.png)

*Figura 5.2.2.5-8. Vista complementaria de gestión de transportes con mayor detalle.*

---

**5. Perfil de usuario**

Módulo destinado a revisar y actualizar la información personal y la configuración de la cuenta.

![Perfil de usuario](../assets/perfil_usuario_front.png)

*Figura 5.2.2.5-9. Pantalla de perfil de usuario del frontend de KairoLabs.*

---

**6. Alertas e incidencias**

Vista enfocada en la notificación de eventos críticos y su seguimiento oportuno.

![Alertas e incidencias](../assets/alertas%20_ins_front.png)

*Figura 5.2.2.5-10. Pantalla de alertas e incidencias del frontend de KairoLabs.*

---

**7. Planes y suscripción**

Sección que presenta el estado del plan activo y las opciones de suscripción disponibles.

![Planes y suscripción](../assets/planes_suscrip_front.png)

*Figura 5.2.2.5-11. Pantalla principal de planes y suscripción del frontend de KairoLabs.*

![Planes y suscripción 2](../assets/planes_suscrip2_front.png)

*Figura 5.2.2.5-12. Vista complementaria de planes y suscripción del frontend de KairoLabs.*

---

#### 5.2.2.6. Services Documentation Evidence for Sprint Review

Durante el Sprint 2, el alcance se centró en el **frontend web desarrollado con Vue.js**.

En esta iteración todavía no se desarrollaron servicios RESTful. Para validar la experiencia de usuario de los módulos de dashboard, monitoreo, establecimientos y suscripciones se utilizaron **mocks locales**.

Por este motivo, la documentación mediante OpenAPI/Swagger no corresponde todavía a este Sprint.

La documentación de los servicios RESTful se implementó durante el **Sprint 3** y posteriormente se consolidó en el **Sprint 4** con la API desplegada e integrada con el frontend.

---

#### 5.2.2.7. Software Deployment Evidence for Sprint Review

El frontend de KairoLabs se desplegó en **Vercel** como primera versión de la Web Application.

| Componente | Plataforma | URL de producción |
| :--- | :--- | :--- |
| Frontend Web Application | Vercel | https://kairolabs-frontend.vercel.app/login |
| Repositorio | GitHub | `1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Frontend` |
| Rama de despliegue | `main` | Auto-deploy activo |

El despliegue permitió validar visualmente los módulos desarrollados durante el Sprint, incluyendo:

- Autenticación.
- Dashboard.
- Monitoreo.
- Establecimientos.
- Dispositivos.
- Transportes.
- Perfil de usuario.
- Alertas e incidencias.
- Planes y suscripciones.

La aplicación quedó disponible en Vercel para las pruebas correspondientes de la primera versión del frontend.

---

#### 5.2.2.8. Team Collaboration Insights during Sprint

La implementación del Sprint 2 fue un esfuerzo conjunto orientado al desarrollo de la primera versión del frontend de KairoLabs, así como a la coordinación del reporte y la continuidad de la Landing Page.

La organización del trabajo se realizó mediante **bounded contexts**, permitiendo dividir el desarrollo de las funcionalidades y mantener una estructura ordenada en el repositorio.

**Repositorio de Frontend:** `KairoLabs-Frontend`

- **Mallqui Vilca, Dhilsen Armil — `Dhilsen18`:** desarrolló la lógica y presentación de las vistas asociadas a planes y suscripciones. También participó en la construcción del módulo de monitoreo y en las vistas relacionadas con establecimientos.

- **Diaz Mendoza, Sebastian Victor Andre — `DiazDeveloper`:** participó en la estructuración del módulo IAM y en la definición de la interfaz visual del frontend, además de contribuir con elementos gráficos, responsive y componentes de interacción.

- **Ramirez Escalante, Carlo Patricio — `Dhilsen18`:** participó en la implementación general del frontend y en la organización de la documentación del Sprint.

- **Oblitas Alcalde, Rodrigo — `DiazDeveloper`:** apoyó la implementación del módulo de logística y transportes, además de participar en la construcción y adaptación visual de componentes.

- **Dinklange Arevalo, Sandro — `Dhilsen18`:** participó en las actividades de revisión, documentación, pruebas y soporte a la integración de los módulos desarrollados.

**Repositorio del Reporte:** `KairoLabs-Project-Report`

El equipo coordinó la elaboración del reporte de manera conjunta, manteniendo la correspondencia entre las tareas registradas en Trello, los cambios realizados en GitHub y las evidencias del producto.

**Repositorio de Landing Page:** `KairoLabs-Landing-Page`

La Landing Page continuó siendo mantenida y desplegada durante esta etapa, conservando la base visual y comunicacional establecida durante el Sprint 1.

En conjunto, la colaboración del Sprint 2 permitió avanzar desde la Landing Page hacia una primera versión funcional de la aplicación web, manteniendo una distribución de responsabilidades por módulos y una estrategia de integración basada en GitFlow.


### 5.2.3. Sprint 3

En esta sección se registra y explica el avance en términos de producto backend y trabajo colaborativo para el Sprint 3. Durante esta iteración, el equipo tuvo como objetivo principal implementar los Web Services y la API RESTful de KairoLabs, desarrollando los endpoints necesarios para los principales bounded contexts de la plataforma.

El trabajo se concentró en los módulos de IAM, Monitoring, Establishments, Subscriptions y Logistics, incorporando persistencia de datos, autenticación, operaciones CRUD y documentación mediante OpenAPI/Swagger.

---

#### 5.2.3.1. Sprint Planning 3

A continuación se presenta el resumen del Sprint Planning Meeting realizado para el Sprint 3.

| Sprint # | Sprint 3 |
| :--- | :--- |
| **Sprint Planning Background** |  |
| **Date** | 2026-06-12 |
| **Time** | Según planificación del Sprint |
| **Location** | Reunión virtual |
| **Prepared By** | *(completar: integrante del equipo)* |
| **Attendees** | Mallqui Vilca, Dhilsen Armil / *(completar: integrante del equipo)* / *(completar: integrante del equipo)* |
| **Sprint Goal & User Stories** |  |
| **Sprint 3 Goal** | Our goal is to develop the backend API and web services for the KairoLabs platform. We believe that this implementation will provide the core functionality required by the frontend application, enabling data persistence, authentication, and RESTful API endpoints for managing subscriptions, devices, establishments, operators, and logistics. This will be confirmed once all microservices are deployed and integrated with the frontend application. |
| **Sprint 3 Velocity** | 18 |
| **Sum of Story Points** | 18 |

El Sprint 3 representó el paso de una aplicación frontend basada en mocks hacia la implementación de los servicios backend necesarios para soportar la persistencia y gestión de información de KairoLabs.

---

#### 5.2.3.2. Aspect Leaders and Collaborators

En esta sección se detalla la matriz de liderazgo y colaboración (LACX) para el Sprint 3. Cada aspecto representa una fase crítica de la entrega del backend, donde se designa un líder (L) responsable de la dirección del entregable y colaboradores (C) que apoyaron en su ejecución.

| Team Member (Last Name, First Name) | GitHub Username | Backend Architecture | IAM Module | Subscriptions Module | Monitoring Module | Establishments Module | Logistics Module | Database Design | Services Deployment |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| *(completar: integrante del equipo)* | completar-integrante | **L** | **L** | C | **L** | **L** | C | **L** | C |
| Mallqui Vilca, Dhilsen Armil | `Dhilsen18` | C | C | **L** | C | C | C | C | C |
| *(completar: integrante del equipo)* | completar-integrante | C | C | C | C | C | **L** | C | **L** |

**Sustento de los Aspectos de Liderazgo:**

- ***(completar: integrante del equipo) — Backend Architecture, IAM, Monitoring, Establishments & Database:* lideró la arquitectura general de microservicios, la implementación del módulo de autenticación, el diseño de la base de datos relacional y los endpoints relacionados con dispositivos y establecimientos.

- **Mallqui Vilca, Dhilsen Armil — Subscriptions Module:** fue responsable de la implementación de la lógica de planes de suscripción, integrando endpoints para la creación, consulta y eliminación de suscripciones vinculadas a administradores.

- ***(completar: integrante del equipo) — Logistics Module & Services Deployment:* lideró la implementación de los endpoints de logística y transportes, además de coordinar el despliegue en Render y la configuración de infraestructura.

---

#### 5.2.3.3. Sprint Backlog 3

Durante el tercer Sprint, el equipo tuvo como objetivo principal implementar los Web Services y la API RESTful de KairoLabs, completando los endpoints principales para las cinco áreas funcionales del sistema.

Para la organización y gestión se utilizó Trello, permitiendo dividir las tareas de desarrollo backend en incrementos manejables y asignarlas según la especialidad técnica de cada integrante.

![Sprint Backlog 3 Trello](../assets/sprint-backlog-3-trello.png)

**Enlace de Trello:**

https://trello.com/invite/b/6a2997ef988f03df0e99f5ba/ATTIe7076c2890011c022be6d9d46ec8740b24ABF214/sprint-3

| Sprint # | Sprint 3 | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **User Story / Endpoint** | | **Work-Item / Task** | | | | | |
| **Id** | **Title** | **Id** | **Title** | **Description** | **Estimation (Hours)** | **Assigned To** | **Status** |
| EP01 | GET /api/v1/admins | TS-EP01-001 | Implementar endpoint GET Admins | Desarrollar endpoint para listar administradores | 4 | *(completar: integrante del equipo)* | Done |
| EP02 | POST /api/v1/admins | TS-EP02-001 | Implementar endpoint POST Admins | Desarrollar endpoint para crear nuevo administrador | 6 | *(completar: integrante del equipo)* | Done |
| EP03 | GET /api/v1/devices | TS-EP03-001 | Implementar endpoint GET Devices | Desarrollar endpoint para listar dispositivos | 4 | *(completar: integrante del equipo)* | Done |
| EP04 | POST /api/v1/devices | TS-EP04-001 | Implementar endpoint POST Devices | Desarrollar endpoint para crear nuevo dispositivo | 6 | *(completar: integrante del equipo)* | Done |
| EP05 | PUT /api/v1/devices/{id}/sensor-data | TS-EP05-001 | Implementar endpoint PUT Sensor Data | Desarrollar endpoint para actualizar datos de sensores | 6 | Mallqui Vilca, Dhilsen Armil | Done |
| EP06 | DELETE /api/v1/devices/{id} | TS-EP06-001 | Implementar endpoint DELETE Devices | Desarrollar endpoint para eliminar dispositivo | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| EP07 | GET /api/v1/establishments | TS-EP07-001 | Implementar endpoint GET Establishments | Desarrollar endpoint para listar establecimientos | 4 | *(completar: integrante del equipo)* | Done |
| EP08 | POST /api/v1/establishments | TS-EP08-001 | Implementar endpoint POST Establishments | Desarrollar endpoint para crear establecimiento | 6 | Mallqui Vilca, Dhilsen Armil | Done |
| EP09 | DELETE /api/v1/establishments/{id} | TS-EP09-001 | Implementar endpoint DELETE Establishments | Desarrollar endpoint para eliminar establecimiento | 4 | *(completar: integrante del equipo)* | Done |
| EP10 | GET /api/v1/operators | TS-EP10-001 | Implementar endpoint GET Operators | Desarrollar endpoint para listar operadores | 4 | *(completar: integrante del equipo)* | Done |
| EP11 | POST /api/v1/operators | TS-EP11-001 | Implementar endpoint POST Operators | Desarrollar endpoint para crear operador | 6 | *(completar: integrante del equipo)* | Done |
| EP12 | PUT /api/v1/operators/{id} | TS-EP12-001 | Implementar endpoint PUT Operators | Desarrollar endpoint para actualizar operador | 5 | Mallqui Vilca, Dhilsen Armil | Done |
| EP13 | DELETE /api/v1/operators/{id} | TS-EP13-001 | Implementar endpoint DELETE Operators | Desarrollar endpoint para eliminar operador | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| EP14 | PUT /api/v1/operators/{id}/alert-answered | TS-EP14-001 | Implementar endpoint PUT Alert Answered | Desarrollar endpoint para incrementar conteo de alertas respondidas | 5 | *(completar: integrante del equipo)* | Done |
| EP15 | GET /api/v1/subscriptions | TS-EP15-001 | Implementar endpoint GET Subscriptions | Desarrollar endpoint para recuperar lista de suscripciones | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| EP16 | POST /api/v1/subscriptions | TS-EP16-001 | Implementar endpoint POST Subscriptions | Desarrollar endpoint para crear nueva suscripción | 6 | *(completar: integrante del equipo)* | Done |
| EP17 | DELETE /api/v1/subscriptions/{id} | TS-EP17-001 | Implementar endpoint DELETE Subscriptions | Desarrollar endpoint para eliminar suscripción | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| EP18 | GET /api/v1/transports | TS-EP18-001 | Implementar endpoint GET Transports | Desarrollar endpoint para listar transportes | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| EP19 | POST /api/v1/transports | TS-EP19-001 | Implementar endpoint POST Transports | Desarrollar endpoint para crear transporte | 6 | *(completar: integrante del equipo)* | Done |
| EP20 | PUT /api/v1/transports/{id}/sensor-data | TS-EP20-001 | Implementar endpoint PUT Transport Sensor Data | Desarrollar endpoint para actualizar datos de sensores en transporte | 6 | *(completar: integrante del equipo)* | Done |
| EP21 | DELETE /api/v1/transports/{id} | TS-EP21-001 | Implementar endpoint DELETE Transports | Desarrollar endpoint para eliminar transporte | 4 | *(completar: integrante del equipo)* | Done |
| EP22 | GET /api/v1/users | TS-EP22-001 | Implementar endpoint GET Users | Desarrollar endpoint para listar usuarios | 4 | *(completar: integrante del equipo)* | Done |
| EP23 | POST /api/v1/users | TS-EP23-001 | Implementar endpoint POST SignUp | Desarrollar endpoint para registrar nuevos usuarios | 6 | *(completar: integrante del equipo)* | Done |
| EP24 | POST /api/v1/users/sign-in | TS-EP24-001 | Implementar endpoint POST SignIn | Desarrollar endpoint para autenticación y generación JWT | 6 | Mallqui Vilca, Dhilsen Armil | Done |
| EP25 | DELETE /api/v1/users/{id} | TS-EP25-001 | Implementar endpoint DELETE Users | Desarrollar endpoint para eliminar usuario | 4 | *(completar: integrante del equipo)* | Done |

---

#### 5.2.3.4. Development Evidence for Sprint Review

Durante el Sprint 3, el equipo de backend utilizó GitHub como sistema de control de versiones, siguiendo la estrategia **GitFlow** con branches por bounded context.

El repositorio `KairoLabs-Backend` es privado; por ello, la evidencia principal de desarrollo se documenta mediante el despliegue en Render, la especificación OpenAPI en Swagger y la verificación de endpoints en producción.

**Repository:**

`1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Backend`

**Evidencia de despliegue y documentación:**

| Evidencia | URL / descripción | Fecha |
| :--- | :--- | :--- |
| Swagger UI (OpenAPI 3.0) | https://kairolabs-platform.onrender.com/swagger/index.html | 23/06/2026 |
| API en producción | `kairolabs-platform.onrender.com` | 23/06/2026 |
| Base de datos PostgreSQL | Filess.io — persistencia de entidades IAM, dispositivos, establecimientos, operadores, suscripciones y transportes | 23/06/2026 |

**Endpoints implementados y verificados mediante Swagger:**

| Módulo | Endpoints | Métodos |
| :--- | :--- | :--- |
| IAM | `/api/v1/users`, `/api/v1/users/sign-in`, `/api/v1/admins` | GET, POST, DELETE |
| Monitoring | `/api/v1/devices`, `/api/v1/devices/{id}/sensor-data` | GET, POST, PUT, DELETE |
| Establishments | `/api/v1/establishments` | GET, POST, DELETE |
| Subscriptions | `/api/v1/subscriptions` | GET, POST, DELETE |
| Logistics | `/api/v1/operators`, `/api/v1/transports` | GET, POST, PUT, DELETE |

La evidencia demuestra la implementación de los servicios backend correspondientes a los bounded contexts definidos para la plataforma.

---

#### 5.2.3.5. Execution Evidence for Sprint Review

Después de finalizar el Sprint 3, se implementó la versión inicial del backend de KairoLabs con los principales endpoints funcionando.

Esta entrega consolida los Web Services necesarios para integrar la aplicación frontend con la base de datos persistente, permitiendo operaciones CRUD en los cinco módulos principales del sistema.

**Enlace de despliegue:**

https://kairolabs-platform.onrender.com/swagger/index.html

**Endpoints implementados y funcionales:**

- `POST /api/v1/subscriptions` — Creación de suscripciones.
- `POST /api/v1/devices` — Registro de dispositivos de monitoreo.
- `PUT /api/v1/devices/{id}/sensor-data` — Actualización de datos de sensores.
- `POST /api/v1/users/sign-in` — Autenticación de usuarios con JWT.
- `POST /api/v1/establishments` — Creación de establecimientos.
- `DELETE /api/v1/establishments/{id}` — Eliminación de establecimientos.
- `GET /api/v1/operators` — Consulta de operadores del sistema.
- `PUT /api/v1/operators/{id}` — Actualización de información de operadores.

La ejecución de estos servicios permitió establecer la base backend sobre la cual posteriormente se realizaría la integración con la aplicación frontend.

---

#### 5.2.3.6. Services Documentation Evidence for Sprint Review

Durante el Sprint 3 se generó la documentación de los servicios mediante **OpenAPI/Swagger**.

La especificación técnica contempla los siguientes elementos:

- **Autenticación:** esquema JWT Bearer mediante headers.
- **Validación:** reglas de negocio y restricciones de datos.
- **Respuestas:** códigos HTTP y formatos de payload según REST standards.
- **Modelos:** definiciones de entidades y value objects del dominio.

La documentación interactiva se encuentra disponible en Swagger UI:

https://kairolabs-platform.onrender.com/swagger/index.html

Esta documentación permite consultar los endpoints disponibles, revisar sus parámetros y estructuras de respuesta y realizar pruebas manuales de los servicios.

---

#### 5.2.3.7. Software Deployment Evidence for Sprint Review

El despliegue del backend de KairoLabs se realizó utilizando **Render** para el Web Service y **Filess.io** para la base de datos relacional.

##### 1. Database Configuration — Filess.io

Se configuró una base de datos PostgreSQL remota en Filess.io.

![Database Configuration Filess](../assets/database-filess-config.png)

*Figura 5.2.3.7-1. Configuración de credenciales de base de datos en Filess.io.*

**Configuración registrada:**

- **Host:** `ryne-j.h.filess.io`
- **Port:** `3306`
- **Database:** `medi_track_sensor_db_homeworth`
- **User:** `medi_track_sensor_db_homeworth`

##### 2. Web Service Deployment — Render

Se creó un Web Service en Render conectado al repositorio backend.

![Render Web Service Configuration](../assets/render-new-web-service.png)

*Figura 5.2.3.7-2. Panel de creación del Web Service en Render.*

**Configuración:**

- **Name:** `kairolabs-platform`
- **Runtime:** Docker
- **Source Code Repository:** `1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Backend`
- **Branch:** `master`
- **Region:** Virginia (US East)
- **Instance Type:** Free plan with upgradeable capacity

##### 3. Deployment Status

El servicio fue desplegado en Render.

![Render Deployment Status](../assets/render-deployment-status.png)

*Figura 5.2.3.7-3. Estado de deployment del backend en Render.*

**Datos registrados:**

- **Service Name:** `kairolabs-platform`
- **Status:** Deployed
- **Runtime:** Docker
- **Region:** Virginia

##### 4. Environment Variables Configuration

Se configuraron variables de entorno para permitir la conexión del backend con la base de datos.

![Render Environment Variables](../assets/render-env-variables.png)

*Figura 5.2.3.7-4. Variables de entorno configuradas en Render.*

Entre las variables configuradas se encuentran:

- `DATABASE_HOST`
- `DATABASE_PORT`
- `DATABASE_NAME`
- `DATABASE_USER`
- `DATABASE_PASSWORD`
- Variables adicionales relacionadas con la configuración de seguridad y autenticación.

##### 5. API Documentation & Swagger UI

El backend se documentó mediante Swagger/OpenAPI.

![Swagger API Documentation](../assets/swagger-api-docs.png)

*Figura 5.2.3.7-5. Documentación interactiva de API en Swagger UI.*

**URL de producción:**

https://kairolabs-platform.onrender.com/swagger/index.html

**Endpoints desplegados y accesibles:**

- `POST /api/v1/subscriptions`
- `POST /api/v1/devices`
- `PUT /api/v1/devices/{id}/sensor-data`
- `POST /api/v1/users/sign-in`
- `POST /api/v1/establishments`
- `DELETE /api/v1/establishments/{id}`
- `GET /api/v1/operators`
- `PUT /api/v1/operators/{id}`

**Deployment Summary:**

| Componente | Plataforma | Status | URL |
| :--- | :--- | :--- | :--- |
| Backend API | Render | Active | https://kairolabs-platform.onrender.com |
| Swagger UI | Render | Active | https://kairolabs-platform.onrender.com/swagger/index.html |
| Database | Filess.io | Connected | PostgreSQL |
| Repository | GitHub | Linked | `KairoLabs-Backend` |
| CI/CD | Render | Auto-Deploy | Automatic on push to master |

---

#### 5.2.3.8. Team Collaboration Insights during Sprint

En esta sección se evidencia la colaboración del equipo durante el Sprint 3 en el desarrollo del backend de KairoLabs, con una distribución de módulos por bounded context y responsabilidades técnicas.

**Repositorio de Backend:** `KairoLabs-Backend`

- ***(completar: integrante del equipo) — IAM & Backend Architecture:* lideró la arquitectura general de microservicios y la implementación del módulo de autenticación, estableciendo patrones de seguridad y estructuras de control.

- **Mallqui Vilca, Dhilsen Armil — Subscriptions Module:** implementó los endpoints de gestión de planes de suscripción, asegurando persistencia y validación de datos.

- ***(completar: integrante del equipo) — Monitoring Module & Database Design:* diseñó la estructura de la base de datos relacional e implementó los endpoints correspondientes a dispositivos, establecimientos y datos de sensores.

- ***(completar: integrante del equipo) — Logistics Module & Deployment:* implementó los endpoints relacionados con operadores y transportes, además de coordinar la estrategia de deployment en Render.

### Contribuciones y Participación

El equipo mantuvo comunicación mediante Discord y reuniones sincrónicas, colaborando en diferentes actividades técnicas:

- Code reviews antes de realizar merges hacia `develop`.
- Resolución de conflictos Git en features complejas.
- Testing manual de endpoints mediante Postman y Swagger UI.
- Documentación de cambios mediante Conventional Commits.
- Coordinación entre los módulos backend y el frontend desarrollado durante el Sprint 2.

En conjunto, el Sprint 3 permitió consolidar las bases técnicas del backend y establecer los servicios necesarios para la posterior integración con el frontend, manteniendo la organización del desarrollo mediante bounded contexts y GitFlow.


### 5.2.4. Sprint 4

En esta sección se registra y explica el avance correspondiente al Sprint 4, orientado a la integración final del producto KairoLabs. Durante esta iteración, el equipo concentró sus actividades en finalizar los servicios backend, integrar la aplicación frontend con la API REST, validar la persistencia de datos, completar la documentación de servicios y realizar el despliegue final del ecosistema.

El Sprint 4 permitió consolidar los componentes desarrollados durante los Sprints anteriores, integrando la Landing Page, la Web Application, la RESTful API y la base de datos PostgreSQL en un entorno de producción.

---

#### 5.2.4.1. Sprint Planning 4

A continuación se presenta el resumen del Sprint Planning Meeting realizado para el Sprint 4.

| Sprint # | Sprint 4 |
| :--- | :--- |
| **Sprint Planning Background** |  |
| **Date** | 2026-07-05 |
| **Time** | Reunión virtual |
| **Location** | Reunión virtual |
| **Prepared By** | Diaz Mendoza, Sebastian Victor Andre |
| **Attendees** | Mallqui Vilca, Dhilsen Armil / Diaz Mendoza, Sebastian Victor Andre / Ramirez Escalante, Carlo Patricio / Oblitas Alcalde, Rodrigo / Dinklange Arevalo, Sandro |
| **Sprint Goal & User Stories** |  |
| **Sprint 4 Goal** | Our goal is to finalize the backend API and web services for the KairoLabs platform, and ensure their seamless integration with the frontend application. We believe that uniting these components will deliver a complete and functional ecosystem, enabling data persistence, authentication, and RESTful API endpoints for managing subscriptions, devices, establishments, operators, and logistics. This will be confirmed once both the frontend and all backend microservices are correctly deployed, connected, and fully operational. |
| **Sprint 4 Velocity** | 16 |
| **Sum of Story Points** | 16 |

El objetivo principal del Sprint 4 fue completar la integración full-stack de KairoLabs. Para ello, se consideraron actividades relacionadas con la conexión del frontend con la API, validación de autenticación, verificación de operaciones CRUD, finalización de endpoints, documentación OpenAPI, persistencia de datos y despliegue de los componentes en producción.

---

#### 5.2.4.2. Aspect Leaders and Collaborators

En esta sección se presenta la matriz de liderazgo y colaboración (LACX) correspondiente al Sprint 4. Cada aspecto representa una actividad relevante para el cierre del producto, asignando un líder (L) y colaboradores (C) de acuerdo con las responsabilidades distribuidas durante el Sprint.

| Team Member (Last Name, First Name) | GitHub Username | Backend Finalization | Frontend Integration | Database Optimization | Services Documentation | Full-Stack Deployment | Report & Conclusions |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Mallqui Vilca, Dhilsen Armil | `Dhilsen18` | C | **L** | C | C | **L** | C |
| Diaz Mendoza, Sebastian Victor Andre | `DiazDeveloper` | **L** | C | C | **L** | C | C |
| Ramirez Escalante, Carlo Patricio | `Dhilsen18` | C | C | **L** | C | C | C |
| Oblitas Alcalde, Rodrigo | `DiazDeveloper` | C | C | C | C | **L** | **L** |
| Dinklange Arevalo, Sandro | `Dhilsen18` | C | C | C | C | C | **L** |

**Sustento de los Aspectos de Liderazgo:**

- **Mallqui Vilca, Dhilsen Armil — Frontend Integration & Full-Stack Deployment:** lideró las actividades relacionadas con la conexión de la aplicación frontend con la API REST desplegada en Render, así como la validación de los flujos de autenticación y navegación entre los diferentes módulos.

- **Diaz Mendoza, Sebastian Victor Andre — Backend Finalization & Services Documentation:** lideró la finalización de los endpoints pendientes del backend y la documentación de los servicios mediante Swagger/OpenAPI.

- **Ramirez Escalante, Carlo Patricio — Database Optimization:** participó en la validación de las relaciones entre las entidades y en las actividades relacionadas con la persistencia de información en PostgreSQL.

- **Oblitas Alcalde, Rodrigo — Full-Stack Deployment & Report:** lideró actividades relacionadas con el despliegue final y la consolidación de evidencias utilizadas en el informe del proyecto.

- **Dinklange Arevalo, Sandro — Report & Conclusions:** participó en la organización de la documentación final, actualización del informe y elaboración de las conclusiones correspondientes al cierre del proyecto.

La distribución de responsabilidades permitió mantener una participación colaborativa durante el Sprint, evitando concentrar todas las actividades en un único integrante y facilitando la integración entre frontend, backend, base de datos y documentación.

---

#### 5.2.4.3. Sprint Backlog 4

![Sprint Backlog 4 Trello](../assets/sprint-backlog-4-trello.png)

**Enlace de Trello:**

https://trello.com/invite/b/6a4aec825530c3b6ab9db1b7/ATTI2034d17571ccf6acbefeae2e9ecfb71e4BAC22E5/sprint-4

Durante el Sprint 4, el equipo priorizó la integración full-stack y el cierre del ciclo de vida del proyecto. Las actividades fueron organizadas en tareas relacionadas con la integración del frontend, finalización del backend, persistencia de datos, despliegue y documentación.

| Sprint # | Sprint 4 | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **User Story / Objetivo** | | **Work-Item / Task** | | | | | |
| **Id** | **Title** | **Id** | **Title** | **Description** | **Estimation (Hours)** | **Assigned To** | **Status** |
| INT01 | Integración full-stack | T01 | Configurar URL de API en frontend | Conectar `VITE_API_BASE_URL` al backend en Render | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| INT02 | Integración full-stack | T02 | Validar flujo de autenticación | Probar login, JWT y redirección post sign-in | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| INT03 | Integración full-stack | T03 | Validar módulos CRUD en frontend | Verificar establecimientos, dispositivos, operadores y transportes | 6 | Mallqui Vilca, Dhilsen Armil | Done |
| API01 | Finalización backend | T04 | Completar endpoints pendientes | Finalizar endpoints REST de todos los bounded contexts | 8 | Diaz Mendoza, Sebastian Victor Andre | Done |
| API02 | Finalización backend | T05 | Documentar API en Swagger | Completar especificación OpenAPI de todos los servicios | 4 | Diaz Mendoza, Sebastian Victor Andre | Done |
| DB01 | Persistencia de datos | T06 | Optimizar esquema de base de datos | Validar relaciones y persistencia en Filess.io | 4 | Ramirez Escalante, Carlo Patricio | Done |
| DEP01 | Despliegue producción | T07 | Desplegar frontend final en Vercel | Publicar versión integrada con API en producción | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| DEP02 | Despliegue producción | T08 | Desplegar backend final en Render | Verificar pipeline CI/CD y variables de entorno | 4 | Oblitas Alcalde, Rodrigo | Done |
| DOC01 | Cierre del proyecto | T09 | Actualizar informe TB2 | Registro de versiones, Student Outcome y Sprint 4 | 6 | Dinklange Arevalo, Sandro | Done |
| DOC02 | Cierre del proyecto | T10 | Redactar conclusiones finales | Conclusiones, recomendaciones y validación del producto | 4 | Oblitas Alcalde, Rodrigo / Dinklange Arevalo, Sandro | Done |

El Sprint Backlog permitió organizar las actividades de cierre en cuatro grupos principales: integración frontend-backend, finalización de servicios, persistencia y despliegue, y documentación final.

---

#### 5.2.4.4. Development Evidence for Sprint Review

Durante el Sprint 4, el equipo consolidó la integración entre los tres repositorios de producto y el repositorio del informe.

Las evidencias de desarrollo muestran cambios realizados tanto en el frontend como en la documentación del proyecto. Los commits utilizaron mensajes descriptivos siguiendo la convención empleada durante el desarrollo.

##### Repository — Project Report

**Repository:**

`1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Project-Report`

| Repository | Branch | Commit Id | Commit Message | Committed on (Date) |
| :--- | :--- | :--- | :--- | :--- |
| `KairoLabs-Project-Report` | `main` | `970794a` | `fix(main): update version project` | 05/07/2026 |
| `KairoLabs-Project-Report` | `main` | `908a6f2` | `add: include evidence and links for Sprint 4 frontend and backend deployments` | 05/07/2026 |
| `KairoLabs-Project-Report` | `main` | `b777a05` | `docs: add Sprint 4 details including planning, backlog, and collaboration insights` | 05/07/2026 |

##### Repository — Frontend

**Repository:**

`1ASI0732-2610-9082-TBL-KairoLabs/KairoLabs-Frontend`

| Repository | Branch | Commit Id | Commit Message | Committed on (Date) |
| :--- | :--- | :--- | :--- | :--- |
| `KairoLabs-Frontend` | `main` | `705a464` | `feat: connect control center to API and fix transport registration` | 05/07/2026 |
| `KairoLabs-Frontend` | `main` | `e048b3f` | `fix: treat billing as design-only mock gateway separate from API sign-up` | 05/07/2026 |
| `KairoLabs-Frontend` | `main` | `48bc7d2` | `fix: register health entity in single POST /users call` | 04/07/2026 |
| `KairoLabs-Frontend` | `main` | `ebb2ced` | `feat: improve UX with sidebar, semantic routes, delete devices and map filters` | 04/07/2026 |
| `KairoLabs-Frontend` | `main` | `f39624a` | `refactor(iam): align IAM bounded context with learning-center DDD pattern` | 01/07/2026 |

Los cambios registrados evidencian la integración progresiva entre el frontend y los servicios backend, incluyendo la conexión con la API, la corrección del registro de entidades, la mejora de navegación y la organización de las rutas de la aplicación.

##### Repositorios de producto

| Producto | Repositorio GitHub | URL de producción |
| :--- | :--- | :--- |
| Landing Page | `KairoLabs-Landing-Page` | https://KairoLabs-sensor.vercel.app/ |
| Frontend | `KairoLabs-Frontend` | https://kairolabs-frontend.vercel.app/login |
| Backend API | `KairoLabs-Backend` | https://kairolabs-platform.onrender.com/swagger/index.html |

---

#### 5.2.4.5. Execution Evidence for Sprint Review

En esta sección se documenta la ejecución del producto final integrado. Durante el Sprint 4 se validaron los principales flujos funcionales sobre los componentes desplegados.

| Flujo validado | Descripción | URL de evidencia |
| :--- | :--- | :--- |
| Login y autenticación | Acceso con credenciales y generación de sesión JWT | https://kairolabs-frontend.vercel.app/login |
| Dashboard de monitoreo | Visualización de sensores, temperatura y humedad | https://kairolabs-frontend.vercel.app/login |
| Gestión de establecimientos | CRUD de establecimientos | https://kairolabs-frontend.vercel.app/login |
| Gestión de dispositivos | Consulta y administración de dispositivos IoT | https://kairolabs-frontend.vercel.app/login |
| Gestión de operadores | Consulta y administración de operadores | https://kairolabs-frontend.vercel.app/login |
| Gestión de transportes | Consulta y gestión de transportes | https://kairolabs-frontend.vercel.app/login |
| API REST documentada | Consulta y prueba de endpoints mediante Swagger UI | https://kairolabs-platform.onrender.com/swagger/index.html |
| Landing Page final | Presentación del producto y propuesta de valor | https://KairoLabs-sensor.vercel.app/ |

**Endpoints verificados en producción:**

- `POST /api/v1/users/sign-in` — Autenticación con JWT.
- `GET /api/v1/devices` — Listado de dispositivos IoT.
- `POST /api/v1/devices` — Registro de dispositivos.
- `PUT /api/v1/devices/{id}/sensor-data` — Actualización de telemetría.
- `GET /api/v1/establishments` — Consulta de establecimientos.
- `POST /api/v1/establishments` — Creación de establecimientos.
- `GET /api/v1/operators` — Listado de operadores.
- `GET /api/v1/subscriptions` — Consulta de suscripciones.
- `GET /api/v1/transports` — Listado de transportes.

La ejecución del Sprint 4 permitió verificar la comunicación entre la aplicación frontend y la RESTful API desplegada, así como la disponibilidad de los servicios y la persistencia de información mediante PostgreSQL.

---

#### 5.2.4.6. Services Documentation Evidence for Sprint Review

La documentación completa de la API REST se encuentra disponible mediante Swagger UI, utilizando la especificación OpenAPI 3.0.

**URL:**

https://kairolabs-platform.onrender.com/swagger/index.html

| Módulo (Bounded Context) | Endpoints principales | Métodos |
| :--- | :--- | :--- |
| IAM (Users & Admins) | `/api/v1/users`, `/api/v1/users/sign-in`, `/api/v1/admins` | GET, POST, DELETE |
| Subscriptions | `/api/v1/subscriptions` | GET, POST, DELETE |
| Monitoring (Devices) | `/api/v1/devices`, `/api/v1/devices/{id}/sensor-data` | GET, POST, PUT, DELETE |
| Establishments | `/api/v1/establishments` | GET, POST, DELETE |
| Logistics (Operators & Transports) | `/api/v1/operators`, `/api/v1/transports` | GET, POST, PUT, DELETE |

La especificación de servicios incluye:

- Esquema JWT Bearer para autenticación.
- Modelos de entidades correspondientes al dominio.
- Parámetros de entrada de los endpoints.
- Estructuras de respuesta.
- Códigos HTTP utilizados por los servicios.
- Reglas de validación correspondientes a cada recurso.

La documentación interactiva permite consultar los servicios disponibles y realizar pruebas directamente sobre la API desplegada.

---

#### 5.2.4.7. Software Deployment Evidence for Sprint Review

Durante el Sprint 4 se consolidó el despliegue del ecosistema KairoLabs, compuesto por la Landing Page, la Web Application, la RESTful API y la base de datos PostgreSQL.

| Componente | Plataforma | URL | Estado |
| :--- | :--- | :--- | :--- |
| Landing Page | Vercel | https://KairoLabs-sensor.vercel.app/ | Activo |
| Web Application | Vercel | https://kairolabs-frontend.vercel.app/login | Activo |
| Backend API | Render | https://kairolabs-platform.onrender.com | Activo |
| Swagger UI | Render | https://kairolabs-platform.onrender.com/swagger/index.html | Activo |
| Base de datos | Filess.io | PostgreSQL | Conectada |

**Configuración de despliegue:**

- **Backend:** Runtime Docker en Render.
- **Backend Branch:** `master`.
- **Backend Region:** Virginia (US East).
- **Backend CI/CD:** auto-deploy desde GitHub.
- **Frontend:** aplicación Vue.js desplegada en Vercel.
- **Frontend configuration:** variable `VITE_API_BASE_URL` apuntando al backend en Render.
- **Base de datos:** PostgreSQL remota en Filess.io.
- **Database connection:** gestionada mediante variables de entorno.
- **API documentation:** Swagger/OpenAPI disponible desde el servicio desplegado.

La configuración permite mantener separados los componentes de presentación, aplicación y persistencia, facilitando la actualización independiente de cada servicio.

---

#### 5.2.4.8. Team Collaboration Insights during Sprint

En esta sección se evidencia la colaboración del equipo durante el Sprint 4, principalmente en las actividades de integración full-stack, despliegue, documentación y cierre del proyecto KairoLabs.

##### Repositorio de Frontend — `KairoLabs-Frontend`

- **Mallqui Vilca, Dhilsen Armil (`Dhilsen18`):** lideró la conexión del frontend con la API en producción y participó en la validación de los flujos de autenticación, navegación y operaciones CRUD.

- **Oblitas Alcalde, Rodrigo (`DiazDeveloper`):** colaboró en la revisión de la interfaz, consistencia de navegación y validación de los módulos integrados.

##### Repositorio de Backend — `KairoLabs-Backend`

- **Diaz Mendoza, Sebastian Victor Andre (`DiazDeveloper`):** lideró la finalización de los endpoints pendientes y la organización de la documentación de los servicios mediante Swagger/OpenAPI.

- **Ramirez Escalante, Carlo Patricio (`Dhilsen18`):** participó en la validación de la persistencia y relaciones de las entidades utilizadas por los servicios backend.

- **Dinklange Arevalo, Sandro (`Dhilsen18`):** colaboró en las pruebas funcionales de los servicios y en la revisión de la integración entre backend y frontend.

##### Repositorio del Reporte — `KairoLabs-Project-Report`

- **Oblitas Alcalde, Rodrigo (`DiazDeveloper`):** participó en la consolidación de las evidencias correspondientes al Sprint 4.

- **Dinklange Arevalo, Sandro (`Dhilsen18`):** participó en la actualización de la documentación, conclusiones y organización final del informe.

##### Coordinación del equipo

Durante el Sprint 4, el equipo mantuvo coordinación mediante reuniones virtuales y comunicación sincrónica para organizar las actividades de integración y cierre.

Las principales actividades colaborativas fueron:

- Revisión de cambios antes de realizar merges.
- Validación conjunta de los flujos de autenticación.
- Pruebas de los módulos CRUD del frontend.
- Verificación de los endpoints mediante Swagger.
- Revisión de la conexión entre frontend, backend y PostgreSQL.
- Validación del despliegue en Vercel y Render.
- Consolidación de evidencias para el informe final.
- Organización de las conclusiones y documentación correspondiente al Sprint 4.

En conjunto, el Sprint 4 permitió integrar los componentes desarrollados durante las iteraciones anteriores y consolidar el producto KairoLabs en un entorno desplegado, conectando la aplicación frontend con la RESTful API y la base de datos PostgreSQL.


### 5.2.2. Implemented Landing Page Evidence

**(Anexar evidencias)**

---

### 5.2.3. Implemented Frontend-Web Application Evidence

**(Anexar evidencias)**

---

### 5.2.4. Acuerdo de Servicio - SaaS

KairoLabs plantea su producto bajo un modelo de **Software as a Service (SaaS)**, mediante el cual los usuarios pueden acceder a la plataforma web para gestionar y supervisar información relacionada con el monitoreo de las condiciones de almacenamiento y transporte de medicamentos.

La solución contempla un modelo de suscripción orientado principalmente a entidades de salud y gestores farmacéuticos, permitiendo utilizar las funcionalidades de la plataforma mediante un navegador web, sin requerir la instalación local del sistema.

#### Descripción del servicio

KairoLabs proporciona una plataforma digital compuesta por una **Landing Page**, una **Web Application** y servicios backend que permiten gestionar información relacionada con establecimientos, dispositivos, operadores, transportes y suscripciones.

El acceso a la aplicación se realiza mediante navegador web y la información es gestionada mediante los servicios RESTful implementados por la plataforma.

#### Modalidad de servicio

| Característica | Descripción |
| :--- | :--- |
| **Modelo** | Software as a Service (SaaS) |
| **Acceso** | Mediante navegador web |
| **Aplicación web** | Vue.js |
| **Backend** | ASP.NET Core / C# |
| **Base de datos** | PostgreSQL |
| **API** | RESTful API |
| **Autenticación** | JWT |
| **Despliegue frontend** | Vercel |
| **Despliegue backend** | Render |
| **Persistencia** | Filess.io |
| **Modalidad de uso** | Suscripción |

#### Planes de suscripción

La propuesta comercial de KairoLabs contempla diferentes niveles de suscripción, permitiendo adaptar el servicio a las necesidades de las entidades usuarias.

| Plan | Descripción |
| :--- | :--- |
| **Básico** | Acceso a las funcionalidades esenciales de monitoreo y gestión de información. |
| **Profesional** | Acceso ampliado a funcionalidades de gestión y monitoreo de la plataforma. |
| **Premium** | Acceso a las funcionalidades disponibles para una gestión más completa del sistema. |

El proyecto considera como referencia un modelo de suscripción mensual escalable. Durante la validación del proyecto se consideró un rango aproximado de **S/ 100 a S/ 200 mensuales**, sujeto a las características y alcance del servicio contratado.

#### Alcance del servicio

El servicio contempla el acceso a las funcionalidades implementadas en la plataforma:

- Autenticación de usuarios.
- Gestión de establecimientos.
- Gestión de dispositivos.
- Monitoreo de información proveniente de sensores.
- Gestión de operadores.
- Gestión de transportes.
- Gestión de suscripciones.
- Visualización de información mediante dashboard.
- Acceso a los servicios RESTful de la plataforma.

#### Disponibilidad del servicio

La plataforma se encuentra desplegada utilizando servicios cloud, permitiendo acceder a los componentes principales del sistema mediante Internet.

| Componente | Servicio utilizado |
| :--- | :--- |
| **Landing Page** | Vercel |
| **Web Application** | Vercel |
| **RESTful API** | Render |
| **Base de datos** | Filess.io |

El modelo SaaS permite que las actualizaciones de la plataforma se realicen sobre una infraestructura centralizada, evitando que cada usuario tenga que instalar manualmente nuevas versiones de la aplicación.

#### Acceso y seguridad

El acceso a la Web Application se realiza mediante autenticación de usuarios. La API utiliza autenticación mediante **JWT Bearer**, mientras que las credenciales y parámetros de conexión utilizados por los servicios se gestionan mediante variables de entorno.

De esta manera, la información de configuración utilizada para la conexión con la base de datos y otros servicios no se almacena directamente dentro del código fuente.

#### Responsabilidades del servicio

| Parte | Responsabilidad |
| :--- | :--- |
| **KairoLabs** | Mantener la aplicación, los servicios backend y la infraestructura de base de datos utilizados por la plataforma. |
| **KairoLabs** | Mantener y actualizar los componentes de software del producto. |
| **Usuario / Entidad contratante** | Utilizar la plataforma de acuerdo con las funcionalidades y condiciones establecidas para el servicio contratado. |
| **Usuario / Entidad contratante** | Mantener bajo su responsabilidad las credenciales utilizadas para acceder a la plataforma. |

#### Condiciones del servicio

El servicio se plantea bajo una modalidad de suscripción, mediante la cual la entidad contratante obtiene acceso a las funcionalidades disponibles de KairoLabs durante el periodo correspondiente al servicio contratado.

La prestación del servicio se encuentra soportada por una infraestructura cloud compuesta por Vercel para los componentes frontend, Render para la RESTful API y Filess.io para la persistencia de datos mediante PostgreSQL.

La administración de la plataforma, actualización de sus componentes y mantenimiento de los servicios desplegados corresponde al equipo responsable de KairoLabs dentro del alcance definido para el producto.

El usuario o entidad contratante será responsable del uso adecuado de la plataforma y de la protección de las credenciales utilizadas para acceder al servicio.

El presente apartado corresponde al modelo de servicio planteado para el proyecto académico **KairoLabs**. Las condiciones comerciales, niveles de disponibilidad, términos de contratación y demás condiciones contractuales definitivas deberán establecerse formalmente en caso de una implementación comercial del servicio.

### 5.2.7. RESTful API documentation

La RESTful API de KairoLabs fue implementada utilizando **ASP.NET Core y C#**, permitiendo establecer la comunicación entre la Web Application y los servicios backend de la plataforma.

La documentación de los servicios se realizó mediante **OpenAPI/Swagger**, proporcionando una interfaz interactiva para consultar los endpoints disponibles, sus parámetros, modelos de datos y respuestas.

**Documentación de la API:**

https://kairolabs-platform.onrender.com/swagger/index.html

#### Organización de los servicios

La API se encuentra organizada de acuerdo con los principales bounded contexts definidos para KairoLabs.

| Bounded Context | Endpoints principales | Métodos |
| :--- | :--- | :--- |
| **IAM** | `/api/v1/users`, `/api/v1/users/sign-in`, `/api/v1/admins` | GET, POST, DELETE |
| **Subscriptions** | `/api/v1/subscriptions` | GET, POST, DELETE |
| **Monitoring** | `/api/v1/devices`, `/api/v1/devices/{id}/sensor-data` | GET, POST, PUT, DELETE |
| **Establishments** | `/api/v1/establishments` | GET, POST, DELETE |
| **Logistics** | `/api/v1/operators`, `/api/v1/transports` | GET, POST, PUT, DELETE |

#### IAM

El bounded context IAM concentra los servicios relacionados con usuarios y administradores.

| Método | Endpoint | Descripción |
| :--- | :--- | :--- |
| GET | `/api/v1/users` | Obtener usuarios registrados. |
| POST | `/api/v1/users` | Registrar un nuevo usuario. |
| POST | `/api/v1/users/sign-in` | Autenticar un usuario. |
| DELETE | `/api/v1/users/{id}` | Eliminar un usuario. |
| GET | `/api/v1/admins` | Obtener administradores. |
| POST | `/api/v1/admins` | Registrar un administrador. |

#### Monitoring

Este módulo proporciona servicios para administrar los dispositivos y actualizar la información obtenida de los sensores.

| Método | Endpoint | Descripción |
| :--- | :--- | :--- |
| GET | `/api/v1/devices` | Obtener dispositivos registrados. |
| POST | `/api/v1/devices` | Registrar un dispositivo. |
| PUT | `/api/v1/devices/{id}/sensor-data` | Actualizar información de sensores. |
| DELETE | `/api/v1/devices/{id}` | Eliminar un dispositivo. |

#### Establishments

Este módulo permite administrar los establecimientos asociados a la plataforma.

| Método | Endpoint | Descripción |
| :--- | :--- | :--- |
| GET | `/api/v1/establishments` | Obtener establecimientos. |
| POST | `/api/v1/establishments` | Registrar un establecimiento. |
| DELETE | `/api/v1/establishments/{id}` | Eliminar un establecimiento. |

#### Subscriptions

Este módulo permite administrar la información relacionada con los planes de suscripción.

| Método | Endpoint | Descripción |
| :--- | :--- | :--- |
| GET | `/api/v1/subscriptions` | Obtener suscripciones. |
| POST | `/api/v1/subscriptions` | Registrar una suscripción. |
| DELETE | `/api/v1/subscriptions/{id}` | Eliminar una suscripción. |

#### Logistics

El bounded context Logistics contiene los servicios relacionados con operadores y transportes.

| Método | Endpoint | Descripción |
| :--- | :--- | :--- |
| GET | `/api/v1/operators` | Obtener operadores. |
| POST | `/api/v1/operators` | Registrar un operador. |
| PUT | `/api/v1/operators/{id}` | Actualizar un operador. |
| DELETE | `/api/v1/operators/{id}` | Eliminar un operador. |
| GET | `/api/v1/transports` | Obtener transportes. |
| POST | `/api/v1/transports` | Registrar un transporte. |
| PUT | `/api/v1/transports/{id}/sensor-data` | Actualizar información de sensores del transporte. |
| DELETE | `/api/v1/transports/{id}` | Eliminar un transporte. |

#### Autenticación

La API utiliza autenticación mediante **JWT Bearer**. El proceso de autenticación se realiza mediante:

```text
POST /api/v1/users/sign-in
```

Una vez validada la información del usuario, el servicio genera el token correspondiente para permitir el acceso a los recursos protegidos.

#### Documentación OpenAPI

La documentación generada mediante Swagger permite visualizar:

- Endpoints disponibles.
- Métodos HTTP.
- Parámetros de entrada.
- Modelos de datos.
- Códigos de respuesta.
- Esquema de autenticación JWT Bearer.
- Estructuras de respuesta de los servicios.

La documentación interactiva permite consultar los servicios disponibles y realizar pruebas directamente sobre la API desplegada.

**URL de Swagger UI:**

https://kairolabs-platform.onrender.com/swagger/index.html


### 5.2.8. Team Collaboration Insights

La implementación de KairoLabs se realizó mediante un trabajo colaborativo entre los cinco integrantes del equipo. Las actividades fueron distribuidas de acuerdo con las necesidades de desarrollo, integración, despliegue, pruebas y documentación del producto.

| Integrante | GitHub | Principales actividades |
| :--- | :--- | :--- |
| **Mallqui Vilca, Dhilsen Armil** | `Dhilsen18` | Desarrollo e integración del frontend, participación en los módulos de monitoreo, establecimientos y suscripciones, integración frontend con la API y validación del despliegue. |
| **Diaz Mendoza, Sebastian Victor Andre** | `DiazDeveloper` | Desarrollo y finalización de servicios backend, implementación de endpoints REST y documentación mediante Swagger/OpenAPI. |
| **Ramirez Escalante, Carlo Patricio** | `Dhilsen18` | Apoyo en persistencia, relaciones de entidades, validación de la base de datos y pruebas de los servicios backend. |
| **Oblitas Alcalde, Rodrigo** | `DiazDeveloper` | Apoyo en integración full-stack, despliegue de servicios y consolidación de evidencias del proyecto. |
| **Dinklange Arevalo, Sandro** | `Dhilsen18` | Apoyo en pruebas funcionales, documentación, organización del informe y consolidación de resultados. |

#### Colaboración durante el desarrollo

El equipo utilizó GitHub como plataforma principal para gestionar los repositorios de código y mantener el control de versiones de los diferentes componentes del producto.

Los principales repositorios utilizados fueron:

| Producto | Repositorio |
| :--- | :--- |
| **Landing Page** | `KairoLabs-Landing-Page` |
| **Frontend Web Application** | `KairoLabs-Frontend` |
| **Backend RESTful API** | `KairoLabs-Backend` |
| **Documentación del proyecto** | `KairoLabs-Project-Report` |

Durante el desarrollo se utilizaron ramas para organizar las funcionalidades y posteriormente integrar los cambios en las ramas correspondientes.

Entre las principales actividades colaborativas realizadas se encuentran:

- Revisión de cambios antes de realizar merges.
- Resolución de conflictos durante la integración del código.
- Pruebas de los endpoints mediante Swagger.
- Validación de los flujos de autenticación.
- Pruebas de los módulos CRUD.
- Coordinación entre frontend y backend.
- Verificación de la conexión con PostgreSQL.
- Revisión del despliegue en Vercel y Render.
- Consolidación de evidencias para el informe.

#### Distribución de actividades

La participación del equipo se organizó considerando los diferentes componentes que conforman la solución KairoLabs.

| Área de trabajo | Integrantes involucrados |
| :--- | :--- |
| **Frontend Web Application** | Mallqui Vilca, Dhilsen Armil / Oblitas Alcalde, Rodrigo |
| **RESTful API y Backend** | Diaz Mendoza, Sebastian Victor Andre / Ramirez Escalante, Carlo Patricio |
| **Base de datos y persistencia** | Ramirez Escalante, Carlo Patricio / Diaz Mendoza, Sebastian Victor Andre |
| **Integración y despliegue** | Mallqui Vilca, Dhilsen Armil / Oblitas Alcalde, Rodrigo |
| **Pruebas y validación** | Dinklange Arevalo, Sandro / Ramirez Escalante, Carlo Patricio |
| **Documentación del proyecto** | Dinklange Arevalo, Sandro / Oblitas Alcalde, Rodrigo |

#### Integración de componentes

El trabajo colaborativo permitió integrar los diferentes componentes desarrollados durante los cuatro Sprints.

```text
                         KairoLabs
                             |
             +---------------+---------------+
             |                               |
        Landing Page                 Web Application
           Vercel                         Vercel
                                             |
                                             |
                                      RESTful API
                                         Render
                                             |
                                             |
                                    PostgreSQL
                                      Filess.io
```

La integración permitió conectar la interfaz desarrollada en Vue.js con los servicios RESTful desarrollados en ASP.NET Core y con la base de datos PostgreSQL.

#### Comunicación y coordinación

Durante los Sprints, el equipo mantuvo comunicación para coordinar las actividades de desarrollo, revisar avances y resolver problemas relacionados con la integración de los componentes.

Las actividades colaborativas incluyeron:

- Coordinación de tareas correspondientes a cada Sprint.
- Revisión de avances de los diferentes componentes.
- Integración de funcionalidades desarrolladas individualmente.
- Validación de la comunicación entre frontend y backend.
- Pruebas de los servicios RESTful.
- Revisión del despliegue de los componentes.
- Organización de las evidencias correspondientes al proyecto.
- Actualización colaborativa de la documentación.

La organización mediante Sprints permitió distribuir progresivamente las actividades del proyecto:

| Sprint | Principal resultado |
| :--- | :--- |
| **Sprint 1** | Desarrollo y despliegue de la Landing Page. |
| **Sprint 2** | Desarrollo de la primera versión de la Web Application. |
| **Sprint 3** | Implementación de la RESTful API y servicios backend. |
| **Sprint 4** | Integración full-stack, validación y despliegue final. |

En conjunto, la colaboración del equipo permitió integrar los componentes desarrollados durante los cuatro Sprints y consolidar la solución KairoLabs como un producto compuesto por una Landing Page, una Web Application, una RESTful API y una base de datos PostgreSQL.


### 5.3. Video About-the-Product

El video del producto presenta el funcionamiento general de KairoLabs y permite evidenciar los principales componentes implementados durante el desarrollo del proyecto.

La demostración comprende los principales flujos y funcionalidades desarrollados durante los cuatro Sprints, mostrando la integración entre la Landing Page, la Web Application y los servicios backend de la plataforma.

**Video del producto:**

(Anexar enlace o evidencia del video)



