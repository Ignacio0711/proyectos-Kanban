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

## Ejemplo Resuelto: Comparativa de Estimación

Para ilustrar el procedimiento, analicemos el caso de estimación para el desarrollo de un **Módulo de Autenticación de Usuarios (Login, Registro con JWT y validaciones en Base de Datos)**.

### Caso A: Desarrollo Tradicional (Sin IA)
Un desarrollador trabaja consultando documentación técnica convencional y escribiendo el código de manera manual.

1. **Definición de Escenarios:**
   * $O_{trad} = 10 \text{ horas}$ (La integración no presenta complicaciones).
   * $M_{trad} = 16 \text{ horas}$ (Flujo de trabajo habitual con ajustes menores).
   * $P_{trad} = 30 \text{ horas}$ (Aparecen inconvenientes de configuración en la base de datos o en la firma de tokens).

2. **Cálculo del Esfuerzo Esperado con PERT:**
   $$E_{trad} = \frac{10 + 4(16) + 30}{6} = \frac{10 + 64 + 30}{6} = \frac{104}{6} \approx 17.33 \text{ horas}$$

---

### Caso B: Desarrollo Asistido por Inteligencia Artificial
El desarrollador utiliza herramientas de IA para autocompletar código y generar estructuras base de las funciones.

1. **Definición de Escenarios:**
   * $O_{ia} = 5 \text{ horas}$ (La IA genera la estructura base y los tests casi de forma inmediata).
   * $M_{ia} = 11 \text{ horas}$ (Se agiliza la codificación, pero se invierte tiempo en auditar la lógica y corregir errores del asistente).
   * $P_{ia} = 22 \text{ horas}$ (La IA sugiere métodos obsoletos o con vulnerabilidades de seguridad, demandando depuración manual).

2. **Cálculo del Esfuerzo Esperado con PERT:**
   $$E_{ia} = \frac{5 + 4(11) + 22}{6} = \frac{5 + 44 + 22}{6} = \frac{71}{6} \approx 11.83 \text{ horas}$$

---

### Comparativa de Resultados

| Métrica | Desarrollo Tradicional | Desarrollo con IA | Diferencia |
| :--- | :---: | :---: | :---: |
| **Escenario Optimista ($O$)** | $10 \text{ hs}$ | $5 \text{ hs}$ | $-50\%$ |
| **Escenario Más Probable ($M$)** | $16 \text{ hs}$ | $11 \text{ hs}$ | $-31.25\%$ |
| **Escenario Pesimista ($P$)** | $30 \text{ hs}$ | $22 \text{ hs}$ | $-26.67\%$ |
| **Esfuerzo Esperado PERT ($E$)** | **$17.33 \text{ hs}$** | **$11.83 \text{ hs}$** | **$-31.73\%$** |

**Conclusión del ejemplo:** El uso de asistentes de IA permite una reducción estimada del **$31.73\%$** del esfuerzo total esperado en este módulo particular.

---

## Trabajo Práctico: Estimación de un Módulo de Software

### Consigna
Asuma el rol de líder de proyecto y realice la estimación del esfuerzo en horas para el desarrollo de un **Módulo de Reportes y Exportación de Datos (en formatos PDF y Excel con filtros personalizados)**.

Deberá plantear los dos escenarios posibles (sin IA y con IA) y presentar los resultados fundamentados.

---

### Guía de Pasos para Completar la Actividad:

1. **Definir los valores para el desarrollo tradicional (Sin IA):**
   Determine y justifique los valores en horas para $O_{trad}$, $M_{trad}$ y $P_{trad}$.
2. **Calcular el Esfuerzo Tradicional ($E_{trad}$):**
   Aplique la fórmula de PERT utilizando sus valores definidos.
3. **Definir los valores para el desarrollo asistido por IA:**
   Establezca los valores en horas para $O_{ia}$, $M_{ia}$ y $P_{ia}$, considerando el ahorro de tiempo en codificación y el tiempo dedicado a la revisión de código.
4. **Calcular el Esfuerzo con IA ($E_{ia}$):**
   Aplique nuevamente la fórmula de PERT.
5. **Redactar un Informe Final:**
   Elabore una breve conclusión argumentando:
   * ¿Cuál es el porcentaje de reducción (o incremento) de esfuerzo obtenido?
   * ¿En qué tareas específicas considera que la IA aportó mayor eficiencia y en cuáles requirió mayor supervisión humana?