# 06 Estimación y Métricas de Software

## Guía de Estudio: Estimación de Software en la Era de la Inteligencia Artificial

Bienvenido a esta unidad. El objetivo de este material es comprender cómo los equipos de desarrollo calculan cuánto tiempo, esfuerzo y dinero costará construir un sistema informático, y cómo las herramientas de Inteligencia Artificial actuales están cambiando estas reglas de juego.

---
## Desarrollo Teórico

### 1. ¿Por qué es tan difícil estimar en software?
A diferencia de la construcción civil o la manufactura, el software es intangible y los requerimientos suelen cambiar sobre la marcha. Estimar significa predecir el futuro bajo condiciones de incertidumbre. Una mala estimación genera retrasos, sobrecostos o agotamiento (*burnout*) en el equipo de desarrollo.

### 2. Las 3 Etapas Clave de la Estimación
Para estimar un proyecto de forma profesional, debemos seguir un orden lógico:
1. **Tamaño:** ¿Qué tan grande es el sistema? (Se mide tradicionalmente en Líneas de Código - KLOC, o modernamente en Puntos de Historia basados en la complejidad).
2. **Esfuerzo:** ¿Cuántas **horas-hombre** o **meses-hombre** tomará escribir ese tamaño?
3. **Duración y Costo:** Traducir el esfuerzo en tiempo de calendario real (ej. si se necesitan 100 horas y tengo 2 programadores, tomará menos semanas) y calcular el costo financiero.

### 3. Estimación bajo Incertidumbre: Método PERT (3 Puntos)
Como no somos adivinos, el método PERT propone calcular el **Esfuerzo Esperado ($E$)** utilizando tres escenarios posibles:

$$E = \frac{O + 4M + P}{6}$$

* **$O$ (Optimista):** El tiempo que tomaría si **todo sale perfecto** y sin ningún tipo de bloqueo técnico.
* **$M$ (Más Probable):** El tiempo realista basado en proyectos anteriores similares y con interrupciones normales.
* **$P$ (Pesimista):** El peor escenario posible (ej. problemas graves con librerías, bugs complejos o curvas de aprendizaje largas).

> ** Importante en la era moderna:** Al calcular estos valores, ya no solo debes contar el tiempo de tipeo de código. Debes incluir obligatoriamente el tiempo de **configuración del entorno, pruebas unitarias y *Code Review* (revisión de código)**.

### 4. El Impacto de la Inteligencia Artificial Generativa
Hoy en día, herramientas como *GitHub Copilot, Cursor, Claude o ChatGPT* aceleran notablemente la escritura de código repetitivo (*boilerplate*), lo que reduce el tiempo del escenario **Optimista ($O$)**. 
Sin embargo, la IA también introduce un fenómeno nuevo: el código se escribe más rápido, pero **aumenta la carga en la revisión de código y pruebas de integración**, ya que se debe validar minuciosamente que la IA no haya introducido vulnerabilidades o lógica incorrecta.

---

## Trabajo Práctico Guiado: "Estimación Híbrida (Tradicional + IA)"

### Consigna
Su objetivo como líder de proyecto es estimar el esfuerzo en horas para desarrollar un **Módulo de Autenticación de Usuarios (Login y Registro en Base de Datos)** para una aplicación web. Deberá realizar una comparativa entre un desarrollo tradicional y un desarrollo asistido por IA.

---

### Paso a Paso para Resolver la Actividad:

#### Paso 1: Definir los escenarios sin asistencia de IA (Desarrollo Tradicional)
Imagina que el equipo programa de forma convencional (buscando documentación en Google y escribiendo todo desde cero). Define tus tres valores en horas:
* **$O_{trad}$ (Optimista):** ¿Cuántas horas en el mejor de los casos? *(Ej: 10 horas)*
* **$M_{trad}$ (Más Probable):** ¿Cuántas horas habitualmente? *(Ej: 16 horas)*
* **$P_{trad}$ (Pesimista):** ¿Cuántas horas si surgen problemas de conexión a la BD? *(Ej: 30 horas)*

#### Paso 2: Calcular el Esfuerzo Tradicional con PERT
Aplica la fórmula:
$$E_{trad} = \frac{O_{trad} + (4 \times M_{trad}) + P_{trad}}{6}$$
*(Ejemplo con los valores anteriores: $\frac{10 + (4 \times 16) + 30}{6} = \frac{10 + 64 + 30}{6} = \frac{104}{6} \approx 17.3 \text{ horas}$)*

#### Paso 3: Definir los escenarios utilizando Asistentes de IA (GitHub Copilot / ChatGPT)
Ahora, plantea cómo cambian los tiempos si el programador utiliza IA para autocompletar funciones y generar estructuras base:
* **$O_{ia}$ (Optimista):** La codificación inicial es mucho más rápida. *(Ej: 6 horas)*
* **$M_{ia}$ (Más Probable):** El tiempo realista considerando que ahorras tiempo en escribir código, pero inviertes más tiempo revisando lo que sugirió la IA. *(Ej: 12 horas)*
* **$P_{ia}$ (Pesimista):** Si la IA alucina código obsoleto y tardas en depurarlo. *(Ej: 22 horas)*

#### Paso 4: Calcular el Esfuerzo con IA con PERT
Aplica nuevamente la fórmula con los nuevos valores:
$$E_{ia} = \frac{O_{ia} + (4 \times M_{ia}) + P_{ia}}{6}$$

#### Paso 5: Conclusión y Análisis Crítico (Entregable)
Redacta un breve informe (de 10 a 15 renglones) respondiendo:
1. ¿Cuál fue la diferencia numérica en horas entre ambos métodos según el cálculo PERT?
2. ¿En qué etapa específica del desarrollo sentiste o estimas que la IA aportó mayor velocidad?
3. ¿Hubo alguna etapa donde utilizar IA pudo haber hecho el proceso más lento o demandado mayor atención? ¿Por qué?