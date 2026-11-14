# Capítulo VII: DevOps Practices

Este capítulo describe las prácticas de **DevOps** implementadas para el ecosistema digital de **KairoLabs**, desarrollado por **Aether System** para el curso **1ASI0732 - Diseño de Experimentos de Ingeniería de Software**, ciclo **2026-20**. Se detalla la automatización de los procesos de integración continua (*Continuous Integration*), entrega continua (*Continuous Delivery*), despliegue continuo (*Continuous Deployment*) y la infraestructura de monitoreo continuo (*Continuous Monitoring*) en producción.

---

## 7.1. Continuous Integration

### 7.1.1. Tools and Practices.

*(Sección pendiente de desarrollo)*

### 7.1.2. Build & Test Suite Pipeline Components.

*(Sección pendiente de desarrollo)*

---

## 7.2. Continuous Delivery

### 7.2.1. Tools and Practices.

*(Sección pendiente de desarrollo)*

### 7.2.2. Stages Deployment Pipeline Components.

*(Sección pendiente de desarrollo)*

---

## 7.3. Continuous Deployment

### 7.3.1. Tools and Practices.

*(Sección pendiente de desarrollo)*

### 7.3.2. Production Deployment Pipeline Components.

*(Sección pendiente de desarrollo)*

---

## 7.4. Continuous Monitoring

El monitoreo continuo (*Continuous Monitoring*) en la práctica DevOps de KairoLabs asegura la supervisión proactiva y en tiempo real del ecosistema digital (Frontend Web y servicios en producción). Su objetivo primordial es identificar tempranamente anomalías operativas, degradaciones en la latencia, saturación de peticiones o caídas de servicio (*downtime*) antes de que perjudiquen las operaciones de las clínicas, farmacias y hospitales que confían en el sistema para la trazabilidad y preservación de medicamentos sensibles.

### 7.4.1. Tools and Practices

Para garantizar la observabilidad integral de KairoLabs, el equipo adoptó un enfoque híbrido que combina monitoreo sintético periódico con análisis de telemetría pasiva en el borde de la red:

**Tabla 16**

*Herramientas y prácticas operativas de monitoreo continuo en KairoLabs*

| Herramienta | Tipo de Monitoreo | Métrica Principal Supervisada | Práctica DevOps Implementada |
| :--- | :---: | :--- | :--- |
| **UptimeRobot** | Monitoreo Sintético Externo | Disponibilidad global (*Uptime %*), latencia de conexión (*TTFB* en ms) y códigos de estado HTTP (200 OK vs 5xx/Timeout). | Sondeos automáticos cada 5 minutos mediante solicitudes HTTP `HEAD`/`GET` desde nodos distribuidos globalmente. |
| **Vercel Analytics & Logs** | Observabilidad en Edge Network | Métricas de rendimiento (*Core Web Vitals*: LCP, FID, CLS), volumen de tráfico concurrente y registros de error en tiempo real. | Ingesta pasiva de registros en los nodos perimetrales del CDN sin penalizar el rendimiento del cliente ni consumir recursos extra. |
| **Axios Runtime Interceptors** | Diagnóstico en Cliente Web | Excepciones no controladas de JavaScript, interrupciones de red y fallos de autenticación JWT. | Manejo centralizado de excepciones en la capa de infraestructura del frontend (`base-api.js`), capturando eventos anómalos. |

*Nota.* Elaboración propia basada en la arquitectura de observabilidad desplegada para KairoLabs.

Las prácticas operativas clave implementadas incluyen:
* **Monitoreo Proactivo de Disponibilidad:** Detección automática e inmediata de interrupciones de servicio sin depender del reporte manual de los operadores hospitalarios.
* **Correlación de Despliegues e Incidentes:** Vinculación directa entre cada nuevo despliegue en producción y el impacto en las tasas de error o latencia, agilizando decisiones de rollback o parches urgentes.

---

### 7.4.2. Monitoring Pipeline Components

El pipeline de monitoreo continuo opera mediante un flujo desacoplado compuesto por cuatro fases estructurales: ingesta y sondaje sintético, procesamiento analítico en la nube, visualización en paneles de control y derivación condicional de eventos.

**Figura 42**

*Arquitectura de componentes del pipeline de monitoreo continuo en KairoLabs*

<p align="center">
  <img src="../assets/chapter-7/figures/CONTINUOUS-MONITORING-PIPELINE.jpg" alt="Pipeline de Monitoreo Continuo DevOps de KairoLabs" width="1000">
</p>

*Nota.* Arquitectura del pipeline de observabilidad continua de KairoLabs, detallando la interacción entre sondas sintéticas externas, la red perimetral de Vercel, el motor analítico de agregación, los dashboards de salud operativa y el módulo de alertas. Elaboración propia.

Los componentes principales que articulan este pipeline son:

1. **Componente de Ingesta y Sondaje Sintético:**
   * Agentes distribuidos de UptimeRobot envían solicitudes periódicas hacia la URL pública de producción (`https://landing-page-kairolabs.vercel.app`), midiendo el tiempo de resolución DNS, conexión TCP y recepción del primer byte (*Time to First Byte* - TTFB).
   * La infraestructura perimetral de Vercel captura los metadatos de cada petición entrante de usuarios reales (código de respuesta, región geográfica, ruta de vista y duración de renderizado).
2. **Componente de Agregación y Procesamiento Analítico:**
   * Motor de procesamiento que consolida la telemetría en ventanas temporales para calcular el porcentaje de disponibilidad acumulado (acorde al objetivo SLA $\ge 99.5\%$) y la latencia media de respuesta.
3. **Componente de Visualización y Dashboard de Salud:**
   * Paneles unificados donde el equipo técnico inspecciona el historial de disponibilidad, curvas de tráfico y registros de excepciones en vivo.

---

### 7.4.3. Alerting Pipeline Components

El componente de alertas define la lógica condicional, umbrales y reglas operativas que determinan cuándo una variación de telemetría debe clasificarse como un incidente operativo:

* **Umbral de Caída Crítica (*Down State*):** Si dos sondeos consecutivos devuelven un código de error de servidor (`500 Internal Server Error`, `502 Bad Gateway`, `503 Service Unavailable`) o un tiempo de espera agotado (*Connection Timeout*), el estado de la aplicación cambia de *Up* a *Down*.
* **Umbral de Degradación de Rendimiento (*High Latency Warning*):** Se genera una alerta de advertencia si la latencia promedio supera los 2500 ms de forma continua en una ventana de 10 minutos.
* **Mecanismo de Confirmación Multinodal:** Para mitigar falsos positivos provocados por congestión transitoria en un nodo de red aislado, la alerta crítica solo se consolida si la indisponibilidad es corroborada por al menos dos nodos geográficos distintos.

---

### 7.4.4. Notification Pipeline Components

El pipeline de notificaciones gestiona el despacho oportuno y el enrutamiento de las alertas hacia los canales de comunicación del equipo técnico:

* **Canal Primario de Alerta Inmediata (Correo Electrónico SMTP):** Despacho automatizado de un correo electrónico de alta prioridad hacia los responsables técnicos con el informe del evento (marca de tiempo exacta, código HTTP devuelto y URL afectada).
* **Notificación de Recuperación y Medición de MTTR:** En cuanto el pipeline detecta que los sondeos retornan a un estado consistente de `200 OK`, emite una notificación de resolución calculando el tiempo total de caída (*downtime duration*), métrica indispensable para estimar el tiempo medio de recuperación (*Mean Time to Recovery* - MTTR).
