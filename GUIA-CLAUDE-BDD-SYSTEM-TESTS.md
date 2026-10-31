# Guía para completar BDD y pruebas de sistema

Esta guía explica qué preparar para los dos puntos de la rúbrica y qué evidencia guardar. Los apartados corresponden a **6.1.3 Core Behavior-Driven Development (BDD)** y **6.1.4 Core System Tests**. En el informe actual, el contenido relacionado con entrevistas y validación está en el capítulo V; confirma con el docente si estos títulos deben numerarse como capítulo VI o integrarse en el capítulo V.

## Diferencia entre los dos puntos

- **6.1.3 BDD:** define el comportamiento esperado desde el punto de vista del usuario mediante escenarios Given–When–Then (Dado–Cuando–Entonces) y demuestra que se automatizaron y ejecutaron con una herramienta BDD.
- **6.1.4 Pruebas de sistema:** comprueba que el producto completo funciona de extremo a extremo: interfaz, navegación, API y respuesta visible para el usuario. Debe cubrir web y móvil según la rúbrica.
- **Lighthouse:** es evidencia complementaria de rendimiento, accesibilidad, buenas prácticas y SEO. No reemplaza escenarios BDD ni las pruebas funcionales de sistema.

## Punto 6.1.3 — Core Behavior-Driven Development (BDD)

### Qué hacer

1. Escoger entre **2 y 4 flujos implementados** de KairoLabs. Priorizar, por ejemplo, inicio de sesión, consulta de establecimientos y consulta de dispositivos; confirmar primero que esas funciones están disponibles en el producto.
2. Redactar cada flujo como escenario Given–When–Then. Incluir al menos un caso exitoso y uno alternativo o de error.
3. Automatizar los escenarios con una herramienta BDD compatible con el stack existente. Para una aplicación web, Claude debe revisar primero el repositorio y sugerir la opción compatible, por ejemplo Cucumber con Playwright o una alternativa adecuada. No instalar un framework sin revisar antes la estructura y las herramientas ya usadas.
4. Ejecutar las pruebas contra un entorno de prueba, nunca contra datos reales de producción. Guardar el comando usado y el resultado de la ejecución.

### Ejemplo de escenario (ajustar al comportamiento real)

```gherkin
Feature: Inicio de sesión
  Como usuario de KairoLabs
  Quiero iniciar sesión con mis credenciales
  Para acceder a las funciones permitidas para mi cuenta

  Scenario: Inicio de sesión con credenciales válidas
    Given que existe una cuenta de prueba activa
    And el usuario se encuentra en la página de inicio de sesión
    When ingresa credenciales válidas y envía el formulario
    Then el sistema permite el acceso
    And muestra el panel correspondiente al tipo de usuario

  Scenario: Inicio de sesión con contraseña incorrecta
    Given que existe una cuenta de prueba activa
    And el usuario se encuentra en la página de inicio de sesión
    When ingresa una contraseña incorrecta y envía el formulario
    Then el sistema deniega el acceso
    And muestra un mensaje de error comprensible
```

Este ejemplo no debe presentarse como prueba ejecutada hasta que el equipo lo automatice y lo corra. Usar cuentas ficticias y ocultar correos, tokens, contraseñas y datos personales en las capturas.

### Qué incluir en el informe

- Propósito breve de BDD y herramienta elegida, con versión si se conoce.
- Funcionalidades y rol de usuario cubiertos.
- Tabla de escenarios con nombre, resultado esperado y estado (aprobado/fallido).
- Fragmentos representativos de los archivos `.feature` y ubicación en el repositorio.
- Resultado real de la ejecución y comando utilizado.
- Hallazgos o defectos detectados y su estado.

### Capturas/evidencias recomendadas

1. Archivo `.feature` abierto mostrando los escenarios Given–When–Then.
2. Terminal o reporte del runner mostrando total de escenarios y estado final.
3. Si se usa navegador automatizado, captura o reporte HTML con el flujo realizado; ocultar información sensible.

No basta una captura de escenarios escritos: la rúbrica habla de pruebas, por eso debe verse también una ejecución real.

## Punto 6.1.4 — Core System Tests

### Qué hacer

Probar la aplicación integrada en los dos tamaños/contextos solicitados por la rúbrica: navegador de escritorio y vista móvil. Se puede usar Playwright (emulación de dispositivos móviles) para automatizar el navegador y complementar con revisión manual en un teléfono real si está disponible. La emulación comprueba viewport y comportamiento del navegador móvil, pero no equivale a probar todos los dispositivos físicos.

Elegir flujos completos que realmente existan, por ejemplo:

1. Navegar a inicio de sesión, autenticarse y llegar al panel.
2. Abrir establecimientos y consultar el detalle de uno.
3. Consultar dispositivos o información de monitoreo.
4. Probar una condición de error, como credenciales inválidas o API no disponible, y verificar el mensaje mostrado.

En cada caso observar: navegación y enlaces, interacción con formularios y botones, solicitud/respuesta de la API, datos presentados y comportamiento ante errores. Registrar ambiente y fecha, navegador/viewport, precondiciones, pasos, resultado esperado, resultado observado y estado.

### Matriz sencilla de resultados

| ID | Flujo | Entorno | Resultado esperado | Resultado observado | Estado |
|---|---|---|---|---|---|
| SYS-01 | Inicio de sesión válido | Web escritorio | Acceso al panel | Completar tras ejecutar | Pendiente |
| SYS-02 | Inicio de sesión válido | Vista móvil | Acceso al panel y controles utilizables | Completar tras ejecutar | Pendiente |
| SYS-03 | Consulta de establecimientos | Web y móvil | Se muestran datos autorizados | Completar tras ejecutar | Pendiente |
| SYS-04 | Error de autenticación/API | Web y móvil | Se informa el error sin bloquear la interfaz | Completar tras ejecutar | Pendiente |

Cambiar o quitar los flujos que no existan en el producto. No rellenar resultados por anticipado.

### Capturas/evidencias recomendadas

1. Prueba corriendo en escritorio: página y resultado del flujo, sin datos sensibles.
2. Prueba en viewport móvil o dispositivo real: pantalla del flujo y evidencia del resultado.
3. Reporte del runner con pruebas aprobadas/fallidas.
4. Cuando aporte valor, evidencia de la petición/respuesta API (Swagger, panel de red o log sanitizado), sin publicar tokens ni credenciales.
5. La captura de Lighthouse que ya tienen puede incluirse como **evidencia complementaria**. Anotar fecha, URL evaluada, modo/dispositivo y puntajes legibles. No presentarla como sustituto de los casos funcionales.

### Qué incluir en el informe

- Alcance del sistema probado (landing, frontend, backend/API y ambiente).
- Herramienta y configuración: navegador, resolución o viewport móvil y URL/ambiente.
- Casos de extremo a extremo y resultados reales.
- Evidencias numeradas con pie de figura y referencia desde el texto.
- Defectos encontrados, impacto y corrección o estado pendiente.
- Resumen: cuántas pruebas pasaron, fallaron o quedaron bloqueadas.

## Organización de las evidencias

Guardar capturas sin secretos en una carpeta como `assets/testing/` y nombrarlas claramente, por ejemplo:

- `bdd-feature-login.png`
- `bdd-run-results.png`
- `system-test-desktop-login.png`
- `system-test-mobile-login.png`
- `system-test-api-error.png`
- `lighthouse-landing-desktop.png`

En Markdown insertar con una leyenda, por ejemplo:

```markdown
![Ejecución de escenarios BDD de inicio de sesión](../assets/testing/bdd-run-results.png)

**Figura X.** Resultado de la ejecución automatizada de escenarios BDD.
```

## Prompt para pedir ayuda a Claude

Comparte con Claude el repositorio del **frontend y, si está separado, del backend**, además de esta guía y la rúbrica. Puedes enviarle este texto:

> Necesito completar en el informe académico los puntos 6.1.3 Core Behavior-Driven Development (BDD) y 6.1.4 Core System Tests para KairoLabs. Revisa primero el código y dime qué flujos están implementados de verdad, qué stack y pruebas ya existen y qué herramienta BDD y de pruebas de sistema encaja con el proyecto. No inventes funciones ni resultados, no ejecutes pruebas contra producción y no muestres credenciales/tokens. Propón escenarios Given–When–Then para los flujos existentes, incluyendo casos exitosos y de error; luego implementa pruebas automatizadas compatibles con el repositorio y dime los comandos exactos para ejecutarlas. Para pruebas de sistema, cubre los flujos completos en escritorio y viewport móvil, incluida la interacción con la API. Después de ejecutar, resume resultados reales, fallos y capturas/reportes que debo guardar. Finalmente redacta ambos apartados del informe en español, distinguiendo claramente BDD de pruebas de sistema y dejando Lighthouse solo como evidencia complementaria. Si falta información o una función no existe, indícalo en vez de asumirla.

Pídele a Claude que no afirme que algo pasó si no existe salida de ejecución verificable. Luego incorpora al informe solo los escenarios y resultados que el equipo haya confirmado.
