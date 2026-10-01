# Capítulo V: Product Implementation

En este capítulo se presenta la implementación y el despliegue de los productos digitales que conforman **KairoLabs**, desarrollados por el equipo **Aether System** durante el **Sprint 1** del ciclo académico **2026-20** (curso 1ASI0732 – Diseño de Experimentos de Ingeniería de Software).

Se documenta la configuración del entorno de desarrollo, la gestión del código fuente, las convenciones de codificación y la configuración de despliegue. Luego se presentan las evidencias de implementación de cada producto: **Landing Page**, **Frontend Web Application**, **Native-Mobile Application** (primer incremento) y **RESTful API**, junto con el Acuerdo de Servicio SaaS, la documentación de la API y los insights de colaboración del equipo.

Todos los repositorios del producto se encuentran en la organización de GitHub [`1ASI0732-2620-9082-Aether-System`](https://github.com/1ASI0732-2620-9082-Aether-System).

| Producto | URL pública | Repositorio |
| :--- | :--- | :--- |
| Landing Page | https://landing-page-kairolabs.vercel.app | [`KairoLabs-Landing-Page`](https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Landing-Page) |
| Frontend Web Application | https://kairo-labs-frontend.vercel.app | [`KairoLabs-Frontend`](https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Frontend) |
| Native-Mobile Application (incremento 1) | Ejecución local (`npm run dev`) | [`KairoLabs-Mobile`](https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Mobile) |
| RESTful API (Swagger UI) | https://medi-track-sensor-platform.onrender.com/swagger/index.html | [`KairoLabs-Platform`](https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Platform) |
| Project Report | — | [`KairoLabs-Project-Report`](https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Project-Report) |

---

## 5.1. Software Configuration Management

La gestión de configuración de software permite que los cinco integrantes del equipo trabajen sobre entornos, herramientas y convenciones comunes, manteniendo la trazabilidad de los cambios realizados sobre cada producto. En esta sección se describen las herramientas utilizadas, la estrategia de control de versiones, las convenciones de estilo y la configuración de despliegue.

### 5.1.1. Software Development Environment Configuration

A continuación se presentan los productos de software utilizados por el equipo, organizados según la actividad del ciclo de vida en la que intervienen. Esta información permite que los integrantes actuales y futuros reproduzcan el entorno de trabajo.

**Project Management**

| Herramienta | Propósito en KairoLabs | Referencia |
| :--- | :--- | :--- |
| **Trello** | Gestión del Product Backlog y del Sprint Backlog mediante el tablero *KairoLabs — Product Backlog* con las columnas Product Backlog, Ready, In Progress y Done. | https://trello.com/ |
| **GitHub Organization** | Organización `1ASI0732-2620-9082-Aether-System` que centraliza los cinco repositorios del producto. | https://github.com/1ASI0732-2620-9082-Aether-System |
| **Google Meet** | Reuniones síncronas del equipo (planificación, revisión de avance y coordinación de entregables). | https://meet.google.com/ |

**Requirements Management**

| Herramienta | Propósito en KairoLabs | Referencia |
| :--- | :--- | :--- |
| **Trello** | Registro de User Stories (US01–US78), Technical Stories (TS01–TS12) y Spikes (SP01–SP05) con su prioridad y Story Points. | https://trello.com/ |
| **UXPressia** | Elaboración de User Personas, Empathy Maps, Journey Maps e Impact Mapping. | https://uxpressia.com/ |
| **Miro** | As-Is y To-Be Scenario Mapping y EventStorming. | https://miro.com/ |

**Product UX/UI Design**

| Herramienta | Propósito en KairoLabs | Referencia |
| :--- | :--- | :--- |
| **Figma** | Wireframes, mock-ups y prototipos de la Landing Page y la Web Application. | https://www.figma.com/ |
| **Lucidchart** | Wireflows, User Flows, diagramas C4, diagramas de clases y de base de datos. | https://www.lucidchart.com/ |

**Software Development**

| Herramienta / Tecnología | Producto | Propósito |
| :--- | :--- | :--- |
| **Visual Studio Code** | Todos | Editor principal para HTML, CSS, JavaScript, Vue y Markdown. |
| **HTML5, CSS3 y JavaScript (ES6+)** | Landing Page, Mobile | Estructura, estilos e interacción del sitio público y de la versión mobile-first. |
| **Bootstrap 5.3 + Bootstrap Icons** | Landing Page | Grid responsive, componentes de navegación e iconografía. |
| **Matter.js 0.19** | Landing Page | Animación física de los elementos decorativos del footer. |
| **Vue.js 3 + Vite** | Web Application, Mobile | Framework SPA de la Web App y herramienta de construcción / servidor de desarrollo. |
| **PrimeVue 4, PrimeIcons y PrimeFlex** | Web Application | Biblioteca de componentes UI (toasts, diálogos, selects) e iconografía. |
| **Vue Router 5 y Pinia 3** | Web Application | Enrutamiento por bounded context y gestión de estado (`*.store.js`). |
| **Axios** | Web Application | Cliente HTTP para consumir la RESTful API. |
| **vue-i18n** | Web Application | Internacionalización español / inglés. |
| **Chart.js + vue-chartjs** | Web Application | Gráficos de tendencias del Centro de Control. |
| **Leaflet + OpenStreetMap** | Web Application | Mapa de establecimientos. |
| **C# / ASP.NET Core (Kestrel)** | RESTful API | Implementación de los Web Services RESTful. |
| **Entity Framework Core** | RESTful API | ORM para el acceso a datos. |
| **MySQL (Filess.io)** | RESTful API | Base de datos relacional del backend. |
| **Git** | Todos | Control de versiones distribuido. |
| **Node.js / npm** | Web Application, Mobile | Gestión de dependencias y ejecución de scripts (`npm run dev`, `npm run build`). |

**Software Testing**

| Herramienta | Propósito |
| :--- | :--- |
| **Swagger UI** | Pruebas manuales de los endpoints publicados (opción *Try it out*). |
| **Postman** | Pruebas de solicitudes HTTP durante la integración Web App ↔ API. |
| **Modo demo del frontend (`VITE_USE_MOCKS=true`)** | Base de datos en memoria (`mock-database.js`) para probar la Web App sin depender del backend. |
| **Chrome / Edge DevTools (Device Mode)** | Validación responsive en resoluciones de smartphone, tablet y desktop. |

**Software Deployment**

| Herramienta | Propósito |
| :--- | :--- |
| **Vercel** | Hosting de la Landing Page (sitio estático) y de la Web Application (build de Vite). Despliegue automático al hacer push a la rama de producción. |
| **GitHub Pages** | Publicación alternativa de la Landing Page (entorno `github-pages`). |
| **Render** | Hosting de la RESTful API como Web Service con runtime Docker. |
| **Filess.io** | Hosting de la base de datos relacional del backend. |

**Software Documentation**

| Herramienta | Propósito |
| :--- | :--- |
| **Markdown + GitHub** | Redacción del Project Report bajo control de versiones (`report/*.md`). |
| **Swagger / OpenAPI 3.0** | Documentación interactiva de la RESTful API (`MediTrack Sensor API v1`). |
| **README.md por repositorio** | Instrucciones de ejecución de cada producto. |

---

### 5.1.2. Source Code Management

El equipo utiliza **GitHub** como plataforma de control de versiones. Todos los productos se alojan en la organización pública:

**Organización:** https://github.com/1ASI0732-2620-9082-Aether-System

![Organización Aether System en GitHub](../assets/chapter-5/gh-organizacion.png)

*Figura 5.1.2-1. Organización `1ASI0732-2620-9082-Aether-System` con los repositorios de KairoLabs.*

| Producto | Repositorio | Rama por defecto | Contenido |
| :--- | :--- | :---: | :--- |
| **Project Report** | https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Project-Report | `main` | Informe en Markdown (`report/`), imágenes y evidencias (`assets/`). |
| **Landing Page** | https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Landing-Page | `main` | Sitio estático: `index.html`, `css/`, `js/`, `Imagenes/`, `Videos/`. |
| **Frontend Web Application** | https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Frontend | `master` | SPA en Vue 3 organizada por bounded contexts (`iam`, `establishment`, `monitoring`, `logistics`, `subscriptions`, `shared`). |
| **Native-Mobile Application** | https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Mobile | `main` | Primer incremento mobile-first (Vite + HTML/CSS/JS). |
| **RESTful API** | https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Platform | `main` | Repositorio destinado al código fuente del backend ASP.NET Core. |

**GitFlow Workflow**

El equipo aplica **GitFlow** (Driessen, 2010) para separar el trabajo en curso de las versiones estables:

| Rama | Uso |
| :--- | :--- |
| `main` / `master` | Versión estable y desplegada. Vercel publica en producción cada cambio integrado en esta rama. |
| `develop` | Rama de integración. Recibe las *feature branches* terminadas antes de promoverlas a `main`. |
| `feature/<nombre>` | Desarrollo aislado de una funcionalidad o capítulo. Se crea desde `develop` y vuelve a `develop` mediante merge o Pull Request. |
| `release/<versión>` | Preparación de una versión (por ejemplo `release/1.0.0`) antes de integrarla a `main`. |
| `hotfix/<descripción>` | Corrección urgente sobre `main`, que luego se integra también a `develop`. |

En el repositorio del informe se aplicó este flujo con una rama por capítulo (`feature/chapter-1` … `feature/chapter-5`), integradas a `develop` y luego a `main` (por ejemplo, el Pull Request #1 `feature/chapter4 → main`).

![Ramas del repositorio del informe](../assets/chapter-5/gh-report-branches.png)

*Figura 5.1.2-2. Ramas `main`, `develop` y `feature/chapter-*` del repositorio `KairoLabs-Project-Report`.*

**Conventional Commits**

Los mensajes de commit siguen la especificación **Conventional Commits 1.0.0**:

```text
<type>(<scope>): <description>

[body opcional]
```

| Tipo | Uso | Ejemplo |
| :--- | :--- | :--- |
| `feat` | Nueva funcionalidad | `feat(landing): rebrand to KairoLabs with partner logos and scroll animations` |
| `fix` | Corrección de errores | `fix(deploy): serve landing from repo root, not leftover public folder` |
| `chore` | Configuración o mantenimiento | `chore: add Vercel static config so index.html is served at root` |
| `docs` | Documentación | `docs: estudiante Rodrigo Oblitas` |
| `refactor` | Reestructuración sin cambio de comportamiento | `refactor(iam): align IAM bounded context with learning-center DDD pattern` |
| `style` | Cambios de formato o estilos sin lógica | `style(landing): improve responsive layout` |
| `test` | Pruebas | `test(iam): add sign-in flow scenarios` |

**Semantic Versioning**

Las versiones liberadas de cada producto se identifican con **Semantic Versioning 2.0.0** (`MAJOR.MINOR.PATCH`):

- **MAJOR:** cambios incompatibles (por ejemplo, un cambio de contrato de la API).
- **MINOR:** nuevas funcionalidades compatibles (por ejemplo, un nuevo módulo de la Web App).
- **PATCH:** correcciones sin cambios funcionales.

Las versiones se publican mediante *tags* sobre `main` (`v1.0.0`, `v1.1.0`, `v1.1.1`). El Project Report mantiene además su propio registro de versiones (1.01, 1.02, …) en el `README.md` del repositorio.

---

### 5.1.3. Source Code Style Guide & Conventions

Toda la nomenclatura técnica (variables, funciones, clases, componentes, archivos y comentarios de código) se escribe en **inglés**. El contenido visible para el usuario se escribe en español y se traduce al inglés mediante i18n.

**Principios generales**

- Nombres descriptivos que expresen la responsabilidad del elemento.
- Indentación de 2 espacios en HTML, CSS, JavaScript y Vue; 4 espacios en C#.
- Evitar duplicación: lógica reutilizable en servicios, stores o componentes compartidos.
- Comentarios solo cuando aclaran una decisión no evidente.
- Separación de responsabilidades por capa (`domain`, `application`, `infrastructure`, `presentation`).

**HTML** (referencia: [Google HTML/CSS Style Guide](https://google.github.io/styleguide/htmlcssguide.html))

- Declarar `<!DOCTYPE html>` y el idioma (`<html lang="es">`).
- Etiquetas y atributos en minúsculas, valores entre comillas dobles.
- Etiquetas semánticas: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>`.
- Atributo `alt` en todas las imágenes y `aria-label` en controles sin texto (por ejemplo, el botón de menú de la versión móvil).
- Cada sección de la Landing tiene un `id` usado por la navegación (`#tecnologia`, `#sectores`, `#planes`, `#contacto`).

```html
<section id="planes" class="pricing-section-premium">
  <h2 data-i18n="plan_h2">Planes de Monitoreo</h2>
</section>
```

**CSS**

- Clases en `kebab-case` con prefijo de componente cuando aplica (`site-header__bar`, `team-equipo-card__badge`, notación BEM).
- Variables CSS en `:root` para los colores del design system (navy `#102635`, naranja `#f47a38`).
- Diseño responsive con `@media` (mobile-first en `KairoLabs-Mobile`).
- Evitar `!important` y selectores excesivamente específicos.

```css
:root {
  --ink: #102635;
  --orange: #f47a38;
  --radius: 24px;
}
```

**JavaScript** (referencia: [Google JavaScript Style Guide](https://google.github.io/styleguide/jsguide.html))

- `camelCase` para variables y funciones, `PascalCase` para clases, `UPPER_SNAKE_CASE` para constantes.
- `const` por defecto, `let` solo si hay reasignación; no se usa `var`.
- Módulos ES (`import` / `export`) y `async/await` para llamadas HTTP.

**Vue.js (Web Application)** (referencia: [Vue Style Guide](https://vuejs.org/style-guide/))

- Componentes *Single File Component* con `<script setup>`.
- Archivos de vistas y componentes en `kebab-case` (`view-establishments.vue`, `control-center-panel.vue`).
- Estructura por bounded context y capa:

```text
src/
├── iam/                 # Identity & Access Management
│   ├── application/     # iam.store.js (Pinia)
│   ├── domain/          # entidades y comandos (sign-in.command.js)
│   ├── infrastructure/  # iam-api.js, assemblers, guard, interceptor
│   └── presentation/    # vistas y rutas
├── establishment/
├── monitoring/
├── logistics/
├── subscriptions/
└── shared/              # layout, componentes comunes, base-api.js, mocks
```

- Entidades en `*.entity.js`, *assemblers* en `*.assembler.js`, clientes HTTP en `*-api.js` y stores en `*.store.js`.

**C# / ASP.NET Core (RESTful API)** (referencia: [C# Coding Conventions – Microsoft](https://learn.microsoft.com/dotnet/csharp/fundamentals/coding-style/coding-conventions))

- `PascalCase` para clases, métodos y propiedades; prefijo `I` en interfaces (`IDeviceRepository`).
- `camelCase` para parámetros y variables locales.
- Sufijo `Async` en métodos asíncronos.
- Recursos de entrada y salida con sufijo `Resource` (`SignInResource`, `CreateNestedDeviceResource`).

**RESTful API**

- Recursos en plural y minúsculas: `/api/v1/devices`, `/api/v1/transports`.
- Rutas anidadas para expresar pertenencia: `/api/v1/establishments/{establishmentId}/devices`.
- Atributos JSON en `snake_case` (`establishment_name`, `door_status`).
- Verbos HTTP según la operación: `GET` (consultar), `POST` (crear), `PUT` (actualizar), `DELETE` (eliminar).

**Gherkin**

Los criterios de aceptación se redactan con **Gherkin** (`Given / When / Then`), en Happy Path y Unhappy Path, tal como se especificó en el Capítulo III.

---

### 5.1.4. Software Deployment Configuration

Cada producto se despliega de forma independiente. Los repositorios de la Landing Page y de la Web Application están conectados a Vercel, que genera un despliegue de **Production** cada vez que se integra un cambio en la rama principal. La API se ejecuta en Render y persiste en una base de datos de Filess.io.

```mermaid
flowchart LR
    U([Usuario]) --> L[Landing Page<br/>Vercel]
    U --> M[Mobile App<br/>incremento 1]
    L -- "Comienza ahora" --> W[Web Application<br/>Vue 3 · Vercel]
    M -- "Comienza ahora" --> W
    W -- "HTTPS / JSON<br/>Axios" --> A[RESTful API<br/>ASP.NET Core · Render]
    A --> D[(Base de datos<br/>Filess.io)]
    G[GitHub<br/>Aether System] -. push a main/master .-> L
    G -. push a main/master .-> W
```

*Figura 5.1.4-1. Arquitectura de despliegue de KairoLabs.*

| Componente | Tecnología | Plataforma | URL | Rama | Configuración |
| :--- | :--- | :--- | :--- | :---: | :--- |
| Landing Page | HTML5, CSS3, JS, Bootstrap | Vercel (+ GitHub Pages) | https://landing-page-kairolabs.vercel.app | `main` | `vercel.json` con `outputDirectory: "."` y `cleanUrls: true` (sitio estático servido desde la raíz). |
| Web Application | Vue 3 + Vite | Vercel | https://kairo-labs-frontend.vercel.app | `master` | Build `vite build`; `vercel.json` con *rewrite* `/(.*) → /index.html` para el enrutamiento SPA. |
| Mobile (incremento 1) | Vite + HTML/CSS/JS | Local | `http://<ip-local>:5173` | `main` | `npm run dev` ejecuta `vite --host 0.0.0.0` para probar desde un smartphone en la misma red. |
| RESTful API | ASP.NET Core | Render (Docker) | https://medi-track-sensor-platform.onrender.com | — | Web Service con Swagger UI publicado en `/swagger/index.html`. |
| Base de datos | MySQL | Filess.io | — | — | Cadena de conexión inyectada como variable de entorno en Render. |

**Variables de entorno de la Web Application**

La URL del backend no se escribe en el código: se define por ambiente en archivos `.env`, que Vite expone mediante `import.meta.env`.

| Variable | `.env.development` | `.env.production` |
| :--- | :--- | :--- |
| `VITE_USE_MOCKS` | `true` (base de datos en memoria) | `false` |
| `VITE_API_BASE_URL` | `http://localhost:5000/api/v1` | `https://medi-track-sensor-platform.onrender.com/api/v1` |
| `VITE_IAM_ENDPOINT_PATH` | `/users` | `/users` |
| `VITE_ESTABLISHMENT_ENDPOINT_PATH` | `/establishments` | `/establishments` |
| `VITE_MONITORING_ENDPOINT_PATH` | `/devices` | `/devices` |
| `VITE_LOGISTICS_ENDPOINT_PATH` | `/transports` | `/transports` |
| `VITE_SUBSCRIPTIONS_ENDPOINT_PATH` | `/subscriptions` | `/subscriptions` |

**Variables de entorno de la RESTful API (Render)**

| Variable | Función |
| :--- | :--- |
| `ASPNETCORE_ENVIRONMENT` | Ambiente de ejecución del servicio. |
| `ConnectionStrings__DefaultConnection` | Cadena de conexión hacia la base de datos de Filess.io. |

**Procedimiento de despliegue (Vercel)**

1. Iniciar sesión en Vercel con la cuenta de GitHub e importar el repositorio (*Add New → Project*).
2. Seleccionar el *framework preset*: **Other** para la Landing Page (estático) y **Vite** para la Web Application.
3. Registrar las variables `VITE_*` en *Settings → Environment Variables* (solo Web Application).
4. Confirmar *Deploy*. A partir de ese momento cada push a la rama principal genera un nuevo despliegue de producción, registrado por `vercel[bot]` en la pestaña *Deployments* del repositorio.

---

## 5.2. Product Implementation & Deployment

### 5.2.1. Sprint Backlogs

En esta sección se presenta el Sprint Backlog del **Sprint 1**, que corresponde al primer incremento del producto para el Sprint Review de la semana 4 (AVANCE 1). Las User Stories provienen del Product Backlog priorizado del Capítulo III y se gestionaron en Trello.

| Sprint # | Sprint 1 |
| :--- | :--- |
| **Periodo** | 06/09/2026 – 30/09/2026 |
| **Sprint 1 Goal** | Our focus is to deliver the first increment of the KairoLabs ecosystem for cycle 2026-20: the rebranded Landing Page, the Web Application authentication flow aligned with the new design system, and the first mobile-first version of the mobile app. We believe it delivers a clear and consistent entry point to KairoLabs for pharmacy managers and warehouse staff. This will be confirmed when the Landing Page and the Web Application are deployed on Vercel and the mobile version runs correctly on smartphone viewports. |
| **Sum of Story Points** | 50 |

**Tablero en Trello**

![Sprint Backlog en Trello](../assets/chapter-5/sprint1-trello-product-backlog.png)

*Figura 5.2.1-1. Tablero KairoLabs — Product Backlog en Trello (columnas Product Backlog, Ready, In Progress y Done).*

**Enlace del tablero:** https://trello.com/invite/b/6aadc5316cf3b1b25172d115/ATTI62b2568d05f97578a9aaa820380a86ceF4D89A86/kairolabs-product-backlog

**Sprint Backlog 1**

| Sprint # | Sprint 1 | | | | | | |
| :--- | :--- | :--- | :--- | :--- | :---: | :--- | :---: |
| **User Story** | | **Work-Item / Task** | | | | | |
| **Id** | **Title** | **Id** | **Title** | **Description** | **Estimation (Hours)** | **Assigned To** | **Status** |
| US01 | Navegación clara | T01 | Rediseñar header y navegación | Barra de navegación fija con resaltado de la sección activa y selector ES/EN. | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| US02 | Mensaje hero claro | T02 | Implementar hero de KairoLabs | Hero con video de fondo, tagline y CTA principal. | 4 | Mallqui Vilca, Dhilsen Armil | Done |
| US03 | Acceso a sección tecnología | T03 | Implementar sección Tecnología | Carrusel de capacidades, resultados esperados y video demostrativo. | 6 | Mallqui Vilca, Dhilsen Armil | Done |
| US04 | Acceso a sectores objetivo | T04 | Implementar sección Sectores | Tarjetas para personal operativo de almacenes y gestores de farmacia. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| US06 | Información del equipo | T05 | Actualizar sección Equipo | Tarjetas de los integrantes de Aether System. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| US16 | Información de planes y precios | T06 | Implementar deck de planes | Planes Piloto, Básico, Profesional, Hospitalario y Premium. | 5 | Mallqui Vilca, Dhilsen Armil | Done |
| US20 | Información de la empresa | T07 | Implementar sección Nosotros | Acordeón con misión, visión y equipo académico. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| US21 | Botón de contacto visible | T08 | Enlazar CTAs a la plataforma | Botones "Comienza ahora" dirigidos a la Web Application. | 1 | Mallqui Vilca, Dhilsen Armil | Done |
| US27 | Carga eficiente | T09 | Optimizar recursos y despliegue | Retiro del video de 62 MB y configuración estática de Vercel (`vercel.json`). | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US26 | Adaptación responsive | T10 | Ajustar responsive de la Landing | Corrección del header y de las secciones en pantallas pequeñas. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| US26 | Adaptación responsive | T11 | Construir versión mobile-first | Repositorio `KairoLabs-Mobile`: menú táctil, acordeón, carruseles deslizables y CTA a la Web App. | 8 | Oblitas Alcalde, Rodrigo | Done |
| US29 | Pantalla de Login | T12 | Rediseñar vistas de autenticación | Login y registro con el design system navy/naranja y panel visual lateral. | 5 | Mallqui Vilca, Dhilsen Armil | Done |
| US31 | Registro Sign Up operador/usuario | T13 | Registro de personal de almacén | Formulario con código de entidad de salud. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US32 | Registro Sign Up entidad Admin | T14 | Registro de gestor de farmacia | Formulario con nombre de la entidad y paso a selección de plan. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US30 | Inicio de sesión (Login) | T15 | Integrar sign-in con la API | Consumo de `POST /api/v1/users/sign-in` y persistencia de la sesión. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| US34 | Protección de rutas privadas | T16 | Validar guard de autenticación | Redirección a `/login` cuando no existe sesión activa. | 2 | Mallqui Vilca, Dhilsen Armil | Done |
| US48 | Login diferenciado personal vs entidad | T17 | Redirección según rol | Home de entidad de salud u home de personal operativo según el rol. | 3 | Mallqui Vilca, Dhilsen Armil | Done |
| TS10 | Swagger/OpenAPI publish | T18 | Verificar API desplegada | Revisión de Swagger UI y ejecución de endpoints de lectura en producción. | 3 | Dinklange Arevalo, Sandro | Done |
| — | Documentación | T19 | Capítulo I | Revisión de la introducción, 5W2H y Lean UX. | 6 | Diaz Mendoza, Sebastian Victor Andre | Done |
| — | Documentación | T20 | Capítulo II | Actualización de entrevistas y análisis de requisitos. | 5 | Dinklange Arevalo, Sandro | Done |
| — | Documentación | T21 | Capítulo III | User Stories, Product Backlog, To-Be Scenario Mapping e Impact Mapping. | 8 | Mallqui Vilca, Dhilsen Armil | Done |
| — | Documentación | T22 | Capítulo IV | Documentación del diseño del producto. | 6 | Ramirez Escalante, Carlo Patricio | Done |
| — | Documentación | T23 | Capítulo V | Evidencias de implementación, despliegue y documentación de la API. | 8 | Dinklange Arevalo, Sandro | Done |

---

### 5.2.2. Implemented Landing Page Evidence

La Landing Page presenta la propuesta de valor de KairoLabs a los dos segmentos objetivo (personal operativo de almacenes farmacéuticos y gestores de farmacia). En el Sprint 1 se realizó el *rebranding* a KairoLabs / Aether System, se incorporaron los logos de las instituciones del marco regulatorio, las animaciones de scroll y la configuración de despliegue estático en Vercel.

| Elemento | Detalle |
| :--- | :--- |
| **URL (Vercel)** | https://landing-page-kairolabs.vercel.app |
| **URL alternativa (GitHub Pages)** | https://1asi0732-2620-9082-aether-system.github.io/KairoLabs-Landing-Page/ |
| **Repositorio** | https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Landing-Page |
| **Tecnologías** | HTML5, CSS3, JavaScript, Bootstrap 5.3, Bootstrap Icons, Matter.js, i18n ES/EN |
| **Despliegue de producción (`vercel[bot]`)** | Commit `34434e8`, 14/09/2026 10:04 (hora de Lima), entorno *Production* |

**Commits del Sprint 1**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| :--- | :---: | :--- | :--- | :--- | :---: |
| KairoLabs-Landing-Page | main | `f0dfc9a` | feat(landing): rebrand to KairoLabs with partner logos and scroll animations | Replace MediTrack branding with Aether System copy, institution logos, and expand and story interactions. | 13/09/2026 |
| KairoLabs-Landing-Page | main | `cc153f1` | fix(landing): drop heavy video-5 until it is compressed | Use video-3 in the expand section so Vercel can deploy without the 62 MB file. | 13/09/2026 |
| KairoLabs-Landing-Page | main | `02b2707` | chore: add Vercel static config so index.html is served at root | — | 13/09/2026 |
| KairoLabs-Landing-Page | main | `0376bd1` | fix(deploy): serve landing from repo root, not leftover public folder | — | 14/09/2026 |
| KairoLabs-Landing-Page | main | `34434e8` | fix: design in the header | — | 14/09/2026 |

**Evidencias de la Landing Page desplegada**

![Hero de la Landing Page](../assets/chapter-5/landing-hero.jpg)

*Figura 5.2.2-1. Sección Inicio (hero) con navegación, selector ES/EN y CTA "¡Comienza hoy mismo!" (US01, US02).*

![Instituciones del marco regulatorio](../assets/chapter-5/landing-instituciones.png)

*Figura 5.2.2-2. Franja "Respaldados por instituciones líderes" con MINSA, DIGEMID, SUSALUD, CENARES, CONCYTEC y Osinergmin.*

![Sección Nosotros](../assets/chapter-5/landing-nosotros.png)

*Figura 5.2.2-3. Sección Nosotros con misión, visión y equipo académico (US20).*

![Sección Tecnología](../assets/chapter-5/landing-tecnologia.jpg)

*Figura 5.2.2-4. Sección Tecnología Inteligente: capacidades, resultados esperados y video demostrativo (US03).*

![Sección Sectores](../assets/chapter-5/landing-sectores.jpg)

*Figura 5.2.2-5. Sección Sectores objetivo (US04).*

![Sección Equipo](../assets/chapter-5/landing-equipo.png)

*Figura 5.2.2-6. Sección Integrantes del Equipo (US06).*

![Sección Planes](../assets/chapter-5/landing-planes.png)

*Figura 5.2.2-7. Deck de planes de monitoreo (US16).*

![Sección Contacto](../assets/chapter-5/landing-contacto.png)

*Figura 5.2.2-8. Llamado a la acción final (US21).*

![Footer](../assets/chapter-5/landing-footer.jpg)

*Figura 5.2.2-9. Footer con navegación, redes y términos y condiciones.*

<p align="center">
  <img src="../assets/chapter-5/landing-responsive-mobile.jpg" alt="Landing Page en smartphone" width="300"><br>
  <em>Figura 5.2.2-10. Landing Page en un viewport de smartphone de 390 × 844 px (US26).</em>
</p>

![Repositorio de la Landing Page](../assets/chapter-5/gh-landing-repo.png)

*Figura 5.2.2-11. Repositorio `KairoLabs-Landing-Page` vinculado al despliegue en Vercel.*

![Commits de la Landing Page](../assets/chapter-5/gh-landing-commits.png)

*Figura 5.2.2-12. Historial de commits del Sprint 1 en la rama `main`.*

---

### 5.2.3. Implemented Frontend-Web Application Evidence

La Web Application es la plataforma operativa de KairoLabs. Está construida con **Vue 3 + Vite** y organizada por bounded contexts (IAM, Establishment, Monitoring, Logistics y Subscriptions). En el Sprint 1 se unificó la interfaz bajo el design system navy/naranja de KairoLabs, se rediseñaron el login y el registro, y se reemplazaron varias navegaciones por diálogos de inspección (modales).

| Elemento | Detalle |
| :--- | :--- |
| **URL (Vercel)** | https://kairo-labs-frontend.vercel.app |
| **Repositorio** | https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Frontend |
| **Tecnologías** | Vue 3, Vite, PrimeVue 4, Pinia, Vue Router, Axios, vue-i18n, Chart.js, Leaflet |
| **Backend consumido** | `https://medi-track-sensor-platform.onrender.com/api/v1` |
| **Despliegue de producción (`vercel[bot]`)** | Commit `ffadea8`, 14/09/2026 19:03 (hora de Lima), entorno *Production* |

**Commits del Sprint 1**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| :--- | :---: | :--- | :--- | :--- | :---: |
| KairoLabs-Frontend | master | `ad01cfd` | feat: rebrand KairoLabs UI with modals, branded selects, and control center polish | Unify auth, profile, establishments, devices, transports, and operators under the navy/orange design system, replace page navigations with inspect modals, and harden mock flows for local demos. | 14/09/2026 |
| KairoLabs-Frontend | master | `ffadea8` | fix: responsive | Ajustes responsive de `auth-panel`, `register` y `layout`. | 14/09/2026 |

**Vistas públicas (aplicación desplegada en Vercel)**

![Login](../assets/chapter-5/web-login.jpg)

*Figura 5.2.3-1. Inicio de sesión (US29, US30).*

![Registro de gestor de farmacia](../assets/chapter-5/web-register-entidad.jpg)

*Figura 5.2.3-2. Registro como Gestor de farmacia (US32).*

![Registro de personal de almacén](../assets/chapter-5/web-register-personal.jpg)

*Figura 5.2.3-3. Registro como Personal de almacén con código de entidad de salud (US31).*

**Vistas internas**

Las siguientes capturas se obtuvieron ejecutando la aplicación en **modo demo** (`VITE_USE_MOCKS=true`), que utiliza los datos de prueba de `src/shared/infrastructure/mocks/mock-database.js`. Así se muestran todos los módulos con datos representativos sin alterar la información de producción.

![Home de la entidad de salud](../assets/chapter-5/web-home-entidad.png)

*Figura 5.2.3-4. Inicio del gestor de farmacia: accesos rápidos, Centro de Control Operativo y KPIs (US48, US57).*

![Listado de establecimientos](../assets/chapter-5/web-establecimientos.png)

*Figura 5.2.3-5. Ver Establecimientos con filtros y contadores por tipo (US37, US41).*

![Detalle de establecimiento](../assets/chapter-5/web-establecimiento-detalle.png)

*Figura 5.2.3-6. Detalle de establecimiento en modal de inspección (US39).*

![Agregar establecimiento](../assets/chapter-5/web-establecimiento-nuevo.png)

*Figura 5.2.3-7. Agregar Establecimiento (US38).*

![Mapa de establecimientos](../assets/chapter-5/web-mapa-establecimientos.jpg)

*Figura 5.2.3-8. Mapa de Establecimientos con Leaflet / OpenStreetMap (US42, US65).*

![Operadores](../assets/chapter-5/web-operadores.png)

*Figura 5.2.3-9. Ver Operadores con turno, alertas atendidas y establecimiento asignado (US43).*

![Detalle de operador](../assets/chapter-5/web-operador-detalle.png)

*Figura 5.2.3-10. Información del operador (US47).*

![Dispositivos](../assets/chapter-5/web-dispositivos.png)

*Figura 5.2.3-11. Ver Dispositivos con lecturas de temperatura y humedad (US50, US53, US54).*

![Detalle de dispositivo](../assets/chapter-5/web-dispositivo-detalle.png)

*Figura 5.2.3-12. Lecturas del dispositivo con estados OK / Atención / Crítico (US51, US66).*

![Registrar dispositivo](../assets/chapter-5/web-dispositivo-nuevo.png)

*Figura 5.2.3-13. Registrar dispositivo con selección de sensores habilitados (US49).*

![Centro de Control](../assets/chapter-5/web-centro-control.png)

*Figura 5.2.3-14. Centro de Control: KPIs, sensores por sede e índice ambiental (US57, US59).*

![Transportes](../assets/chapter-5/web-transportes.png)

*Figura 5.2.3-15. Ver Transportes con alertas críticas de cadena de frío (US72).*

![Detalle de transporte](../assets/chapter-5/web-transporte-detalle.png)

*Figura 5.2.3-16. Lecturas de sensores de una unidad de transporte (US73).*

![Planes](../assets/chapter-5/web-planes.png)

*Figura 5.2.3-17. Elige un plan (US75, US78).*

![Perfil](../assets/chapter-5/web-perfil.png)

*Figura 5.2.3-18. Perfil de usuario con plan activo (US35, US36).*

![Home del personal operativo](../assets/chapter-5/web-home-personal.png)

*Figura 5.2.3-19. Inicio del personal de almacén con módulos de su sede (US48).*

![Repositorio del frontend](../assets/chapter-5/gh-frontend-repo.png)

*Figura 5.2.3-20. Repositorio `KairoLabs-Frontend`.*

![Commits del frontend](../assets/chapter-5/gh-frontend-commits.png)

*Figura 5.2.3-21. Historial de commits de la rama `master`.*

---

### 5.2.4. Acuerdo de Servicio - SaaS

KairoLabs se ofrece bajo el modelo **Software as a Service (SaaS)**: la entidad de salud accede por suscripción a la plataforma desde un navegador o smartphone, sin instalar ni mantener infraestructura propia. El presente acuerdo define el alcance, los niveles de servicio y las responsabilidades de las partes.

#### 1. Partes

| Parte | Descripción |
| :--- | :--- |
| **Proveedor** | KairoLabs, producto desarrollado por el equipo Aether System. |
| **Cliente** | Entidad de salud contratante (hospital, clínica, farmacia, almacén o distribuidora farmacéutica) que se registra como *Gestor de farmacia* (rol `Admin`). |
| **Usuarios autorizados** | Gestores (`Admin`) y personal operativo (`Operator`) registrados por el Cliente mediante su código de entidad. |

#### 2. Objeto y descripción del servicio

El servicio permite monitorear las condiciones de conservación de medicamentos (temperatura, humedad, luz, calidad del aire, vibración, presión, partículas y estado de puertas) en establecimientos y unidades de transporte, gestionar sedes, operadores y dispositivos IoT, y recibir alertas cuando una lectura sale del rango seguro.

| Componente | Función | Acceso |
| :--- | :--- | :--- |
| Landing Page | Información comercial, planes y contacto | https://landing-page-kairolabs.vercel.app |
| Web Application | Operación diaria: establecimientos, operadores, dispositivos, transportes, Centro de Control, planes y perfil | https://kairo-labs-frontend.vercel.app |
| Aplicación móvil | Consulta rápida y acceso a la plataforma desde smartphone | Incremento 1 (mobile-first) |
| RESTful API | Lógica de negocio y persistencia | https://medi-track-sensor-platform.onrender.com |

#### 3. Planes y tarifas

Los planes publicados en la Landing Page son la referencia comercial del servicio. Los montos están expresados en dólares estadounidenses por mes.

| Plan | Precio | Dirigido a | Incluye |
| :--- | :---: | :--- | :--- |
| **Piloto** | US$ 0 (14 días) | Validación inicial en una cámara fría | 1 sensor · 1 área, alertas por email, onboarding incluido. |
| **Básico** | US$ 49 / mes | Farmacias y clínicas con una sede | Monitoreo de 1 sede, visualización en tiempo real, alertas por email, 30 días de historial. |
| **Profesional** | US$ 149 / mes | Centros de distribución y hospitales con varias áreas | Varias áreas, alertas SMS/WhatsApp, 1 año de historial, reportes y dashboards, integración con sistemas. |
| **Hospitalario** | US$ 249 / mes | Hospitales y farmacias clínicas con vacunas y biológicos | Varias cámaras y pabellones, rangos 2–8 °C, roles operador/gestor, evidencia para auditorías, soporte clínico. |
| **Premium** | Personalizado | Cadenas farmacéuticas y redes de salud multisede | Monitoreo multisede, gestión centralizada, análisis de tendencias, soporte prioritario 24/7, cumplimiento DIGEMID/MINSA. |

En la API, la suscripción se registra con el recurso `/api/v1/admins/{adminId}/subscriptions` indicando `plan` (`Basic`, `Premium` o `Enterprise`), `start_date` y `end_date`.

#### 4. Vigencia, renovación y cancelación

- La suscripción es **mensual** y se renueva automáticamente al término de cada periodo.
- El servicio es **sin permanencia**: el Cliente puede cancelar desde *Elige un plan → Cancelar plan*. La cancelación se aplica al cierre del periodo pagado.
- El plan Piloto dura 14 días calendario. Al finalizar, el Cliente puede contratar cualquiera de los planes de pago.
- El Cliente puede cambiar de plan en cualquier momento. El nuevo plan rige desde el siguiente periodo de facturación.

#### 5. Disponibilidad del servicio

| Indicador | Compromiso (versión comercial) |
| :--- | :--- |
| Disponibilidad mensual de la Web Application y la API | ≥ 99.5 % |
| Ventana de mantenimiento programado | Domingos de 00:00 a 04:00 (hora de Lima), con aviso de 48 horas |
| Tiempo máximo de recuperación ante incidentes (RTO) | 4 horas |
| Pérdida máxima de datos ante incidentes (RPO) | 24 horas (respaldo diario de la base de datos) |

Se excluyen del cálculo de disponibilidad el mantenimiento programado, las fallas de conectividad del Cliente o de sus dispositivos IoT y los casos de fuerza mayor.

> **Entorno académico actual:** en el Sprint 1 la API se ejecuta en una instancia gratuita de Render, que se suspende tras un periodo de inactividad. La primera solicitud después de la suspensión puede tardar alrededor de 30 segundos (en la verificación del 30/09/2026 la carga inicial de Swagger UI tomó 33 s y las solicitudes siguientes entre 0.5 s y 0.7 s). Los compromisos de la tabla aplican a la versión comercial con infraestructura dedicada.

#### 6. Soporte y tiempos de respuesta

| Severidad | Ejemplo | Básico / Piloto | Profesional / Hospitalario | Premium |
| :--- | :--- | :---: | :---: | :---: |
| **Crítica** | La plataforma no está disponible o no se registran lecturas | 8 h | 4 h | 1 h (24/7) |
| **Alta** | Un módulo no funciona (por ejemplo, alertas o transportes) | 24 h | 8 h | 4 h |
| **Media / Baja** | Consultas, errores visuales o solicitudes de mejora | 72 h | 48 h | 24 h |

Canales de soporte: correo electrónico (todos los planes), WhatsApp (Profesional, Hospitalario y Premium) y soporte telefónico 24/7 (Premium). La atención es en español.

#### 7. Seguridad y protección de datos

- Todo el tráfico entre el navegador, la Web Application y la API viaja cifrado por **HTTPS**.
- El acceso a la plataforma requiere autenticación con correo y contraseña (`POST /api/v1/users/sign-in`), y cada rol solo accede a los módulos que le corresponden.
- Las credenciales de la base de datos y demás secretos se gestionan como variables de entorno y no se almacenan en el código fuente.
- KairoLabs trata los datos personales de los usuarios conforme a la **Ley N.° 29733, Ley de Protección de Datos Personales**, y su reglamento. Los datos de lecturas y establecimientos pertenecen al Cliente.
- Al finalizar el contrato, el Cliente puede solicitar la exportación de su información durante 30 días. Vencido ese plazo, los datos se eliminan.

#### 8. Responsabilidades

| KairoLabs (Proveedor) | Cliente |
| :--- | :--- |
| Mantener operativos la Web Application, la API y la base de datos. | Usar la plataforma conforme a su plan y a este acuerdo. |
| Aplicar actualizaciones y correcciones sin costo adicional. | Custodiar las credenciales de sus usuarios y desactivar cuentas de personal cesado. |
| Realizar respaldos diarios de la información. | Mantener encendidos y conectados los dispositivos IoT de sus sedes. |
| Notificar mantenimientos programados e incidentes. | Atender las alertas generadas y registrar su respuesta (*alert-answered*). |
| Proteger la confidencialidad de los datos del Cliente. | Pagar la suscripción dentro del plazo establecido. |

#### 9. Compensaciones por incumplimiento

Si la disponibilidad mensual es inferior al compromiso, el Cliente recibe un crédito sobre la siguiente facturación:

| Disponibilidad mensual | Crédito |
| :--- | :---: |
| < 99.5 % y ≥ 99.0 % | 10 % |
| < 99.0 % y ≥ 95.0 % | 25 % |
| < 95.0 % | 50 % |

#### 10. Limitaciones

- KairoLabs apoya el control de las condiciones de almacenamiento, pero no sustituye las obligaciones sanitarias del Cliente ante DIGEMID / MINSA.
- La exactitud de las lecturas depende de la calibración y del estado de los sensores instalados por el Cliente.
- KairoLabs no se responsabiliza por pérdidas de medicamentos ocasionadas por alertas no atendidas por el personal del Cliente.

> Este acuerdo corresponde al modelo de servicio planteado para el proyecto académico KairoLabs. Las condiciones comerciales definitivas deberán formalizarse en un contrato en caso de una implementación comercial.

---

### 5.2.5. Implemented Native-Mobile Application Evidence

Durante el Sprint 1 se construyó el **primer incremento de la aplicación móvil** en el repositorio `KairoLabs-Mobile`. Este incremento es una versión **mobile-first** de la experiencia de KairoLabs, diseñada para interacción táctil en smartphones, que conserva la identidad visual y los contenidos de la Landing Page y dirige al usuario a la Web Application mediante el botón "Comienza ahora".

| Elemento | Detalle |
| :--- | :--- |
| **Repositorio** | https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Mobile |
| **Tecnologías** | Vite 7, HTML5, CSS3 (mobile-first), JavaScript (módulo ES) |
| **Ejecución** | `npm install` y `npm run dev` (`vite --host 0.0.0.0`), lo que permite abrir la app desde un smartphone conectado a la misma red |
| **Viewport de prueba** | 390 × 844 px (smartphone) |

**Commit del Sprint 1**

| Repository | Branch | Commit Id | Commit Message | Commit Message Body | Committed on (Date) |
| :--- | :---: | :--- | :--- | :--- | :---: |
| KairoLabs-Mobile | main | `514be11` | feat: create KairoLabs mobile landing page | Estructura mobile-first: `index.html`, `styles.css`, `app.js`, configuración de Vite. | 14/09/2026 |

**Funcionalidades implementadas**

| Funcionalidad | Descripción | User Story |
| :--- | :--- | :---: |
| Barra superior con menú hamburguesa | Panel lateral de navegación con *scrim*, cierre por botón o toque fuera del panel y atributos `aria-expanded`. | US01, US26 |
| Hero móvil | Mensaje principal y CTA hacia la Web Application. | US02, US21 |
| Carrusel de instituciones | Franja deslizable con DIGEMID, MINSA, SUSALUD y CENARES. | US17 |
| Acordeón Nosotros | Misión, visión y equipo académico en paneles expandibles. | US20 |
| Tarjetas deslizables de tecnología | Temperatura, humedad, iluminación y conectividad 24/7 con desplazamiento horizontal. | US03, US14 |
| Sectores objetivo | Tarjetas por segmento con etiquetas (tiempo real, alertas, cadena de frío). | US04 |
| Planes | Tarjetas de planes optimizadas para lectura en móvil. | US16 |
| Animaciones de aparición | `IntersectionObserver` para revelar secciones al hacer scroll. | US23 |

**Evidencias**

![Versión móvil 1](../assets/chapter-5/mobile-overview-1.png)

*Figura 5.2.5-1. Inicio, menú de navegación, Nosotros y Tecnología en la versión móvil.*

![Versión móvil 2](../assets/chapter-5/mobile-overview-2.png)

*Figura 5.2.5-2. Sectores objetivo, planes y llamado a la acción en la versión móvil.*

![Repositorio móvil](../assets/chapter-5/gh-mobile-repo.png)

*Figura 5.2.5-3. Repositorio `KairoLabs-Mobile`.*

En los siguientes Sprints, este incremento evolucionará hacia la aplicación móvil nativa (iOS/Android) orientada al monitoreo rápido y a la recepción de alertas en tiempo real, consumiendo la misma RESTful API que la Web Application.

---

### 5.2.6. Implemented RESTful API and/or Serverless Backend Evidence

La RESTful API de KairoLabs (**MediTrack Sensor API v1**) está implementada en **ASP.NET Core** y se ejecuta como Web Service en **Render** (el encabezado `x-render-origin-server: Kestrel` confirma el servidor ASP.NET Core). Expone **34 operaciones** organizadas en siete grupos que corresponden a los bounded contexts del dominio, y es la API que consume la Web Application en producción.

| Elemento | Detalle |
| :--- | :--- |
| **Base URL** | `https://medi-track-sensor-platform.onrender.com/api/v1` |
| **Swagger UI** | https://medi-track-sensor-platform.onrender.com/swagger/index.html |
| **Especificación** | OpenAPI 3.0.1 — `/swagger/v1/swagger.json` |
| **Formato** | JSON (`application/json; charset=utf-8`), atributos en `snake_case` |
| **Repositorio** | https://github.com/1ASI0732-2620-9082-Aether-System/KairoLabs-Platform |

| Bounded Context | Recurso | Operaciones |
| :--- | :--- | :---: |
| IAM | Users | 4 |
| IAM | Admins | 2 |
| Establishments | Establishments | 4 |
| Establishments | Operators | 7 |
| Monitoring | Devices | 6 |
| Logistics | Transports | 6 |
| Subscriptions | Subscriptions | 5 |
| **Total** | | **34** |

**Verificación de endpoints en producción (30/09/2026)**

Se ejecutaron solicitudes de solo lectura sobre la API desplegada:

| Método | Endpoint | Código HTTP | Tiempo de respuesta |
| :---: | :--- | :---: | :---: |
| GET | `/api/v1/users` | 200 OK | 0.72 s |
| GET | `/api/v1/admins` | 200 OK | 0.48 s |
| GET | `/api/v1/establishments` | 200 OK | 0.49 s |
| GET | `/api/v1/devices` | 200 OK | 0.62 s |
| GET | `/api/v1/operators` | 200 OK | 0.54 s |
| GET | `/api/v1/transports` | 200 OK | 0.52 s |
| GET | `/api/v1/subscriptions` | 200 OK | 0.51 s |

![Swagger UI](../assets/chapter-5/api-swagger-overview.png)

*Figura 5.2.6-1. Swagger UI de MediTrack Sensor API v1 desplegada en Render.*

![GET establishments](../assets/chapter-5/api-get-establishments.png)

*Figura 5.2.6-2. Ejecución de `GET /api/v1/establishments` con respuesta 200.*

![GET devices](../assets/chapter-5/api-get-devices.png)

*Figura 5.2.6-3. Ejecución de `GET /api/v1/devices` con lecturas de sensores.*

![GET transports](../assets/chapter-5/api-get-transports.png)

*Figura 5.2.6-4. Ejecución de `GET /api/v1/transports`.*

**Integración con la Web Application**

La Web Application consume la API mediante clientes HTTP por bounded context (`iam-api.js`, `establishment-api.js`, `monitoring-api.js`, `logistics-api.js`, `subscriptions-api.js`) que extienden `shared/infrastructure/base-api.js`. La URL base se obtiene de `VITE_API_BASE_URL`, por lo que el mismo código apunta al backend local en desarrollo y a Render en producción.

**Repositorio del backend**

El repositorio `KairoLabs-Platform` de la organización está destinado al código fuente del backend. Durante el Sprint 1 el servicio desplegado en Render corresponde a la versión estable del backend que ya consumía la Web Application; la publicación de su código fuente en `KairoLabs-Platform`, con el flujo GitFlow descrito en la sección 5.1.2, queda pendiente para el siguiente Sprint.

---

### 5.2.7. RESTful API documentation

La documentación de la API se genera con **OpenAPI 3.0 / Swagger** y está disponible en:

**https://medi-track-sensor-platform.onrender.com/swagger/index.html**

Cada endpoint incluye un resumen, una descripción, los parámetros de ruta, el esquema del cuerpo de la solicitud con un ejemplo y los códigos de respuesta. A continuación se documentan los endpoints por recurso.

#### Users (IAM)

| Método | Endpoint | Descripción | Parámetros | Request body | Respuesta |
| :---: | :--- | :--- | :--- | :--- | :--- |
| GET | `/api/v1/users` | Lista todos los usuarios registrados. Útil para verificar IDs antes de crear operadores. | — | — | 200 OK |
| POST | `/api/v1/users` | Registro (sign-up). Si `role = Admin` y se envía `entity_name`, crea también la entidad de salud en la misma transacción. | — | `SignUpResource` | 200 OK |
| POST | `/api/v1/users/sign-in` | Inicio de sesión. Respuesta: `{ user, token }`. | — | `SignInResource` | 200 OK |
| DELETE | `/api/v1/users/{id}` | Elimina un usuario por ID. | `id` | — | 204 No Content |

![Users](../assets/chapter-5/api-tag-users.png)

![Sign-in](../assets/chapter-5/api-sign-in.png)

*Figura 5.2.7-1. Endpoints de Users y detalle de `POST /api/v1/users/sign-in`.*

Ejemplo de solicitud de inicio de sesión:

```http
POST /api/v1/users/sign-in
Content-Type: application/json

{
  "email": "pilsen@gmail.com",
  "password": "tu_password_aqui"
}
```

Ejemplo de registro de una entidad de salud:

```json
{
  "name": "María García",
  "dni": "87654321",
  "email": "nuevo.admin@clinica.com",
  "phone": "+51999999999",
  "job_title": "Administrador",
  "entry_date": "2026-07-06",
  "role": "Admin",
  "password": "********",
  "photo": "",
  "entity_name": "Clínica San Martín"
}
```

#### Admins (IAM)

| Método | Endpoint | Descripción | Parámetros | Request body | Respuesta |
| :---: | :--- | :--- | :--- | :--- | :--- |
| GET | `/api/v1/admins` | Lista las entidades de salud. Su `id` se usa para crear establecimientos y suscripciones. | — | — | 200 OK |
| POST | `/api/v1/admins` | Crea un admin vinculado a un `user_id` existente. | — | `CreateAdminResource` | 200 OK |

![Admins](../assets/chapter-5/api-tag-admins.png)

*Figura 5.2.7-2. Endpoints de Admins.*

#### Establishments

| Método | Endpoint | Descripción | Parámetros | Request body | Respuesta |
| :---: | :--- | :--- | :--- | :--- | :--- |
| GET | `/api/v1/establishments` | Lista global de establecimientos. | — | — | 200 OK |
| GET | `/api/v1/admins/{adminId}/establishments` | Establecimientos de un admin. | `adminId` | — | 200 OK |
| POST | `/api/v1/admins/{adminId}/establishments` | Crea un establecimiento bajo el admin indicado en la ruta. | `adminId` | `CreateNestedEstablishmentResource` | 200 OK |
| DELETE | `/api/v1/establishments/{id}` | Elimina un establecimiento. | `id` | — | 204 No Content |

```json
{
  "establishment_name": "Farmacia Central",
  "establishment_type": "Pharmacy",
  "address": "Av. Principal 123",
  "district": "Miraflores",
  "city_region": "Lima",
  "country": "PE",
  "latitude": -12.1201,
  "longitude": -77.0301,
  "phone": "+5112345678",
  "email": "central@farmacia.pe",
  "website": "www.farmacia.pe"
}
```

`establishment_type` admite: `Warehouse`, `Clinic`, `Hospital`, `Pharmacy`, `Laboratory`.

![Establishments](../assets/chapter-5/api-tag-establishments.png)

*Figura 5.2.7-3. Endpoints de Establishments.*

#### Operators

| Método | Endpoint | Descripción | Parámetros | Request body | Respuesta |
| :---: | :--- | :--- | :--- | :--- | :--- |
| GET | `/api/v1/operators` | Lista global de operadores. | — | — | 200 OK |
| GET | `/api/v1/establishments/{establishmentId}/operators` | Operadores de un establecimiento. | `establishmentId` | — | 200 OK |
| POST | `/api/v1/establishments/{establishmentId}/operators` | Asigna un operador (`users_id` de un usuario con rol Operator). | `establishmentId` | `CreateNestedOperatorResource` | 200 OK |
| PUT | `/api/v1/establishments/{establishmentId}/operators/{operatorId}` | Actualiza el horario del operador. | `establishmentId`, `operatorId` | `UpdateNestedOperatorResource` | 200 OK |
| PUT | `/api/v1/establishments/{establishmentId}/operators/{operatorId}/alert-answered` | Suma 1 al contador `alerts_answered`. Sin body. | `establishmentId`, `operatorId` | — | 200 OK |
| DELETE | `/api/v1/establishments/{establishmentId}/operators/{operatorId}` | Elimina el operador del establecimiento. | `establishmentId`, `operatorId` | — | 204 No Content |
| DELETE | `/api/v1/operators/{id}` | Elimina un operador por ID (ruta plana). | `id` | — | 204 No Content |

![Operators](../assets/chapter-5/api-tag-operators.png)

*Figura 5.2.7-4. Endpoints de Operators.*

#### Devices (Monitoring)

| Método | Endpoint | Descripción | Parámetros | Request body | Respuesta |
| :---: | :--- | :--- | :--- | :--- | :--- |
| GET | `/api/v1/devices` | Lista global de dispositivos. | — | — | 200 OK |
| GET | `/api/v1/establishments/{establishmentId}/devices` | Dispositivos IoT de un establecimiento. | `establishmentId` | — | 200 OK |
| POST | `/api/v1/establishments/{establishmentId}/devices` | Registra un dispositivo (`type_of_medication`: Refrigerated, Biological, Controlled). | `establishmentId` | `CreateNestedDeviceResource` | 200 OK |
| PUT | `/api/v1/establishments/{establishmentId}/devices/{deviceId}/sensor-data` | Actualiza las lecturas del sensor (`door_status`: Open, Closed). | `establishmentId`, `deviceId` | `UpdateDeviceSensorDataResource` | 200 OK |
| DELETE | `/api/v1/establishments/{establishmentId}/devices/{deviceId}` | Elimina el dispositivo del establecimiento. | `establishmentId`, `deviceId` | — | 204 No Content |
| DELETE | `/api/v1/devices/{id}` | Elimina un dispositivo por ID (ruta plana). | `id` | — | 204 No Content |

```json
{
  "temperature": 4.2,
  "humidity": 55,
  "light_intensity": 120.5,
  "air_quality": 98,
  "vibration": 0.1,
  "atmospheric_pressure": 1013.25,
  "suspended_particles": 12,
  "door_status": "Closed"
}
```

![Devices](../assets/chapter-5/api-tag-devices.png)

*Figura 5.2.7-5. Endpoints de Devices.*

#### Transports (Logistics)

| Método | Endpoint | Descripción | Parámetros | Request body | Respuesta |
| :---: | :--- | :--- | :--- | :--- | :--- |
| GET | `/api/v1/transports` | Lista global de transportes. | — | — | 200 OK |
| GET | `/api/v1/establishments/{establishmentId}/transports` | Transportes de un establecimiento. | `establishmentId` | — | 200 OK |
| POST | `/api/v1/establishments/{establishmentId}/transports` | Registra una unidad de transporte con sensores. | `establishmentId` | `CreateNestedTransportResource` | 200 OK |
| PUT | `/api/v1/establishments/{establishmentId}/transports/{transportId}/sensor-data` | Actualiza la telemetría de la unidad. | `establishmentId`, `transportId` | `UpdateTransportSensorDataResource` | 200 OK |
| DELETE | `/api/v1/establishments/{establishmentId}/transports/{transportId}` | Elimina el transporte del establecimiento. | `establishmentId`, `transportId` | — | 204 No Content |
| DELETE | `/api/v1/transports/{id}` | Elimina un transporte por ID (ruta plana). | `id` | — | 204 No Content |

![Transports](../assets/chapter-5/api-tag-transports.png)

*Figura 5.2.7-6. Endpoints de Transports.*

#### Subscriptions

| Método | Endpoint | Descripción | Parámetros | Request body | Respuesta |
| :---: | :--- | :--- | :--- | :--- | :--- |
| GET | `/api/v1/subscriptions` | Lista global de suscripciones. | — | — | 200 OK |
| GET | `/api/v1/admins/{adminId}/subscriptions` | Suscripciones de un admin. | `adminId` | — | 200 OK |
| POST | `/api/v1/admins/{adminId}/subscriptions` | Crea una suscripción (`plan`: Basic, Premium, Enterprise; fechas `YYYY-MM-DD`). | `adminId` | `CreateNestedSubscriptionResource` | 200 OK |
| DELETE | `/api/v1/admins/{adminId}/subscriptions/{subscriptionId}` | Elimina la suscripción del admin. | `adminId`, `subscriptionId` | — | 204 No Content |
| DELETE | `/api/v1/subscriptions/{id}` | Elimina una suscripción por ID (ruta plana). | `id` | — | 204 No Content |

```json
{
  "plan": "Premium",
  "start_date": "2026-07-01",
  "end_date": "2027-06-30"
}
```

![Subscriptions](../assets/chapter-5/api-tag-subscriptions.png)

*Figura 5.2.7-7. Endpoints de Subscriptions.*

#### Esquemas (Schemas)

| Schema | Atributos |
| :--- | :--- |
| `SignUpResource` | `name`, `dni`, `email`, `phone`, `job_title`, `entry_date` (date), `role` (`UserRole`), `password`, `photo`, `entity_name` |
| `SignInResource` | `email`, `password` |
| `CreateAdminResource` | `entity_name`, `entity_code`, `schedule`, `user_id` (int) |
| `CreateNestedEstablishmentResource` | `establishment_name`, `establishment_type` (`EstablishmentType`), `address`, `district`, `city_region`, `country`, `latitude`, `longitude`, `phone`, `email`, `website` |
| `CreateNestedOperatorResource` | `schedule`, `users_id` (int) |
| `UpdateNestedOperatorResource` | `schedule` |
| `CreateNestedDeviceResource` | `exact_location`, `type_of_medication`, `enabled_sensors` (JSON en texto) |
| `UpdateDeviceSensorDataResource` | `temperature`, `humidity`, `light_intensity`, `air_quality`, `vibration`, `atmospheric_pressure`, `suspended_particles`, `door_status` |
| `CreateNestedTransportResource` | `type_of_transport`, `type_of_medication`, `enabled_sensors` |
| `UpdateTransportSensorDataResource` | Mismos atributos que `UpdateDeviceSensorDataResource` |
| `CreateNestedSubscriptionResource` | `plan`, `start_date` (date), `end_date` (date) |
| `UserRole` (enum) | `Admin`, `Operator` |
| `EstablishmentType` (enum) | `Warehouse`, `Clinic`, `Hospital`, `Pharmacy`, `Laboratory` |

![Schemas](../assets/chapter-5/api-schemas.png)

*Figura 5.2.7-8. Esquemas publicados en Swagger UI.*

**Flujo de uso recomendado** (documentado en las descripciones de Swagger):

1. `POST /api/v1/users`: registrar al gestor (`role = Admin`, con `entity_name`).
2. `POST /api/v1/users/sign-in`: iniciar sesión y obtener `{ user, token }`.
3. `POST /api/v1/admins/{adminId}/establishments`: crear el establecimiento.
4. `POST /api/v1/establishments/{establishmentId}/devices`: registrar los dispositivos IoT.
5. `PUT .../devices/{deviceId}/sensor-data`: enviar lecturas de los sensores.

---

### 5.2.8. Team Collaboration Insights

El trabajo del Sprint 1 se distribuyó entre los cinco integrantes de Aether System. Los productos de software (Landing Page, Web Application y Mobile) concentraron su actividad entre el 13 y el 14 de setiembre, y el Project Report se trabajó durante todo el Sprint con ramas por capítulo.

| Integrante | GitHub | Principales aportes en el Sprint 1 |
| :--- | :--- | :--- |
| **Mallqui Vilca, Dhilsen Armil** | [`Dhilsen18`](https://github.com/Dhilsen18) | Estructura del repositorio del informe, Capítulo III (User Stories, Product Backlog, scenario maps e Impact Mapping), rebranding y despliegue de la Landing Page, rediseño de la Web Application. |
| **Diaz Mendoza, Sebastian Victor Andre** | [`DiazDeveloper`](https://github.com/DiazDeveloper) | Capítulo I (introducción, 5W2H, Lean UX, perfiles), revisión de entrevistas del Capítulo II, actualización de los Capítulos IV y V. |
| **Ramirez Escalante, Carlo Patricio** | [`Carlo211`](https://github.com/Carlo211) | Documentación del diseño del producto (Capítulo IV), perfil en el Capítulo I y merge del Pull Request #1. |
| **Oblitas Alcalde, Rodrigo** | [`Darkdren`](https://github.com/Darkdren) | Primer incremento de la aplicación móvil (`KairoLabs-Mobile`) y perfil en el Capítulo I. |
| **Dinklange Arevalo, Sandro** | [`Sandro0406`](https://github.com/Sandro0406) | Capítulo II (requisitos), Capítulo I y Capítulo V (evidencias de implementación, Acuerdo SaaS y documentación de la API). |

**Commits por integrante y repositorio (Sprint 1, sin merges)**

| Integrante | Project Report | Landing Page | Web Application | Mobile | Total |
| :--- | :---: | :---: | :---: | :---: | :---: |
| Mallqui Vilca, Dhilsen Armil | 14 | 6 | 3 | — | 23 |
| Diaz Mendoza, Sebastian Victor Andre | 15 | — | — | — | 15 |
| Dinklange Arevalo, Sandro | 7 | — | — | — | 7 |
| Ramirez Escalante, Carlo Patricio | 2 | — | — | — | 2 |
| Oblitas Alcalde, Rodrigo | 1 | — | — | 1 | 2 |

**Insights del repositorio del informe**

![Contributors Project Report](../assets/chapter-5/gh-report-contributors.png)

*Figura 5.2.8-1. Insights → Contributors de `KairoLabs-Project-Report`.*

![Commits Project Report](../assets/chapter-5/gh-report-commits.png)

*Figura 5.2.8-2. Commits recientes del informe, incluido el merge del Pull Request #1 (`feature/chapter4`).*

**Insights de los repositorios de producto**

![Contributors Landing Page](../assets/chapter-5/gh-landing-contributors.png)

*Figura 5.2.8-3. Insights → Contributors de `KairoLabs-Landing-Page`.*

![Contributors Frontend](../assets/chapter-5/gh-frontend-contributors.png)

*Figura 5.2.8-4. Insights → Contributors de `KairoLabs-Frontend`.*

![Contributors Mobile](../assets/chapter-5/gh-mobile-contributors.png)

*Figura 5.2.8-5. Insights → Contributors de `KairoLabs-Mobile`.*

![Commits Mobile](../assets/chapter-5/gh-mobile-commits.png)

*Figura 5.2.8-6. Commit inicial del repositorio móvil.*

**Análisis de la colaboración**

- **Trabajo por capítulos en paralelo.** Las ramas `feature/chapter-1` … `feature/chapter-5` permitieron que varios integrantes avanzaran el informe a la vez. El Capítulo IV se integró mediante el Pull Request #1, que dejó registro de la revisión.
- **Concentración del desarrollo de producto.** La mayor parte de los commits de la Landing Page y de la Web Application fueron de un solo integrante. Como acción de mejora se propone distribuir las tareas de código por bounded context, de modo que cada integrante lidere al menos un módulo de la Web App o de la aplicación móvil.
- **Commits más descriptivos.** Una parte de los commits del informe se realizó desde la interfaz web de GitHub con mensajes genéricos (`Update ...md`). Se propone que todos los commits sigan Conventional Commits, con el capítulo como `scope` (por ejemplo, `docs(chapter-5): add API documentation`).
- **Integración continua del despliegue.** La conexión de los repositorios con Vercel permitió validar cada incremento en producción inmediatamente después del push (por ejemplo, los despliegues del 14 de setiembre de la Landing Page y de la Web Application).

---

## 5.3. Video About-the-Product

El video About-the-Product presenta KairoLabs desde la perspectiva de sus segmentos objetivo y muestra los productos implementados en el Sprint 1.

| Elemento | Detalle |
| :--- | :--- |
| **Enlace al video** | *(pendiente: agregar el enlace de Microsoft Stream / YouTube)* |
| **Duración objetivo** | 3 a 5 minutos |
| **Idioma** | Español, con subtítulos |

**Guion del video**

| Minuto | Contenido |
| :---: | :--- |
| 0:00 – 0:30 | Problema: pérdida de medicamentos por condiciones inadecuadas de temperatura, humedad y luz en almacenes y transportes. |
| 0:30 – 1:00 | Propuesta de valor de KairoLabs y segmentos objetivo (personal operativo de almacenes y gestores de farmacia). |
| 1:00 – 1:45 | Recorrido por la Landing Page: Tecnología, Sectores, Planes y CTA "Comienza ahora". |
| 1:45 – 3:15 | Web Application: registro, login, establecimientos, mapa, dispositivos, Centro de Control, transportes y planes. |
| 3:15 – 3:45 | Versión móvil en smartphone. |
| 3:45 – 4:15 | Swagger UI de la RESTful API. |
| 4:15 – 4:30 | Cierre e invitación a probar el plan Piloto. |
