# Formulación y Evaluación de Proyectos de Software

Bienvenido al repositorio oficial de la materia. Este espacio contiene los recursos didácticos, guías prácticas, diapositivas y casos de estudio para abordar la gestión, estimación y evaluación de proyectos de software en el contexto del desarrollo moderno.

---

## Unidad: Estimación de Software en la Era de la Inteligencia Artificial

### Objetivos de Aprendizaje
* Comprender la evolución de los modelos de estimación (de métricas tradicionales como COCOMO/KLOC hacia metodologías ágiles y métricas basadas en alcance/complejidad).
* Desglosar y analizar las tres etapas clave de la estimación: **Tamaño**, **Esfuerzo** y **Duración/Costo**.
* Evaluar el impacto de los asistentes de código generativo (GitHub Copilot, Cursor, Claude, ChatGPT) en el ciclo de vida del software.
* Aplicar técnicas cuantitativas de estimación bajo incertidumbre (**Técnica PERT / 3 Puntos**) considerando tiempos de prueba y *Code Review*.

---

## Conceptos Clave

### 1. Las 3 Etapas de la Estimación

```mermaid
flowchart LR
    A[1. Estimación del Tamaño] --> B[2. Estimación del Esfuerzo]
    B --> C[3. Estimación de Duración y Costos]
    
    subgraph Tamaño
    A1[Métricas: Puntos de Historia / Use Case Points / Historias de Usuario]
    end
    
    subgraph Esfuerzo
    B1[Horas/Hombre ajustadas por curva de adopción de IA]
    end
    
    subgraph Duración
    C1[Sprints, Costos Operativos y Licenciamiento]
    end