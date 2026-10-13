# 06 Estimación y Métricas de Software

## Guía de Estudio: Estimación de Software en la Era de la Inteligencia Artificial

El propósito de este material es que usted comprenda cómo los equipos de desarrollo calculan el tiempo, el esfuerzo y el costo requeridos para construir un sistema informático, y cómo la incorporación de herramientas de Inteligencia Artificial está transformando estas dinámicas de trabajo.

---

## Desarrollo Teórico

### 1. ¿Por qué resulta complejo estimar en software?
A diferencia de industrias tradicionales como la construcción civil, el software posee una naturaleza intangible y sus requerimientos suelen evolucionar a lo largo del tiempo. Estimar implica predecir el comportamiento del proyecto bajo condiciones de incertidumbre. Una estimación imprecisa suele derivar en sobrecostos, retrasos en la entrega o desgaste del equipo de trabajo.

### 2. Las 3 Etapas Clave de la Estimación
Para realizar una estimación profesional, es necesario seguir un orden lógico:
1. **Tamaño:** Determinación de la dimensión del sistema. Se mide tradicionalmente en Líneas de Código (KLOC) o mediante métricas basadas en complejidad (Puntos de Función o Puntos de Historia).
2. **Esfuerzo:** Cálculo de las **horas-persona** o **meses-persona** requeridas para construir la dimensión estimada.
3. **Duración y Costo:** Traducción del esfuerzo en tiempo cronológico real (según la disponibilidad del equipo) y determinación del presupuesto financiero.

### 3. Estimación bajo Incertidumbre: Método PERT (3 Puntos)
Frente a la falta de certezas absolutas, el método PERT permite obtener un **Esfuerzo Esperado ($E$)** ponderando tres escenarios:

$$E = \frac{O + 4M + P}{6}$$

* **$O$ (Optimista):** El tiempo necesario si el proceso se desarrolla **sin imprevistos ni bloqueos técnicos**.
* **$M$ (Más Probable):** El tiempo realista basado en la experiencia previa del equipo y en condiciones normales de trabajo.
* **$P$ (Pesimista):** El escenario desfavorable en el que surgen problemas técnicos significativos, dependencias complejas o curvas de aprendizaje no previstas.

> **Consideración actual:** Al calcular estos valores, no solo debe contemplarse el tiempo de codificación pura. Se deben incluir explícitamente las etapas de **configuración de entorno, pruebas automatizadas y revisión de código (*Code Review*)**.

### 4. El Impacto de la Inteligencia Artificial Generativa
El uso de asistentes como *GitHub Copilot, Cursor, Claude o ChatGPT* acelera la generación de código repetitivo (*boilerplate code*), reduciendo significativamente el escenario **Optimista ($O$)**. 

Sin embargo, esto traslada la carga de trabajo hacia otras etapas: si bien la codificación inicial se agiliza, **aumenta la necesidad de realizar revisiones de código exhaustivas y pruebas de integración**, con el objetivo de validar la calidad, la seguridad y la precisión de las soluciones generadas.

---
## Trabajo práctico: estimación de un proyecto con asistencia de IA

### Objetivo

El objetivo de este trabajo práctico es que usted formule y evalúe un proyecto pequeño de software. En este se utiliza inteligencia artificial. No se evaluará su capacidad para programar de forma profesional, sino su habilidad para definir un problema, probar una solución, estimar el esfuerzo mediante métodos formales, identificar riesgos y justificar una decisión técnica y económica fundamentada.

### Secuencia de trabajo

1. Leer atentamente el ejemplo guiado sobre una biblioteca que se presenta en la **Parte A**.
2. Aplicar la misma metodología y completar las planillas correspondientes para el caso del sistema de gestión de turnos detallado en la **Parte B**.
3. Presentar el prototipo funcional o la evidencia concreta de las pruebas realizadas, las planillas de estimación de tiempos con PERT, y una recomendación final justificada.

---

# Parte A. Ejemplo guiado: préstamos de una biblioteca

Una biblioteca registra actualmente los préstamos en un cuaderno físico, lo que le genera graves dificultades para saber con precisión qué libros siguen prestados y quién los tiene en su poder. Para resolver este inconveniente, se propone crear un prototipo informático sencillo.

## Planilla 1. Formulación y alcance

| Campo | Ejemplo |
| --- | --- |
| **Problema** | Cuesta consultar de forma rápida qué libros están prestados y a qué persona. |
| **Usuario** | Bibliotecario/a o voluntario/a de la institución. |
| **Objetivo** | Registrar préstamos y consultar las devoluciones pendientes de manera digital. |
| **Incluye** | Registrar un préstamo, listar los préstamos activos, registrar la devolución de un libro y buscar registros por título o persona. |
| **No incluye** | Multas por retraso, avisos automáticos por correo o mensajería, catálogo público en línea ni lector óptico de códigos de barras. |
| **Criterio de éxito** | El sistema debe permitir registrar un préstamo, encontrarlo en la lista activa y marcarlo correctamente como devuelto. |
| **Supuestos y límites** | Se utilizarán datos ficticios para las pruebas y una sola persona pondrá a prueba el prototipo. |

**Regla fundamental:** antes de solicitarle a la IA que construya o genere código para el sistema, usted debe definir con precisión qué problema resolverá y qué quedará estrictamente fuera del alcance.

## Planilla 2. Funcionalidades y pruebas

Para cada funcionalidad desarrollada, usted debe indicar cómo comprobará que funciona correctamente. El resultado observado debe completarse únicamente después de ejecutar la prueba.

| Funcionalidad | Prueba a realizar | Resultado observado |
| --- | --- | --- |
| **Registrar préstamo** | Registrar el libro "El Principito" a nombre de "Ana" y buscarlo posteriormente en la lista general. | *Completar después de realizar la prueba real.* |
| **Consultar préstamos activos** | Verificar visualmente que el libro prestado y la persona aparezcan reflejados en la lista activa. | *Completar después de realizar la prueba real.* |
| **Registrar devolución** | Marcar el préstamo como devuelto y consultar nuevamente la lista de préstamos activos. | *Completar después de realizar la prueba real.* |
| **Validar datos** | Intentar guardar el registro sin ingresar el título del libro o sin especificar la persona. | *Completar después de realizar la prueba real.* |

**Nota importante:** Los resultados de esta tabla deben surgir de pruebas reales ejecutadas por usted; no debe dar por sentado que funcionan correctamente solo porque la IA generó el código.

## Planilla 3. Registro del uso de IA

Como usted utiliza técnicas de desarrollo asistido (*vibe coding*), es fundamental que registre y mida el tiempo real que le toma interactuar con la herramienta y corregir lo que genera.

| Tarea | Qué se pidió a la IA | Resultado obtenido y correcciones necesarias | Tiempo (min) |
| --- | --- | --- | --- |
| **Crear formulario** | Crear campos para libro y persona, junto con un botón para guardar. | El formulario se generó, pero hubo que comprobar manualmente si realmente guardaba los datos. | 15 |
| **Mostrar préstamos** | Mostrar los registros almacenados en una tabla estructurada. | La tabla apareció en pantalla; quedó pendiente comprobar la persistencia de los datos. | 12 |
| **Registrar devolución** | Agregar una acción para marcar un préstamo como devuelto. | Se cambió el estado del registro; faltó probar otros casos límite. | 18 |
| **Probar datos incompletos** | Impedir el guardado si faltan datos obligatorios en el formulario. | Se probó el formulario vacío; faltaron validaciones adicionales sugeridas. | 10 |

*Los tiempos expuestos son ilustrativos. Cada equipo debe registrar los tiempos reales que le insuma su propio trabajo.*

## Planilla 4. Estimación de tiempos con PERT

Dado que en el desarrollo con IA a menudo se desconoce el esfuerzo real que implicará corregir errores, usted debe estimar el esfuerzo pendiente utilizando la técnica PERT. Las estimaciones deben expresarse en **horas-persona** (esfuerzo total de trabajo), y no en horas de reloj calendario.

* **O (Optimista):** El escenario en el que casi no se presentan problemas ni errores imprevistos.
* **M (Más probable):** El escenario que se presenta en condiciones normales de trabajo.
* **P Pesimista):** El escenario donde aparecen complicaciones importantes que todavía pueden resolverse.

Fórmula de cálculo para el esfuerzo esperado ($E$):


$$E = \frac{O + 4M + P}{6}$$

| Actividad pendiente | O | M | P | Esfuerzo esperado ($E$) |
| --- | --- | --- | --- | --- |
| Completar registro de préstamos | 1 | 2 | 5 | 2,33 |
| Completar consulta y búsqueda | 1 | 2 | 4 | 2,17 |
| Completar devolución | 1 | 2 | 5 | 2,33 |
| Probar y corregir errores | 2 | 4 | 8 | 4,33 |
| Preparar la entrega final | 1 | 2 | 3 | 2,00 |
| **Total** | **6** | **14** | **25** | **13,16** |

**Recuerde la diferencia conceptual:** El **esfuerzo** es la cantidad total de trabajo requerido. La **duración** es el tiempo de calendario necesario. Ambas magnitudes no son iguales, ya que la duración depende de la disponibilidad de los integrantes y de qué tareas puedan ejecutarse en paralelo.

## Planilla 5. Comparación hipotética con IA y sin IA

Para evaluar el impacto real de utilizar herramientas de inteligencia artificial, usted debe comparar un mismo alcance y nivel de calidad estimado bajo ambos escenarios.

| Escenario | O | M | P | $E$ PERT |
| --- | --- | --- | --- | --- |
| **Sin IA** | 16 | 24 | 40 | 25,33 h-persona |
| **Con IA** | 10 | 18 | 32 | 19,00 h-persona |

Fórmula para calcular la reducción porcentual estimada:


$$\text{Reducción estimada} = \frac{E_{\text{sin IA}} - E_{\text{con IA}}}{E_{\text{sin IA}}} \times 100$$

En este ejemplo orientativo, la reducción estimada es aproximadamente del **25 %**. Este valor no demuestra que la IA siempre ahorre exactamente ese porcentaje, sino que representa una comparación hipotética basada en los parámetros elegidos por el evaluador.

## Planilla 6. Costos, riesgos y decisión

Para determinar la viabilidad económica del proyecto, supongamos una tarifa ficticia de referencia de $12.000 por cada hora-persona invertida:

| Concepto | Cálculo o descripción | Resultado |
| --- | --- | --- |
| **Esfuerzo estimado con IA** | Total de horas-persona obtenidas en la Planilla 4 | 19 h |
| **Tarifa** | Valor económico supuesto por hora-persona | $12.000 / h |
| **Costo del esfuerzo** | Esfuerzo estimado × Tarifa | $228.000 |
| **Otros costos** | Herramientas de desarrollo, alojamiento web, licencias, etc. | *Indicar si corresponden o colocar 0* |
| **Costo total** | Suma del costo del esfuerzo + otros costos | *Completar el valor final* |

### Identificación de riesgos y medidas de mitigación

| Riesgo identificado | Medida posible de respuesta o mitigación |
| --- | --- |
| Los datos ingresados no se guardan correctamente en el sistema. | Realizar pruebas exhaustivas para asegurar que los registros se conserven tras recargar. |
| La IA genera validaciones incompletas en los formularios. | Probar intencionalmente campos vacíos y casos límite (*edge cases*). |
| El equipo no logra corregir un error crítico generado por el código asistido. | Reducir el alcance del prototipo y solicitar revisión externa o asesoramiento. |
| Se exponen datos sensibles o personales durante las pruebas. | Utilizar estrictamente datos ficticios y revisar las condiciones de privacidad de la herramienta. |

**Ejemplo de decisión fundamentada:** Continuar con una prueba controlada del prototipo, pero abstenerse de utilizarlo con datos reales hasta comprobar fehacientemente que los registros se conservan de forma íntegra y que las funciones principales superan todas las pruebas previstas.

---

# Parte B. Trabajo práctico: sistema de gestión de turnos

## Situación planteada

Un consultorio médico o profesional organiza actualmente sus turnos de manera manual en planillas de papel. La persona encargada necesita una solución informática sencilla para consultar los turnos asignados a cada día, evitar duplicados en el mismo horario y obtener una lista ordenada de atención.

Para cumplir con esta consigna, su equipo deberá formular una solución pequeña, crear un prototipo funcional asistido por inteligencia artificial y evaluar formalmente su viabilidad técnica y económica.

**Advertencia importante:** Bajo ninguna circunstancia debe construir un sistema clínico complejo ni utilizar datos reales de pacientes reales; toda la información manipulada debe ser absolutamente ficticia.

## Actividades y entregables obligatorios

| Paso | Qué debe hacer usted | Entregable correspondiente |
| --- | --- | --- |
| **1. Formular** | Definir el problema principal, los usuarios, el objetivo, el alcance exacto y los criterios de éxito. | Planilla 1 (Versión del equipo) |
| **2. Definir pruebas** | Elegir entre 3 y 5 funciones clave y describir detalladamente cómo comprobará su correcto funcionamiento. | Planilla 2 (Versión del equipo) |
| **3. Crear prototipo** | Utilizar IA para generar el código, registrar las solicitudes realizadas, los resultados obtenidos y el tiempo insumido. | Prototipo funcional y Planilla 3 |
| **4. Probar** | Ejecutar las pruebas planificadas, registrando explícitamente qué funciona, qué falla y qué es necesario corregir. | Resultados detallados de pruebas |
| **5. Estimar** | Estimar mediante la técnica PERT el esfuerzo de las actividades pendientes, justificando rigurosamente los valores O, M y P. | Planilla 4 (Cálculos PERT) |
| **6. Comparar** | Estimar el mismo alcance de desarrollo trabajando con asistencia de IA y sin ella, distinguiendo claramente los datos observados de los supuestos. | Planilla 5 (Comparación de escenarios) |
| **7. Evaluar** | Calcular los costos totales del proyecto, identificar los riesgos principales, proponer mitigaciones y emitir una recomendación fundamentada. | Planilla 6 e Informe final escrito |

### Funcionalidades posibles a seleccionar (Elija entre 3 y 5)

* Registrar un turno indicando fecha, hora y nombre de paciente ficticio.
* Consultar de forma rápida los turnos programados para un día específico.
* Cambiar o cancelar un turno existente en la agenda.
* Detectar y evitar turnos duplicados asignados para el mismo horario y profesional.
* Impedir obligatoriamente que se guarden registros con campos obligatorios vacíos.

### Pruebas sugeridas para su validación

| Prueba a ejecutar | Qué debe comprobar el alumno |
| --- | --- |
| **Registrar un turno válido** | El turno ingresado aparece correctamente reflejado en la agenda general. |
| **Consultar un día sin turnos** | El sistema informa de manera clara que no existen turnos programados para esa fecha. |
| **Omitir un dato obligatorio** | El sistema bloquea la acción y no permite guardar el registro incompleto. |
| **Intentar crear un turno duplicado** | El sistema aplica la regla de validación definida por el equipo para rechazar el traslape. |
| **Cancelar un turno** | El turno seleccionado deja de aparecer en el listado de turnos activos. |

**Criterio orientativo:** No incluya ninguna función dentro de su prototipo si no puede explicar con precisión matemática y lógica cómo comprobar su correcto funcionamiento mediante pruebas empíricas. Debe registrar siempre los resultados reales obtenidos.

---

## Plantillas vacías para completar por el equipo

### Planilla 1. Formulación y alcance

| Campo | Respuesta detallada del equipo |
| --- | --- |
| **Problema** |  |
| **Usuario** |  |
| **Objetivo** |  |
| **Funcionalidades incluidas** |  |
| **Funcionalidades excluidas** |  |
| **Criterio de éxito** |  |
| **Supuestos y restricciones** |  |

### Planilla 2. Funcionalidades y pruebas

| Funcionalidad | Cómo se probará (Procedimiento) | Resultado esperado | Resultado observado (Real) |
| --- | --- | --- | --- |
| **1.** |  |  |  |
| **2.** |  |  |  |
| **3.** |  |  |  |
| **4.** |  |  |  |
| **5.** |  |  |  |

### Planilla 3. Registro de uso de IA

| Tarea de desarrollo | Solicitud o *prompt* enviado a la IA | Resultado obtenido y corrección requerida | Tiempo insumido (min) |
| --- | --- | --- | --- |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

### Planilla 4. Estimación de esfuerzo con PERT

| Actividad pendiente | $O$ (Optimista - h) | $M$ (Más probable - h) | $P$ (Pesimista - h) | Esfuerzo $E = \frac{O + 4M + P}{6}$ | Justificación técnica del equipo |
| --- | --- | --- | --- | --- | --- |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
|  |  |  |  |  |  |
| **Total** |  |  |  |  | **Esfuerzo total estimado:** |

### Planilla 5. Comparación de escenarios de desarrollo

| Escenario de trabajo | $O$ (h) | $M$ (h) | $P$ (h) | $E$ PERT | Base de la estimación |
| --- | --- | --- | --- | --- | --- |
| **Sin asistencia de IA** |  |  |  |  |  |
| **Con asistencia de IA** |  |  |  |  |  |

* **Reducción o incremento estimado del esfuerzo:** _________ %
* **¿Qué datos observaron empíricamente y cuáles supusieron?:**
---



### Planilla 6. Costos, riesgos y decisión final

| Concepto económico / operativo | Valor calculado |
| --- | --- |
| **Esfuerzo total estimado ($E$ en h-persona)** |  |
| **Tarifa de referencia por hora-persona** |  |
| **Costo total del esfuerzo** |  |
| **Otros costos asociados (infraestructura, herramientas, etc.)** |  |
| **Costo total estimado del proyecto** |  |

| Riesgo identificado | Probabilidad (Baja/Media/Alta) | Impacto (Bajo/Medio/Alto) | Medida concreta de respuesta o mitigación |
| --- | --- | --- | --- |
|  |  |  |  |
|  |  |  |  |
|  |  |  |  |

**Decisión final adoptada por el equipo:** (Seleccione o indique: *continuar / modificar el alcance / descartar el proyecto*)

**Justificación detallada:** ¿Qué evidencia empírica respalda la decisión tomada por ustedes y qué aspectos particulares faltan comprobar en el prototipo?

---

---

---

## Fórmulas matemáticas obligatorias que usted debe aplicar

* **Esfuerzo por actividad individual ($E_i$):**

$$E_i = \frac{O_i + 4M_i + P_i}{6}$$


* **Esfuerzo total del proyecto ($E_{\text{total}}$):**

$$E_{\text{total}} = \sum E_i$$


* **Costo monetario del esfuerzo:**

$$\text{Costo} = E_{\text{total}} \times \text{Tarifa por hora-persona}$$


* **Porcentaje de reducción del esfuerzo mediante el uso de IA:**

$$\text{Reducción (\%)} = \frac{E_{\text{sin IA}} - E_{\text{con IA}}}{E_{\text{sin IA}}} \times 100$$



*Nota aclaratoria:* Si el resultado de la comparación porcentual arroja un valor negativo, significa que la estimación realizada utilizando IA le insumió un esfuerzo mayor que haber desarrollado el proyecto sin ella.

---

## Criterios de evaluación

| Criterio de calificación | Ponderación porcentual |
| --- | --- |
| **Formulación del problema y claridad del alcance** | 20 % |
| **Uso crítico de las herramientas de IA y rigor en las pruebas** | 20 % |
| **Corrección en los cálculos matemáticos y justificación del método PERT** | 25 % |
| **Evaluación realista de costos, identificación de riesgos y solidez de la decisión** | 25 % |
| **Claridad, formalidad y prolijidad del informe final escrito** | 10 % |

**Aclaración importante:** Un prototipo funcional que falle o presente errores durante las pruebas **puede formar parte de un excelente trabajo práctico**, siempre y cuando el equipo presente evidencias claras de las pruebas realizadas, identifique con honestidad las limitaciones técnicas encontradas y fundamente con rigor qué acciones correctivas se deberían tomar. Tenga presente que un prototipo vistoso pero no probado rigurosamente no demuestra por sí solo que un proyecto de software sea viable.

---

## Estructura requerida para el informe final escrito

El informe escrito debe tener una extensión aproximada de **2 a 4 páginas**, redactado con rigor formal, donde usted y su equipo respondan de manera estructurada a las siguientes preguntas clave:

1. ¿Qué problema concreto busca resolver la solución informática desarrollada?
2. ¿Qué funcionalidades se incluyeron explícitamente en el alcance y qué quedó fuera del proyecto?
3. ¿Qué funcionó correctamente y qué falló de manera imprevista durante la ejecución de las pruebas empíricas?
4. ¿Cuál es el esfuerzo total en horas-persona, la duración estimada de calendario y el costo monetario calculado para el proyecto?
5. ¿Cuáles son los riesgos técnicos y operativos más importantes identificados por el equipo?
6. ¿Qué diferencias cuantitativas y cualitativas se estiman entre trabajar con asistencia de inteligencia artificial frente a hacerlo sin ella?
7. Desde el punto de vista técnico y económico, ¿conviene continuar con el desarrollo, modificar el alcance o descartar por completo el proyecto? Justifique su postura con los datos obtenidos.

**Conclusión conceptual:** Formular y evaluar un proyecto de software comienza siempre por comprender a fondo la naturaleza del problema que se pretende resolver. Las herramientas de inteligencia artificial pueden asistirlo con velocidad para generar prototipos de código mediante *vibe coding*, pero es responsabilidad ineludible del equipo técnico definir correctamente el alcance, probar rigurosamente los resultados obtenidos, estimar formalmente el trabajo pendiente utilizando métodos cuantitativos como PERT y justificar con argumentos sólidos cualquier decisión que se adopte en el ámbito profesional.