---
theme: seriph
title: Aplicación de RL y Transformers para el Aprendizaje de Idiomas
info: |
  Presentación del Trabajo Fin de Máster
  Máster Propio en Inteligencia Artificial
  Segunda Edición, Curso Académico 2024
transition: slide-left
colorSchema: light
layout: cover
defaults:
  layout: default
---

# Aplicación de RL y Transformers para el Aprendizaje de Idiomas

Julio Emanuel Suriano Bryk

---

# Contenido de la presentación:

1. Introducción y motivación
2. Arquitectura del sistema
3. Tecnologías clave
4. Demostración
5. Evaluación y resultados
6. Conclusiones


---
layout: section
---

# Introducción y motivación


---
layout: image-right

image: https://images.unsplash.com/photo-1424115087662-5845efc6b366?q=80&w=2576&auto=format&fit=crop&ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D
---

# ¿Por qué aprendizaje de idiomas?

<v-clicks>

* El aprendizaje de idiomas es un desafío global
* Más de 1.500 millones de personas estudian un segundo idioma
* La personalización es clave para el éxito
* La tecnología puede transformar esta experiencia

</v-clicks>

---
layout: fact
class: "![&>h1]:text-6xl"
---

# "La persona promedio necesita 10,000 horas para dominar un idioma usando métodos tradicionales"

## Malcolm Gladwell


---
class: -mt-6
---

```mermaid {scale: 0.8}
timeline
    title Evolución de Tecnologías de IA
    section La oportunidad
        2013-2015 : Reinforcement Learning
                  : Adaptación dinámica
        2016-2018 : Procesamiento de voz
                  : Práctica oral realista
        2018-2020 : LLMs
                  : Interacciones naturales
        2020-2023 : RAG
                  : Conocimiento contextualizado
```

---
layout: two-cols
---

# Objetivo general

Desarrollar un sistema de aprendizaje de idiomas que:

<v-clicks>

* Se adapte dinámicamente al nivel del estudiante
* Ofrezca interacciones conversacionales naturales
* Proporcione retroalimentación personalizada
* Integre práctica oral y escrita

</v-clicks>

::right::

<v-click>

```mermaid  {scale: 0.65}
flowchart TD
    A[Estudiante] --> B[Evaluación de Nivel]
    B --> C[Sistema Adaptativo]
    C --> D[Práctica Integrada]
    
    D --> E[Retroalimentación Personalizada]
    E --> F[Análisis de Progreso]
    F --> G[Ajuste Dinámico]
    G -->|Ciclo de Mejora| C
    
    classDef primary fill:#f9d5e5
    classDef secondary fill:#eeeeee
    classDef emphasis fill:#d3f0ee
    
    class A,B primary
    class C,D,D1,D2,D3,D4 secondary
    class E,F,G emphasis
```

</v-click>

---
layout: two-cols
---

# Flujo de interacción

Proceso iterativo y personalizado al usuario

1. Usuario selecciona situación práctica
2. Sistema genera contexto adaptado al nivel
3. Interacción conversacional con voz/texto
4. Análisis de la conversación y retroalimentación
5. Ajuste de dificultad en base a los resultados
6. Actualización del modelo de estudiante

::right::

```mermaid {scale: 0.75}
flowchart TD
    A[Selección de situación] -->|"Inicio"| B[Generación de contexto]
    B --> C[Interacción voz/texto]
    C --> D[Análisis y feedback]
    D --> E[Ajuste de dificultad]
    E --> F[Actualización perfil]
    F -->|"Ciclo iterativo"| A
    
    %% Estilo
    classDef paso1 fill:#ffcdd2,stroke:#c62828,stroke-width:1px
    classDef paso2 fill:#c8e6c9,stroke:#2e7d32,stroke-width:1px
    classDef paso3 fill:#bbdefb,stroke:#1565c0,stroke-width:1px
    classDef paso4 fill:#e1bee7,stroke:#6a1b9a,stroke-width:1px
    classDef paso5 fill:#ffe0b2,stroke:#ef6c00,stroke-width:1px
    classDef paso6 fill:#b2dfdb,stroke:#00695c,stroke-width:1px
    
    class A paso1
    class B paso2
    class C paso3
    class D paso4
    class E paso5
    class F paso6
```

---

# Objetivos específicos

```mermaid
mindmap
  root((Aprendizaje<br/>Inteligente))
    (Reinforcement Learning)
      [Optimización del aprendizaje]
      [Rutas personalizadas]
    (Grandes Modelos de Lenguajes)
      [Mejora de la interacción]
      [Diálogos naturales]
    (TTS y STT)
      [Habilidades completas]
      [Práctica oral]
    (Sistema RAG)
      [Acceso contextualizado]
      [Recursos educativos]
```

---
layout: section
---

# Arquitectura del sistema

---
class: "[&>.mermaid]:my-10"
---

# Arquitectura general

El sistema emplea una arquitectura modular y escalable a futuro.


```mermaid 

flowchart LR
    subgraph Client["Frontend"]
        UI[/"Interfaz de Usuario"/]
    end
    
    subgraph Core["Backend"]
        Asst["Sistema de Asistente"]
        Eval["Sistema de Evaluación"]
        Voice["Procesamiento de Voz"]
    end
    
    subgraph Store["Almacenamiento"]
        DB[(Bases de Datos)]
    end

    Client <--> Core
    Core <--> Store
    class UI client
    class Asst,Eval,Voice core
    class DB storage
    
```



<v-click>

### Componentes

* **Frontend**: Experiencia de usuario
* **Backend**: Lógica principal del asistante y procesamiento de voz.
* **Bases de datos**: Almacenamiento estructurado y vectorial

</v-click>


---
layout: two-cols
---

# Frontend 


* Arquitectura de tres capas: Interfaz, Central y Almacenamiento
* Desarrollado con [Next.js](https://github.com/vercel/next.js/) y componentes React especializados
* Gestión de estado con [Zustand](https://github.com/pmndrs/zustand) y [React Query](https://github.com/TanStack/query)
* Servicios integrados de API, voz y autenticación
* Almacenamiento local para preferencias y datos de sesión

::right::

```mermaid {scale: 0.7}
flowchart TB
    subgraph UI["Capa de Interfaz de Usuario"]
        Pages["Páginas Next.js"]
        Components["Componentes React"]
    end

    subgraph Core["Capa Central"]
        State["Gestión de Estado (Zustand & React Query)"]
        Services["Servicios del Cliente (API, Voz, Autenticación)"]
    end

    subgraph Storage["Capa de Almacenamiento"]
        ClientStorage["Almacenamiento del Navegador"]
    end

    UI --> Core
    Core <--> Storage
    Services --> BackendAPI["API Backend"]
    
    classDef ui fill:#bbdefb,stroke:#333,stroke-width:1px
    classDef core fill:#c8e6c9,stroke:#333,stroke-width:1px
    classDef storage fill:#ffe0b2,stroke:#333,stroke-width:1px
    classDef external fill:#e1bee7,stroke:#333,stroke-width:1px
    
    class Pages,Components ui
    class State,Services core
    class ClientStorage storage
    class BackendAPI external
```

---
layout: two-cols
---

# Backend

* Arquitectura multicapa con API REST en FastAPI
* Servicios para gestión de usuarios, aprendizaje y evaluación
* Integración de IA: LLM, conversión voz-texto, RAG y gestor de nivel
* Sistema adaptativo para personalizar el aprendizaje de idiomas

::right::

```mermaid { scale: 0.45}
flowchart TB
    subgraph API["Capa API (FastAPI)"]
        endpoints["Endpoints"] --- auth["Autenticación"] --- middleware["Middleware"]
    end
    
    subgraph CoreServices["Servicios Principales"]
        userContent["Servicio de Usuario"] --- languageLearning["Servicio de Aprendizaje"] --- evaluation["Servicio de Evaluación"] 
    end
    
    subgraph AIComponents["Componentes IA"]
        llm["LLM (Ollama)"] --- speechTools["TTS/STT"] --- rag["Sistema RAG"] --- levelManager["Gestor de Nivel (PPO)"]
    end
    
    DataStorage[("Almacenamiento de Datos")]
    
    API --> CoreServices
    CoreServices --> AIComponents
    AIComponents --> DataStorage
    
    classDef apiLayer fill:#e1f5fe,stroke:#0288d1,stroke-width:2px
    classDef coreLayer fill:#e8f5e9,stroke:#388e3c,stroke-width:2px
    classDef aiLayer fill:#fff8e1,stroke:#ffa000,stroke-width:2px
    classDef dataLayer fill:#e0e0e0,stroke:#616161,stroke-width:2px
    
    class API apiLayer
    class endpoints,auth,middleware apiLayer
    
    class CoreServices coreLayer
    class userContent,languageLearning,evaluation coreLayer
    
    class AIComponents aiLayer
    class llm,speechTools,rag,levelManager aiLayer
    
    class DataStorage dataLayer
    class sqlite,chromadb dataLayer
```

---
layout: two-cols
---

# Almacenamiento de Datos

* **SQLite**: Almacena datos estructurados de usuarios, idiomas, situaciones de aprendizaje e historial de progreso

* **ChromaDB**: Base de datos vectorial para ejemplos de idiomas y búsqueda semántica

* **Diseño dual**: Combina almacenamiento relacional y vectorial para optimizar tanto la gestión de datos como la recuperación contextual de ejemplos lingüísticos


::right::

```mermaid { scale: 0.65}
    flowchart TB
    subgraph SQL["Datos Estructurados"]
        direction TB
        users["Usuarios"] --- languages["Idiomas"] --- situations["Situaciones"] --- history["Historial de Aprendizaje"]
    end
    
    subgraph Vector["Datos Vectoriales"]
        direction TB
        examples["Ejemplos de Idiomas"] --- embeddings["Embeddings"] --- retrieval["Sistema de Recuperación"]
    end
    
    %% Estilo
    classDef sqlStyle fill:#d1e7ff,stroke:#2979ff,stroke-width:1px
    classDef vectorStyle fill:#ffd1dc,stroke:#e91e63,stroke-width:1px
    classDef serviceStyle fill:#e8f5e9,stroke:#388e3c,stroke-width:1px
    
    class SQL sqlStyle
    class Vector vectorStyle
    class UserContent,Learning,Evaluation,RAG serviceStyle
```

---
layout: two-cols
---

# Sistema Multi-Agente

### Agente Asistente

* Gestiona conversaciones de aprendizaje
* Adapta respuestas al nivel del usuario
* Integra RAG para contenido contextualizado

<br />

### Agente Evaluador

* Evalúa gramática, vocabulario y fluidez
* Mide cumplimiento de objetivos
* Alimenta el modelo PPO para ajustar dificultad

::right::

```mermaid { scale: 0.5}
flowchart TB
    subgraph AssistantAgent["Agente Asistente"]
        direction TB
        promptEng["Ingeniería de Prompts"] --> conversationFlow["Flujo de Conversación"]
        conversationFlow --> contextManager["Gestor de Contexto"]
    end
    
    subgraph EvaluationAgent["Agente Evaluador"]
        direction TB
        metrics["Métricas de Desempeño"] --> analysis["Análisis CEFR"]
    end
    
    AssistantAgent <--> EvaluationAgent
    
    User["Usuario"] <--> AssistantAgent
    EvaluationAgent --> PPO["Modelo PPO"]
    RAG["Sistema RAG"] --> AssistantAgent
    
    %% Estilo
    classDef agentStyle fill:#fff8e1,stroke:#ffa000,stroke-width:2px
    classDef subAgentStyle fill:#ffecb3,stroke:#ffa000,stroke-width:1px
    classDef externalStyle fill:#e8f5e9,stroke:#388e3c,stroke-width:1px
    classDef userStyle fill:#e1f5fe,stroke:#0288d1,stroke-width:1px
    
    class Agents agentStyle
    class AssistantAgent,EvaluationAgent subAgentStyle
    class RAG,PPO externalStyle
    class User userStyle
```

---
layout: section
---

# Tecnologías clave

---
layout: two-cols-header
---

# Modelos de lenguaje

::left::

<v-click>

## [Phi-4 ](https://github.com/marketplace/models/azureml/Phi-4)

<br />

### Características
- 14B parámetros
- Longitud de contexto: 16k tokens
- Entrenado con datos sintéticos y académicos

<br />

### Casos de Uso
- Investigación de IA
- Sistemas de propósito general
- Aplicaciones con restricciones de latencia

</v-click>

::right::

<v-click>

## [Nomic Embed Text](https://huggingface.co/nomic-ai/nomic-embed-text-v1)

<br />

### Características
- Modelo de embeddings de contexto largo
- Supera el rendimiento de OpenAI `text-embedding-ada-002`
- Convierte palabras en vectores que capturan significado

<br />

### Casos de Uso
- Generación de embeddings
- Búsqueda semántica
- Análisis de similitud textual


</v-click>

---
layout: two-cols-header
---

# Procesamiento de voz

Speech-to-Text / Text-to-Speech

::left::

<v-click>

## [Faster-Whisper](https://github.com/SYSTRAN/faster-whisper)

<br />

### Características

- Versión optimizada del modelo Whisper de OpenAI
- Mayor velocidad y eficiencia computacional
- Soporte para múltiples idiomas

<br />

### Casos de Uso

- Transcripción de audio
- Subtitulado automático
- Accesibilidad

</v-click>

::right::

<v-click>

## [Kokoro-TTS](https://huggingface.co/spaces/hexgrad/Kokoro-TTS)

<br />

### Características

- Modelo ligero de 82 millones de parámetros
- Multilenguaje (8 idiomas, 54 voces)
- Rendimiento comparable a modelos más grandes

<br />

### Casos de Uso

- Asistentes de voz
- Lectura de texto
- Accesibilidad

</v-click>

---
layout: two-cols
---

# Modelo PPO para Ajuste Dinámico de Niveles

Gestión Adaptativa de Niveles de Aprendizaje

<br />

<v-clicks>

* **Propósito**: Ajustar automáticamente la dificultad del aprendizaje basándose en el rendimiento del estudiante
* **Entorno**: 
  * Observaciones: 20 métricas (4 indicadores de rendimiento × 5 días) + nivel actual
  * Acciones: Disminuir (0), Mantener (1) o Aumentar (2) el nivel de dificultad

</v-clicks>

::right::

<v-click>

```mermaid { scale: 0.4}
flowchart TB
  subgraph "Entorno de Aprendizaje"

    subgraph "Sesión 4"
        D4[Gramática: 0.85]
        E4[Vocabulario: 0.78]
        F4[Fluidez: 0.92]
        G4[Objetivos: 0.80]
    end

    subgraph "Sesión 3"
        D3[Gramática: 0.85]
        E3[Vocabulario: 0.78]
        F3[Fluidez: 0.92]
        G3[Objetivos: 0.80]
    end

    subgraph "Sesión 2"
        D2[Gramática: 0.85]
        E2[Vocabulario: 0.78]
        F2[Fluidez: 0.92]
        G2[Objetivos: 0.80]
    end

    subgraph "Sesión 1"
        D1[Gramática: 0.85]
        E1[Vocabulario: 0.78]
        F1[Fluidez: 0.92]
        G1[Objetivos: 0.80]
    end

      H[Nivel Actual: 3]
  end
```

</v-click>

---
layout: two-cols-header
---

# Seguimiento del Rendimiento y Decisiones

::left::

<v-click>

### Indicadores Clave de Rendimiento

<br />

- **Gramática**: Precisión en reglas gramaticales
- **Vocabulario**: Riqueza léxica en base al nivel
- **Fluidez**: Naturalidad de la conversación
- **Objetivos de aprendizaje**: Cumplimiento de las metas de la situación

</v-click>

::right::

<v-click>

### Factores de Decisión

<br />

- Promedios de rendimiento reciente (últimos 2 días)
- Tendencias de rendimiento (comparación de los primeros 2 vs últimos 2 días)
- Desencadenantes basados en umbrales (ej., >85% = aumentar, <30% = disminuir)
- Volatilidad y consistencia del rendimiento

</v-click>



----

# Pruebas del Modelo y Resultados

Aprendizaje por Imitación con Escenarios

- **Metodología**: Combinación de aprendizaje por imitación y aprendizaje por refuerzo
- **Entrenamiento**: 
  - 500,000 pasos temporales con curriculum learning (complejidad progresiva)
  - El modelo aprende de patrones ejemplares predefinidos
  
- **Análisis de Resultados**:
  - Desglose de precisión por categoría de escenario
  - Matriz de confusión para acciones esperadas vs. predichas
  - Comparación entre decisiones humanas y del modelo



---

![alt text](/scenario_results.png)

---
layout: two-cols-header
---

# Evaluador de Lenguaje RAG

::left::

<v-click>

### Usos principales

<br />

- Almacena y recupera frases según los niveles MCER (A1-C2)
- Utiliza búsqueda semántica para encontrar ejemplos contextualmente relevantes
- Permite mejorar el rendimiento de los Agentes Asistente y Evaluador

</v-click>

::right::

<v-click>

### Características Principales

<br />

- **Búsqueda Contextual**: Encuentra frases basadas en el significado, no solo en palabras clave
- **Personalizable**: Filtra por nivel de competencia MCER y contexto.
- **Escalable**: Puede ampliarse con más ejemplos y categorías

</v-click>

---
layout: two-cols
---

# Evaluador de Lenguaje RAG

### Funcionamiento

<br />

1. **Generación de Embeddings**: Utiliza el modelo `nomic-embed-text` de Ollama para crear embeddings vectoriales
2. **Almacenamiento Vectorial**: Guarda ejemplos en la base de datos vectorial Chroma con metadatos
3. **Recuperación Semántica**: Recupera ejemplos basados en:
   - Similitud semántica con la consulta
   - Filtrado por nivel MCER (A1-C2)
   - Filtrado opcional por categoría

::right::

```mermaid {scale: 0.8}
flowchart TB
    U((Usuario)) --> Q[/Consulta/]
    BD[(Base de Conocimientos)] --> R
    Q --> R[Recuperador]
    R --> G[Agente Asistente/Evaluador]
    Q --> G
    G --> A[/Respuesta/]
    A --> U
```

---
layout: section
---

# Demostración


---
layout: iframe
url: https://emasuriano.github.io/language-learning-client/
---

---
layout: recording

direction: right

# the image source
image: /recording/situations.gif
---

# Selector de situaciones

- Contexto donde la conversación va a tomar lugar
- Lista de objetivos a cumplir
- Dificultad: Baja, Media o Alta.


---
layout: recording

direction: right

# the image source
image: /recording/user-profile.gif
---

# Perfil de estudiante

* Configuración del idioma
* Controles de voz
* Indicadores de nivel
* Opciones de configuración

---
layout: recording

direction: right

# the image source
image: /recording/conversation.gif
---

# Conversación

* Ejemplo de diálogo adaptado al nivel
* Uso de voz para práctica oral
* Soporte de Texto a Voz y Voz a Texto
* Traducción a idioma materno
* Asistente de ayuda contextual

---
layout: recording

direction: right

# the image source
image: /recording/progress-record.gif
---

# Análisis de conversación 

* Reporte de evaluación sobre la conversación
* Obtención de métricas para el modelo RL
* Reporte personalizado de cada métrica

---
layout: recording

direction: right

# the image source
image: /recording/learning-progress.gif
---

# Progreso del aprendizaje

* Visualización de métricas por sesiones
* Visualización de tendencias cada 5 sesiones  
* Progresión del nivel del estudiante por sesión
* Posibilidad de subir/bajar nivel (opcional por el estudiante) 

---
layout: section
---

# Evaluación y resultados

---
layout: two-cols
---

# Evaluación con usuarios

Pruebas con 10 participantes durante 2 semanas

* **Facilidad de uso**: 4.0/5
* **Satisfacción con funcionalidades**: 3.9/5
* **Percepción de utilidad**: 3.9/5
* **Preferencia vs métodos tradicionales**: 78%

::right::

![Satisfacción de usuarios](/user-satisfaction.png)

----

# Contribuciones principales

* **Framework de evaluación multidimensional**
  * Métricas para gramática, vocabulario, fluidez y objetivos

* **Modelo PPO optimizado para educación lingüística**
  * 95% de precisión en decisiones de adaptación

* **Integración efectiva LLM+RAG en contexto educativo**
  * Respuestas contextualmente relevantes y pedagógicas

* **Pipeline optimizado de procesamiento de voz**
  * Muy baja latencia al convertir voz a texto y texto a voz

----

# Limitaciones actuales

* **Técnicas**:
  * El poder de computación esta atada al hardware disponible
  * No todos los idiomas cuentan con TTS

* **Pedagógicas**:
  * Cobertura limitada de dominios específicos
  * Adaptación insuficiente a estilos de aprendizaje

* **Validación**:
  * Muestra de usuario reducida (n=10)
  * Período de evaluación corto (2 semanas)

----

# Trabajo futuro

* **Evaluación exhaustiva**
  * Muestra ampliada (n>100)
  * Estudio longitudinal (3-6 meses)

* **Mejoras técnicas**
  * Contar con una versión en la nube del sistema
  * Ampliación de lenguajes disponibles

* **Expansión de funcionalidades**
  * Módulos para dominios especializados
  * Generación de situaciones dinámicas.

---
layout: section
---

# Conclusiones

----

# Conclusiones

<v-clicks>

* La combinación RL + Transformers + RAG permite **superar** limitaciones de sistemas tradicionales

* Los resultados preliminares muestran **gran** potencial para transformar el aprendizaje de idiomas

* La personalización dinámica y las interacciones naturales son clave para **mejorar** la experiencia educativa

* Demuestra un paso hacia educación adaptativa, contextual y **centrada en el estudiante**

</v-clicks>

---
layout: fact
class: "![&>h1]:text-6xl"
---

# "El mejor método no es gramática, ni práctica, ni inmersión, sino input *comprensible*"

## Stephen Krashen

---

# Repositorios públicos

* **Frontend**:
  * [github.com/EmaSuriano/language-learning-client](https://github.com/EmaSuriano/language-learning-client)
  * Next.js, TypeScript, Tailwind CSS

* **Backend**:
  * [github.com/EmaSuriano/language-learning-server](https://github.com/EmaSuriano/language-learning-server)
  * FastAPI, Python, LangChain, Stable-Baselines3

* **Licencia MIT**: Código abierto para la comunidad

---
layout: fact
---

# ¡Gracias por su atención!


