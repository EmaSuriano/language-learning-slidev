---
theme: seriph
background: https://cover.sli.dev
title: Aplicación de Reinforcement Learning y Transformers para el Aprendizaje de Idiomas
info: |
  Presentación del Trabajo Fin de Máster
  Máster Propio en Inteligencia Artificial
  Segunda Edición, Curso Académico 2024
class: text-center
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Aplicación de Reinforcement Learning y Transformers para el Aprendizaje de Idiomas

Trabajo Fin de Máster

<div class="pt-12">
  <span class="px-2 py-1">Julio Emanuel Suriano Bryk</span>
</div>

<div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl slidev-icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
</div>

<!--
Este proyecto integra técnicas avanzadas de IA para crear un sistema de aprendizaje de idiomas adaptativo y personalizado.
-->

---

## transition: fade-out

# Contenido

<Toc minDepth="1" maxDepth="1" />

---

layout: two-cols
layoutClass: gap-4

---

# Motivación

<v-clicks>

- Desafíos en la personalización efectiva del aprendizaje de idiomas
- Limitaciones de los métodos tradicionales:

  - Rigidez estructural
  - Falta de personalización
  - Retroalimentación limitada
  - Práctica conversacional artificial

- Oportunidades de mejora mediante IA:
  - Adaptabilidad dinámica
  - Personalización profunda
  - Interacción natural
  - Feedback contextual

</v-clicks>

::right::

<div v-click class="mt-12">
  <img src="https://i.imgur.com/rzDqByr.png" class="rounded-lg shadow-xl" alt="Imagen conceptual del sistema de aprendizaje adaptativo">
  <div class="text-center text-xs text-gray-500 mt-2">Representación conceptual de aprendizaje adaptativo</div>
</div>

<!--
La adquisición de idiomas varía significativamente entre individuos, influenciada por múltiples factores personales. Los métodos tradicionales siguen un modelo secuencial predefinido que no considera estas diferencias.

El aprendizaje óptimo ocurre cuando el input es ligeramente superior al nivel actual (principio i+1 de Krashen), un equilibrio difícil de lograr con sistemas estáticos.
-->

---

# Estado del Arte

<div class="grid grid-cols-3 gap-4">
<div v-click>
  <h3 class="text-primary">Sistemas Adaptativos</h3>
  <ul class="text-sm">
    <li>Busuu Conversations (2024)</li>
    <li>Duolingo Max (2024)</li>
    <li>Babbel Everyday (2023)</li>
    <li>Lingvist (2023)</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-primary">LLMs en Educación</h3>
  <ul class="text-sm">
    <li>ChatGPT (2022)</li>
    <li>Claude (2023)</li>
    <li>Grammarly with GrammarlyGO</li>
    <li>DeepL Write (2023)</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-primary">Procesamiento de Voz</h3>
  <ul class="text-sm">
    <li>Whisper OpenAI (2022)</li>
    <li>Google Speech-to-Text (2023)</li>
    <li>Azure AI Speech (2023)</li>
    <li>Kokoro-82M (2025)</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-primary">Agentic AI</h3>
  <ul class="text-sm">
    <li>LangChain (2022)</li>
    <li>CrewAI (2023)</li>
    <li>Autogen de Microsoft (2023)</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-primary">Frameworks RL</h3>
  <ul class="text-sm">
    <li>TensorFlow Agents (2019)</li>
    <li>Stable Baselines3 (2020)</li>
    <li>TorchRL (2022)</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-primary">Compañeros de IA</h3>
  <ul class="text-sm">
    <li>Khanmigo (2024)</li>
    <li>Third Space Learning (2024)</li>
    <li>Riiid SANTA (2023)</li>
  </ul>
</div>
</div>

<!--
Estos sistemas representan la vanguardia actual en sus respectivos campos, pero aún existen desafíos significativos que nuestro trabajo busca abordar, especialmente en la integración efectiva de estas tecnologías.
-->

---

layout: two-cols
layoutClass: gap-8

---

# Objetivos

<v-clicks>

## General

Desarrollar un sistema de aprendizaje de idiomas integrando RL, Transformers y enfoque multi-agente para proporcionar una experiencia personalizada, adaptativa y efectiva.

## Específicos

- **Optimización del Aprendizaje**: Implementar PPO para rutas personalizadas y mecanismos de adaptación dinámica.

- **Mejora de la Interacción**: Integrar LLMs para diálogos naturales y análisis de errores en tiempo real.

- **Perfeccionamiento Lingüístico**: Crear sistemas de evaluación de pronunciación y práctica conversacional contextualizada.

- **Gestión del Conocimiento**: Integrar RAG para acceso contextualizado a recursos educativos.

</v-clicks>

::right::

<div v-click class="mt-12">
  <img src="https://i.imgur.com/tVNFr6P.png" class="rounded-lg shadow-xl" alt="Diagrama conceptual de objetivos">
  <div class="text-center text-xs text-gray-500 mt-2">Integración de componentes para lograr objetivos</div>
</div>

---

## transition: slide-up

# Marco Teórico

<div class="grid grid-cols-2 gap-x-4 gap-y-4">
<div v-click>
  <h3 class="text-primary">Aprendizaje de Idiomas</h3>
  <ul class="text-sm">
    <li>Hipótesis del input comprensible (Krashen)</li>
    <li>Factores internos y externos (Ellis)</li>
    <li>Evolución de metodologías de enseñanza</li>
    <li>Desafíos en personalización</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-primary">IA en Educación</h3>
  <ul class="text-sm">
    <li>Evolución de sistemas adaptativos</li>
    <li>Arquitecturas de sistemas educativos</li>
    <li>Personalización y adaptación dinámica</li>
    <li>Evaluación automática y recomendación</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-primary">LLMs y RAG</h3>
  <ul class="text-sm">
    <li>Arquitectura Transformer</li>
    <li>Características de los LLMs modernos</li>
    <li>Sistemas RAG: integración de recuperación y generación</li>
    <li>Ventajas en aplicaciones educativas</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-primary">Reinforcement Learning</h3>
  <ul class="text-sm">
    <li>Fundamentos teóricos (MDP)</li>
    <li>Algoritmo PPO: optimización de políticas</li>
    <li>Sistema de recompensas en educación</li>
    <li>Evaluación de políticas de aprendizaje</li>
  </ul>
</div>
</div>

<div v-click>
  <h3 class="text-primary mt-4">Procesamiento de Voz</h3>
  <div class="grid grid-cols-2 gap-4">
    <div>
      <h4 class="text-sm font-bold">STT (Voz a Texto)</h4>
      <ul class="text-xs">
        <li>Procesamiento de señal acústica</li>
        <li>Modelado acústico y del lenguaje</li>
        <li>Algoritmos de decodificación</li>
      </ul>
    </div>
    <div>
      <h4 class="text-sm font-bold">TTS (Texto a Voz)</h4>
      <ul class="text-xs">
        <li>Procesamiento lingüístico</li>
        <li>Modelado prosódico</li>
        <li>Síntesis de forma de onda</li>
      </ul>
    </div>
  </div>
</div>

<!--
Nuestro trabajo se fundamenta en una sólida base teórica que integra principios de lingüística, educación e inteligencia artificial.

El principio i+1 de Krashen es particularmente relevante, sugiriendo que el aprendizaje óptimo ocurre cuando se expone al estudiante a contenido ligeramente por encima de su nivel actual.
-->

---

layout: two-cols
layoutClass: gap-4

---

# Material

<v-clicks>

## Recursos Computacionales

- GPU: NVIDIA GeForce RTX 4070 (12GB VRAM)
- Memoria: 32GB RAM DDR4
- Almacenamiento: 1TB SSD NVMe

## Componentes del Sistema

- **Backend**: LangChain, FastAPI
- **Procesamiento de Voz**:
  - Faster-Whisper (STT)
  - Kokoro-TTS (TTS)
- **Modelos de Lenguaje**:
  - Phi-4 (14B parámetros)
  - Nomic Embed (embeddings)

</v-clicks>

::right::

<v-clicks>

## Bases de Datos

- SQL: Perfiles, progreso, métricas
- ChromaDB: Embeddings, búsqueda semántica
- Redis: Caché, sesiones

## Frontend

- Next.js: Framework React
- NextAuth.js: Autenticación
- Next-i18next: Internacionalización

## Recursos Lingüísticos

- Soporte para 8 idiomas (TTS)
- 20 idiomas en reconocimiento (STT)
- Material didáctico CEFR (A1-C2)
- Escenarios de práctica predefinidos

</v-clicks>

<!--
La implementación del sistema requiere una infraestructura robusta para manejar los modelos de IA y proporcionar una experiencia fluida al usuario.

Destacamos el uso de Phi-4, un modelo de 14B parámetros, que ofrece un buen equilibrio entre capacidad y eficiencia para nuestro sistema conversacional.
-->

---

## layout: full

# Métodos: Arquitectura del Sistema

<div class="grid grid-cols-2 gap-4 mt-4">
<div v-click>
  <img src="https://i.imgur.com/YkVdoRW.png" class="h-60 mx-auto" alt="Arquitectura del Sistema">
  <div class="text-center text-xs text-gray-500">Arquitectura general del sistema</div>
</div>

<div v-click>
  <img src="https://i.imgur.com/MJcR3mf.png" class="h-60 mx-auto" alt="Sistema Multi-agente">
  <div class="text-center text-xs text-gray-500">Sistema multi-agente con LangChain</div>
</div>
</div>

<div v-click class="mt-4">
  <h3 class="text-primary">Componentes Principales</h3>
  <div class="grid grid-cols-3 gap-4">
    <div>
      <h4 class="text-sm font-bold">Frontend</h4>
      <ul class="text-xs">
        <li>Componentes de chat (Assistant UI)</li>
        <li>Gestión de hilos conversacionales</li>
        <li>Estado con Zustand</li>
        <li>Internacionalización</li>
      </ul>
    </div>
    <div>
      <h4 class="text-sm font-bold">Backend</h4>
      <ul class="text-xs">
        <li>API REST con FastAPI</li>
        <li>Sistema Multi-agente</li>
        <li>Gestión de modelos (LLM, PPO, RAG)</li>
        <li>Servicios core (usuario, contenido, progreso)</li>
      </ul>
    </div>
    <div>
      <h4 class="text-sm font-bold">Procesamiento de Voz</h4>
      <ul class="text-xs">
        <li>Pipeline STT con Faster-Whisper</li>
        <li>Pipeline TTS con Kokoro</li>
        <li>Optimizaciones para respuesta rápida</li>
        <li>Gestión de caché para frases frecuentes</li>
      </ul>
    </div>
  </div>
</div>

<!--
La arquitectura modular del sistema permite la evolución independiente de cada componente, facilitando mejoras incrementales.

El sistema multi-agente coordina dos agentes especializados: Assistant Agent para conversaciones y Evaluation Agent para seguimiento del progreso.
-->

---

layout: two-cols
layoutClass: gap-4

---

# Métodos: Modelo PPO para Adaptación de Niveles

<v-clicks>

## Diseño del Entorno RL

- Entorno personalizado LevelAdjustmentEnv
- Observación: 21 dimensiones (20 métricas + nivel)
- Acciones: Disminuir, Mantener, Aumentar nivel

## Generación de Escenarios

- Fase inicial: Patrones claros (0-20%)
- Fase intermedia: Patrones complejos (20-50%)
- Fase avanzada: Casos límite (50-100%)

## Curvas de Aprendizaje

- Modelos: Lineal, Exponencial, Logarítmica, etc.
- Efectos: Fatiga, calentamiento, ruido aleatorio

</v-clicks>

::right::

<v-clicks>

## Sistema de Recompensas

- Base: +1.0 (correcta), -1.0 (opuesta)
- Modificador según rendimiento reciente

## Implementación PPO (Stable Baselines3)

- Tasa de aprendizaje: 0.0003
- Steps por actualización: 2048
- Épocas por actualización: 10
- Factor de descuento (γ): 0.99

## Evaluación

- Precision >95% en toma de decisiones
- Evaluación con 10 escenarios representativos
- Análisis por categorías: promoción, descenso, mantenimiento

</v-clicks>

<div v-click class="mt-4">
  <img src="https://i.imgur.com/YmQXNjn.png" class="mx-auto" alt="Evaluación del modelo PPO">
  <div class="text-center text-xs text-gray-500">Resultados de evaluación del modelo PPO</div>
</div>

<!--
El modelo PPO es fundamental para la personalización dinámica del aprendizaje, ajustando el nivel según el rendimiento del estudiante.

La evaluación exhaustiva con escenarios representativos confirmó su capacidad para tomar decisiones adecuadas en diversas situaciones.
-->

---

## transition: slide-left

# Resultados: Rendimiento Técnico

<div class="grid grid-cols-2 gap-8">
<div v-click>
  <h3 class="text-primary">Frontend</h3>
  
  <h4 class="text-sm font-bold mt-2">Text-to-Speech (TTS)</h4>
  <ul class="text-xs">
    <li>Latencia: 50ms por frase (mediana)</li>
    <li>Memoria: 120MB promedio</li>
    <li>GPU: 20-25% durante generación</li>
    <li>Inicialización: 1.2 segundos</li>
  </ul>
  
  <h4 class="text-sm font-bold mt-2">Speech-to-Text (STT)</h4>
  <ul class="text-xs">
    <li>Latencia: 100ms (frases cortas)</li>
    <li>Memoria: 150MB promedio</li>
    <li>Precisión: 85% en ambiente controlado</li>
    <li>Degradación con ruido: 10-15%</li>
  </ul>
</div>

<div v-click>
  <h3 class="text-primary">Backend</h3>
  
  <h4 class="text-sm font-bold mt-2">Sistema RAG</h4>
  <ul class="text-xs">
    <li>Latencia búsqueda: 75ms promedio</li>
    <li>Precisión: 82% en recuperación</li>
    <li>Relevancia contextual: 80%</li>
    <li>Tiempo indexación: 3.5 minutos</li>
  </ul>
  
  <h4 class="text-sm font-bold mt-2">Sistema PPO</h4>
  <ul class="text-xs">
    <li>Convergencia: 15 episodios promedio</li>
    <li>Estabilidad: 90% en pruebas sintéticas</li>
    <li>Precisión recomendaciones: 88%</li>
    <li>Tiempo inferencia: 35ms</li>
  </ul>
</div>
</div>

<div v-click>
  <blockquote class="mt-8 p-4 bg-gray-100 rounded-lg text-sm">
    Rendimiento adecuado para interacción fluida, con tiempos de respuesta por debajo del umbral perceptible (200ms) en la mayoría de los casos. La precisión, aunque mejorable, resulta suficiente para una primera versión funcional.
  </blockquote>
</div>

<!--
Los resultados técnicos demuestran que el sistema logra un equilibrio entre calidad y eficiencia, permitiendo una experiencia fluida incluso en equipos con recursos moderados.

La latencia reducida es crucial para mantener conversaciones naturales, y nuestro sistema se mantiene consistentemente por debajo del umbral perceptible de 200ms.
-->

---

# Resultados: Evaluación de Usuario

<div class="grid grid-cols-2 gap-6 mt-4">
<div v-click>
  <h3 class="text-primary">Facilidad de Uso</h3>
  <div class="ml-4">
    <div class="flex items-center">
      <div class="w-36 text-xs">Navegación interfaz</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-blue-600 rounded-full" style="width: 84%"></div>
      </div>
      <div class="ml-2 text-xs">4.2/5</div>
    </div>
    <div class="flex items-center mt-1">
      <div class="w-36 text-xs">Interacción agente</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-blue-600 rounded-full" style="width: 80%"></div>
      </div>
      <div class="ml-2 text-xs">4.0/5</div>
    </div>
    <div class="flex items-center mt-1">
      <div class="w-36 text-xs">Config. preferencias</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-blue-600 rounded-full" style="width: 74%"></div>
      </div>
      <div class="ml-2 text-xs">3.7/5</div>
    </div>
    <div class="flex items-center mt-1">
      <div class="w-36 text-xs">Funciones de voz</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-blue-600 rounded-full" style="width: 78%"></div>
      </div>
      <div class="ml-2 text-xs">3.9/5</div>
    </div>
    <div class="flex items-center mt-1">
      <div class="w-36 text-xs">Selección situaciones</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-blue-600 rounded-full" style="width: 86%"></div>
      </div>
      <div class="ml-2 text-xs">4.3/5</div>
    </div>
  </div>
</div>

<div v-click>
  <h3 class="text-primary">Funcionalidades</h3>
  <div class="ml-4">
    <div class="flex items-center">
      <div class="w-36 text-xs">Diálogo adaptativo</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-green-600 rounded-full" style="width: 82%"></div>
      </div>
      <div class="ml-2 text-xs">4.1/5</div>
    </div>
    <div class="flex items-center mt-1">
      <div class="w-36 text-xs">Reconocimiento voz</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-green-600 rounded-full" style="width: 72%"></div>
      </div>
      <div class="ml-2 text-xs">3.6/5</div>
    </div>
    <div class="flex items-center mt-1">
      <div class="w-36 text-xs">Síntesis de voz</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-green-600 rounded-full" style="width: 80%"></div>
      </div>
      <div class="ml-2 text-xs">4.0/5</div>
    </div>
    <div class="flex items-center mt-1">
      <div class="w-36 text-xs">Análisis gramatical</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-green-600 rounded-full" style="width: 78%"></div>
      </div>
      <div class="ml-2 text-xs">3.9/5</div>
    </div>
    <div class="flex items-center mt-1">
      <div class="w-36 text-xs">Panel de progreso</div>
      <div class="w-36 h-4 bg-gray-200 rounded-full">
        <div class="h-4 bg-green-600 rounded-full" style="width: 84%"></div>
      </div>
      <div class="ml-2 text-xs">4.2/5</div>
    </div>
  </div>
</div>
</div>

<div v-click class="mt-6">
  <h3 class="text-primary">Comparación con Métodos Tradicionales</h3>
  <div class="grid grid-cols-5 gap-4 ml-4 mt-2">
    <div>
      <div class="text-center text-xs mb-1">Conveniencia</div>
      <div class="w-full bg-gray-200 rounded-full h-12 flex items-center justify-center">
        <div class="bg-purple-600 h-12 rounded-full flex items-center justify-center" style="width: 90%">
          <span class="text-white text-xs">90%</span>
        </div>
      </div>
    </div>
    <div>
      <div class="text-center text-xs mb-1">Personalización</div>
      <div class="w-full bg-gray-200 rounded-full h-12 flex items-center justify-center">
        <div class="bg-purple-600 h-12 rounded-full flex items-center justify-center" style="width: 80%">
          <span class="text-white text-xs">80%</span>
        </div>
      </div>
    </div>
    <div>
      <div class="text-center text-xs mb-1">Feedback</div>
      <div class="w-full bg-gray-200 rounded-full h-12 flex items-center justify-center">
        <div class="bg-purple-600 h-12 rounded-full flex items-center justify-center" style="width: 85%">
          <span class="text-white text-xs">85%</span>
        </div>
      </div>
    </div>
    <div>
      <div class="text-center text-xs mb-1">Hab. Orales</div>
      <div class="w-full bg-gray-200 rounded-full h-12 flex items-center justify-center">
        <div class="bg-purple-600 h-12 rounded-full flex items-center justify-center" style="width: 65%">
          <span class="text-white text-xs">65%</span>
        </div>
      </div>
    </div>
    <div>
      <div class="text-center text-xs mb-1">Vocabulario</div>
      <div class="w-full bg-gray-200 rounded-full h-12 flex items-center justify-center">
        <div class="bg-purple-600 h-12 rounded-full flex items-center justify-center" style="width: 70%">
          <span class="text-white text-xs">70%</span>
        </div>
      </div>
    </div>
  </div>
</div>

<!--
Los resultados de las pruebas de usuario (n=10) son prometedores, con una recepción positiva en la mayoría de las áreas evaluadas.

El reconocimiento de voz (STT) recibió la puntuación más baja (3.6/5), principalmente debido a dificultades con acentos no nativos, lo que representa un área clara de mejora.
-->

---

layout: image-right
image: https://i.imgur.com/oXeXvd3.png

---

# Interfaz del Sistema

<v-clicks>

## Características Principales

- **Interfaz minimalista y accesible**

  - Panel de chat interactivo
  - Controles de voz integrados
  - Indicadores de nivel CEFR

- **Sistema de diálogo contextual**

  - Respuestas adaptadas al nivel
  - Corrección en tiempo real
  - Retroalimentación específica

- **Selector de situaciones**

  - Contextos predefinidos
  - Sistema de objetivos
  - Personalización automática

- **Panel de análisis**
  - Visualización del progreso
  - Métricas de aprendizaje
  - Recomendaciones personalizadas

</v-clicks>

<!--
La interfaz del sistema se diseñó priorizando la simplicidad y facilidad de uso, sin sacrificar la potencia de las funcionalidades subyacentes.

Los elementos visuales guían intuitivamente al usuario a través del proceso de aprendizaje, manteniendo visible su progreso y proporcionando retroalimentación constante.
-->

---

layout: two-cols
layoutClass: gap-4

---

# Visualización de Progreso

<v-click>
  <img src="https://i.imgur.com/VGfIFwj.png" class="rounded shadow-xl h-80" alt="Visualización del progreso de aprendizaje">
</v-click>

::right::

<v-clicks>

## Características del Panel

- **Análisis Temporal Flexible**

  - Vista detallada de sesiones individuales
  - Perspectiva de tendencias agrupadas
  - Controles interactivos para exploración

- **Evaluación Integral**

  - Monitorización de 4 dimensiones clave:
    - Gramática
    - Vocabulario
    - Fluidez
    - Cumplimiento de objetivos

- **Análisis de Progresión de Nivel**

  - Resumen visual de la trayectoria
  - Correlación entre estrategias y resultados

- **Diseño Adaptativo**
  - Implementado con Radix UI
  - Experiencia optimizada multipantalla
  - Accesibilidad priorizada

</v-clicks>

<!--
El panel de visualización del progreso es una herramienta fundamental para la reflexión metacognitiva del estudiante.

Permite identificar patrones en el aprendizaje y tomar decisiones informadas sobre futuras prácticas lingüísticas, potenciando la autonomía del aprendizaje.
-->

---

layout: two-cols
layoutClass: gap-8

---

# Limitaciones y Trabajo Futuro

<v-clicks>

## Limitaciones Actuales

- **Técnicas**

  - Precisión STT insuficiente para acentos no nativos
  - Tiempo de carga inicial relativamente alto
  - Consumo de recursos significativo

- **Pedagógicas**
  - Cobertura limitada de dominios específicos
  - Sistema de evaluación no validado formalmente
  - Adaptación insuficiente a estilos de aprendizaje
- **Validación**
  - Muestra reducida (n=10)
  - Período de evaluación corto (2 semanas)
  - Ausencia de grupo de control

</v-clicks>

::right::

<v-clicks>

## Trabajo Futuro

- **Evaluación Exhaustiva**

  - Muestra ampliada (n>100)
  - Evaluación longitudinal (3-6 meses)
  - Estudio comparativo con grupo control

- **Mejoras Técnicas**

  - Fine-tuning del modelo PPO
  - Adaptación STT para acentos no nativos
  - Optimización base de conocimientos RAG

- **Expansión de Funcionalidades**
  - Módulos para dominios especializados
  - Componente social para práctica colaborativa
  - Integración con contenido auténtico
  - Sistema de gamificación adaptativa

</v-clicks>

---

layout: center
class: text-center

---

# Conclusiones

<div class="grid grid-cols-3 gap-4 mt-8">
<div v-click>
  <div class="flex justify-center">
    <div class="rounded-full bg-blue-100 p-4">
      <carbon:chart-relationship class="text-blue-600 text-3xl" />
    </div>
  </div>
  <h3 class="mt-4 text-sm font-bold">Integración Efectiva</h3>
  <p class="text-xs mt-2">
    Demostración exitosa de la sinergia entre RL, Transformers y RAG para crear un sistema de aprendizaje adaptativo.
  </p>
</div>

<div v-click>
  <div class="flex justify-center">
    <div class="rounded-full bg-green-100 p-4">
      <carbon:user-profile class="text-green-600 text-3xl" />
    </div>
  </div>
  <h3 class="mt-4 text-sm font-bold">Personalización Dinámica</h3>
  <p class="text-xs mt-2">
    El modelo PPO logra una adaptación efectiva del nivel de aprendizaje con una precisión superior al 95%.
  </p>
</div>

<div v-click>
  <div class="flex justify-center">
    <div class="rounded-full bg-purple-100 p-4">
      <carbon:idea class="text-purple-600 text-3xl" />
    </div>
  </div>
  <h3 class="mt-4 text-sm font-bold">Potencial Transformador</h3>
  <p class="text-xs mt-2">
    El sistema demuestra el potencial de la IA para democratizar el acceso a experiencias de aprendizaje personalizadas.
  </p>
</div>
</div>

<div v-click class="mt-10 text-left px-10">
  <blockquote class="text-sm">
    "La verdadera medida del éxito de este proyecto será su capacidad para facilitar el aprendizaje de idiomas de manera más eficiente, inclusiva y motivadora, contribuyendo así a derribar las barreras lingüísticas que separan a las personas y comunidades en un mundo cada vez más interconectado."
  </blockquote>
</div>

---

## layout: end

# ¡Gracias por su atención!

Julio Emanuel Suriano Bryk
