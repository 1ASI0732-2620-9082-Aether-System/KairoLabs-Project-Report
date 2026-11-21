# Capítulo VIII: Experiment-Driven Development

> Plantilla de estructura para completar el capítulo VIII.

## 8.1. Experiment Planning

### 8.1.1. As-Is Summary

### 8.1.2. Raw Material: Assumptions, Knowledge Gaps, Ideas, Claims

### 8.1.3. Experiment-Ready Questions

### 8.1.4. Question Backlog

### 8.1.5. Experiment Cards

## 8.2. Experiment Design

Esta sección presenta el diseño experimental de KairoLabs para contrastar nuestras hipótesis con evidencia. Integra la formulación de hipótesis, las métricas de negocio y medidas, las condiciones y escala de las pruebas, la selección de métodos, los objetivos de analítica, los indicadores clave y el seguimiento web y móvil. El diseño considera las necesidades del personal operativo de almacenes farmacéuticos y de los gestores de salud, y permite relacionar los resultados observados con decisiones concretas sobre el producto.

### 8.2.1. Hypotheses

Formulamos cinco hipótesis comprobables a partir de las necesidades del personal operativo y de los gestores de salud, así como de las funciones de monitoreo, alertas, trazabilidad, sensores y supervisión multisede de KairoLabs. Cada hipótesis establece un resultado medible y su hipótesis nula define el umbral que consideramos insuficiente para respaldar nuestra creencia. Las comparaciones se realizan respecto de una línea base; para evaluar la precisión de las lecturas, se contrastan los datos del sensor con un instrumento de referencia y una tolerancia previamente establecida.

| Question (Pregunta) | Belief (Creencia) | Hypothesis (Hipótesis de trabajo, H1) | Null Hypothesis (Hipótesis nula operativa, H0) |
| :--- | :--- | :--- | :--- |
| ¿El monitoreo continuo ayuda a reducir los incidentes de deterioro de medicamentos? | Creemos que las rondas y los registros manuales pueden dejar pasar desviaciones entre revisiones. Consultar lecturas continuas permitiría reconocer antes una condición crítica. | En los primeros tres meses del piloto, la tasa de incidentes de deterioro asociados a condiciones de almacenamiento disminuirá al menos **30 %** frente a la línea base de los mismos establecimientos. | La tasa de incidentes no alcanzará la reducción mínima del **30 %** frente a la línea base. |
| ¿Las alertas automáticas ayudan al personal a responder más rápido ante una desviación? | Creemos que una alerta inmediata puede acortar el tiempo entre detectar una lectura fuera de rango y registrar una acción. En la validación, el personal operativo prefirió recibir avisos en el celular y pidió poder registrar cómo atendió la alerta. | Durante el piloto, el tiempo mediano entre una lectura fuera de rango y el registro de una respuesta disminuirá al menos **25 %** frente al proceso sin notificación automática. | La reducción del tiempo mediano de respuesta será menor al **25 %**. |
| ¿El historial digital facilita reunir evidencia para una auditoría sanitaria? | Creemos que los registros en papel pueden quedar incompletos y tomar tiempo para reunirlos. En la entrevista de validación, el gestor sugirió contar con un historial exportable para auditorías. | Durante los primeros tres meses, el tiempo promedio para reunir los registros solicitados disminuirá al menos **20 %** frente al proceso manual. | La reducción del tiempo para reunir evidencia será menor al **20 %**. |
| ¿El registro automático mediante sensores mejora la precisión de las lecturas? | Creemos que transcribir varias lecturas al día añade trabajo y oportunidades de error. La integración de sensores IoT permitirá automatizar el registro y comparar sus lecturas con un instrumento de referencia. | En un piloto de tres meses, la proporción de lecturas correctas aumentará al menos **25 %** frente al registro manual. Se contrastará cada lectura con un instrumento de referencia y una tolerancia definida antes de la prueba. | El aumento de lecturas correctas será menor al **25 %**. |
| ¿La gestión centralizada mejora la eficiencia de supervisión y reduce las pérdidas entre varias sedes? | Creemos que los gestores que supervisan más de un almacén necesitan consolidar registros. En la validación, el gestor consideró útil revisar sus sedes desde un solo lugar y pudo registrar un establecimiento y asignarle un operador sin ayuda. | Durante los primeros seis meses, el dashboard multisede reducirá al menos **30 %** el tiempo promedio para revisar el estado de todos los establecimientos y disminuirá al menos **20 %** las pérdidas económicas documentadas por incidentes de almacenamiento, frente a la línea base. | La hipótesis no se respaldará si la reducción queda por debajo de **30 %** en el tiempo de supervisión o de **20 %** en las pérdidas económicas. |

**Lectura de las hipótesis y criterios de decisión**

Las cinco hipótesis se derivan de necesidades del proyecto y vinculan cada problema con un resultado que podemos observar: detección de incidentes, respuesta a alertas, preparación de evidencia, precisión de lecturas y eficiencia multisede. En la última hipótesis, el tiempo de supervisión y las pérdidas económicas son dos resultados relacionados con la gestión centralizada.

Para interpretar los resultados:

- **H1** expresa el cambio que esperamos observar y el umbral que respaldaría nuestra creencia.
- **H0** establece que ese umbral no se alcanza; por tanto, el resultado no respalda la hipótesis de trabajo.
- Si los datos respaldan **H0**, revisaremos las condiciones y los resultados, ajustaremos el diseño o reconsideraremos el supuesto antes de decidir si continuamos con la funcionalidad.

### 8.2.2. Domain Business Metrics

### 8.2.3. Measures

### 8.2.4. Conditions

### 8.2.5. Scale Calculations and Decisions

### 8.2.6. Methods Selection

### 8.2.7. Data Analytics: Goals, KPIs and Metrics Selection

### 8.2.8. Web and Mobile Tracking Plan

## 8.3. Experimentation

### 8.3.1. To-Be User Stories

### 8.3.2. To-Be Product Backlog

### 8.3.3. Pipeline-supported, Experiment-Driven To-Be Software Platform Lifecycle

#### 8.3.3.1. To-Be Sprint Backlogs

#### 8.3.3.2. Implemented To-Be Landing Page Evidence

#### 8.3.3.3. Implemented To-Be Frontend-Web Application Evidence

#### 8.3.3.4. Implemented To-Be Native-Mobile Application Evidence

#### 8.3.3.5. Implemented To-Be RESTful API and/or Serverless Backend Evidence

#### 8.3.3.6. Team Collaboration Insights

### 8.3.4. To-Be Validation Interviews

#### 8.3.4.1. Diseño de Entrevistas

#### 8.3.4.2. Registro de Entrevistas

## 8.4. Experiment Aftermath & Analysis

### 8.4.1. Analysis and Interpretation of Results

### 8.4.2. Re-scored and Re-prioritized Question Backlog

## 8.5. Continuous Learning

### 8.5.1. Shareback Session Artifacts: Learning Workflow

## 8.6. To-Be Software Platform Pre-launch

### 8.6.1. About-the-Product Intro Video

### 8.6.2. Resumen usando Gees Framework
