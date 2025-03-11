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
6. Contribuciones y trabajo futuro
7. Conclusiones


---
layout: section
---

# Introducción y motivación


---

# ¿Por qué aprendizaje de idiomas?

* El aprendizaje de idiomas es un desafío global
* Más de 1.500 millones de personas estudian un segundo idioma
* La personalización es clave para el éxito
* La tecnología puede transformar esta experiencia

[*Imagen conceptual sobre aprendizaje de idiomas global*]

---

# Limitaciones actuales

* **Rigidez estructural**: Secuencias predefinidas que no se adaptan al progreso real

* **Falta de personalización**: No consideran estilos de aprendizaje e intereses individuales

* **Retroalimentación limitada**: Feedback básico sin considerar el contexto completo

* **Práctica artificial**: Interacciones mecánicas que no reflejan conversaciones reales

---
layout: fact
class: "![&>h1]:text-6xl"
---

# "La persona promedio necesita 10,000 horas para dominar un idioma usando métodos tradicionales"

## Malcolm Gladwell

---

# La oportunidad

[*Diagrama simple mostrando la evolución de tecnologías*]

Avances recientes en IA abren nuevas posibilidades:
  * **LLMs** → Interacciones naturales
  * **Reinforcement Learning** → Adaptación dinámica
  * **Procesamiento de voz** → Práctica oral realista
  * **RAG** → Conocimiento contextualizado

---

# Objetivo general

Desarrollar un sistema de aprendizaje de idiomas que:

* Se adapte dinámicamente al nivel del estudiante
* Ofrezca interacciones conversacionales naturales
* Proporcione retroalimentación personalizada
* Integre práctica oral y escrita

[*Imagen conceptual representando aprendizaje adaptativo*]


----

# Objetivos específicos

1. **Optimización del aprendizaje**: Rutas personalizadas mediante Reinforcement Learning

2. **Mejora de la interacción**: Diálogos naturales con LLMs y RAG

3. **Habilidades completas**: Integración de tecnologías TTS y STT para práctica oral

4. **Gestión inteligente del conocimiento**: Acceso contextualizado a recursos educativos

---
layout: section
---

# Arquitectura del sistema

---

# Arquitectura general

[*Diagrama simplificado de la arquitectura*]

* **Frontend**: Experiencia de usuario
* **Backend**: Lógica adaptativa
* **Agentes especializados**: Coordinación inteligente
* **Bases de datos**: Almacenamiento estructurado y vectorial

----

# Frontend

[*Captura de pantalla de la interfaz principal*]

* Desarrollado con Next.js
* Interface conversacional intuitiva
* Visualización del progreso
* Selector de situaciones prácticas
* Integración fluida con componentes de voz

----

# Backend

* Sistema multi-agente basado en LangChain
* API REST con FastAPI
* Procesamiento de voz optimizado
* Sistema vectorial para búsqueda semántica
* Modelo PPO para adaptación de niveles

[*Diagrama conceptual del backend*]

----

# Sistema Multi-Agente

[*Diagrama simplificado del sistema multi-agente*]

### Assistant Agent
* Gestiona conversaciones
* Integra RAG para respuestas contextualizadas

### Evaluation Agent
* Analiza el progreso del estudiante
* Alimenta el modelo PPO

----

# Flujo de interacción

[*Diagrama de flujo de usuario*]

1. Usuario selecciona situación práctica
2. Sistema genera contexto adaptado al nivel
3. Interacción conversacional con voz/texto
4. Análisis en tiempo real y retroalimentación
5. Actualización del modelo de estudiante
6. Ajuste dinámico de dificultad

---
layout: section
---

# Tecnologías clave

----

# Tecnologías clave

### Modelos de lenguaje
* **Phi-4** (14B parámetros)
* **Nomic Embed** para embeddings semánticos

### Procesamiento de voz
* **Faster-Whisper** para reconocimiento
* **Kokoro-TTS** para síntesis de voz

### Bases de datos
* **ChromaDB** para búsqueda vectorial
* **Redis** para caché y sesiones

----

# Modelo PPO - Concepto

[*Diagrama conceptual de PPO aplicado a educación*]

* Aprendizaje por refuerzo para optimizar la experiencia educativa
* Observación del desempeño del estudiante
* Decisiones adaptativas sobre nivel y contenido
* Balance entre exploración y explotación

----

# Modelo PPO - Implementación

* **Estado**: 21 dimensiones (métricas de rendimiento + nivel)
* **Acciones**: Disminuir, mantener o aumentar nivel
* **Recompensa**: Basada en decisiones correctas y rendimiento
* **Entrenamiento**: 500,000 pasos con evaluación periódica

[*Gráfico simple de aprendizaje del modelo*]

----

# Sistema RAG

[*Diagrama de flujo del sistema RAG*]

1. **Vectorización** de consulta y documentos
2. **Recuperación** de contenido relevante
3. **Generación** de respuestas contextualizadas
4. **Integración** con el nivel del estudiante

---
layout: section
---

# Demostración

----

# Demo - Interfaz principal

[*Video/GIF o captura de la interfaz principal*]

* Panel de chat interactivo
* Controles de voz
* Indicadores de nivel
* Opciones de configuración

*[Punto para demostración en vivo]*

----

# Demo - Conversación

[*Video/GIF o captura de una conversación*]

* Ejemplo de diálogo adaptado al nivel
* Corrección contextual de errores
* Uso de voz para práctica oral

*[Continuación de demostración en vivo]*

----

# Demo - Análisis de progreso

[*Video/GIF o captura del panel de análisis*]

* Visualización de métricas de aprendizaje
* Progreso en diferentes dimensiones lingüísticas
* Recomendaciones personalizadas

*[Finalización de demostración en vivo]*

---
layout: section
---

# Evaluación y resultados

----

# Evaluación técnica - Frontend

* **Síntesis de voz (TTS)**:
  * Latencia: 50ms por frase
  * Memoria: 120MB promedio
  * Inicialización: 1.2 segundos

* **Reconocimiento de voz (STT)**:
  * Latencia: 100ms para frases cortas
  * Precisión: 85% en ambiente controlado
  * Degradación en ruido: 10-15%

[*Gráfico simple de métricas*]

----

# Evaluación técnica - Backend

* **Sistema RAG**:
  * Latencia de búsqueda: 75ms
  * Precisión recuperación: 82%
  * Relevancia contextual: 80%

* **Sistema PPO**:
  * Tiempo de convergencia: 15 episodios
  * Precisión decisiones: 95%
  * Tiempo de inferencia: 35ms

[*Gráfico simple de rendimiento*]

----

# Evaluación con usuarios

[*Gráfica de satisfacción de usuarios*]

* Pruebas con 10 participantes durante 2 semanas
* **Facilidad de uso**: 4.0/5
* **Satisfacción con funcionalidades**: 3.9/5
* **Percepción de utilidad**: 3.9/5
* **Preferencia vs métodos tradicionales**: 78%

----

# Fortalezas destacadas

* **Diálogos adaptativos**: 4.1/5
* **Análisis de progreso**: 4.2/5
* **Relevancia de escenarios**: 4.2/5
* **Adaptación al nivel**: 4.0/5

[*Gráfico de barras con puntuaciones*]

---
layout: section
---

# Contribuciones y trabajo futuro

----

# Contribuciones principales

* **Modelo PPO optimizado para educación lingüística**
  * 95% de precisión en decisiones de adaptación

* **Integración efectiva LLM+RAG en contexto educativo**
  * Respuestas contextualmente relevantes y pedagógicas

* **Pipeline optimizado de procesamiento de voz**
  * Latencias por debajo del umbral perceptible (200ms)

----

# Aportaciones metodológicas

* **Framework de evaluación multidimensional**
  * Métricas para gramática, vocabulario, fluidez y objetivos

* **Metodología de generación de escenarios**
  * Simulación de patrones reales de aprendizaje

* **Diseño centrado en el estudiante**
  * Adaptación a necesidades pedagógicas reales

----

# Limitaciones actuales

* **Técnicas**:
  * STT insuficiente para acentos no nativos fuertes
  * Tiempo de carga inicial (5-8 segundos)

* **Pedagógicas**:
  * Cobertura limitada de dominios específicos
  * Adaptación insuficiente a estilos de aprendizaje

* **Validación**:
  * Muestra reducida (n=10)
  * Período de evaluación corto (2 semanas)

----

# Trabajo futuro

* **Evaluación exhaustiva**
  * Muestra ampliada (n>100)
  * Estudio longitudinal (3-6 meses)

* **Mejoras técnicas**
  * Refinamiento del modelo PPO con datos reales
  * Adaptación STT para acentos no nativos

* **Expansión de funcionalidades**
  * Módulos para dominios especializados
  * Componente social para práctica colaborativa

---
layout: section
---

# Conclusiones

----

# Repositorios públicos

* **Frontend**:
  * github.com/EmaSuriano/language-learning-client
  * Next.js, TypeScript, Tailwind CSS

* **Backend**:
  * github.com/EmaSuriano/language-learning-server
  * FastAPI, Python, LangChain, Stable-Baselines3

* **Licencia MIT**: Código abierto para la comunidad

----

# Conclusiones

* La combinación RL + Transformers + RAG permite superar limitaciones de sistemas tradicionales

* Los resultados preliminares muestran el potencial para transformar el aprendizaje de idiomas

* La personalización dinámica y las interacciones naturales son clave para mejorar la experiencia educativa

* Un paso hacia educación adaptativa, contextual y centrada en el estudiante

----

# Agradecimientos

* **José Gabriel García Pardo**, director del TFM
* Profesores y compañeros del máster
* Mi familia y amigos por su apoyo
* Universidad Internacional de Valencia (VIU)

[*Imagen de agradecimiento*]

----

# Preguntas

[*Imagen con signo de interrogación*]

## ¡Gracias por su atención!

¿Preguntas?

[*Información de contacto*]

---
layout: recording

direction: right

# the image source
image: /recording/learning-progress.gif
---

# Learning progress

---
layout: recording

direction: left

# the image source
image: /recording/learning-progress.gif
---

# Learning progress


---
layout: iframe
url: https://emasuriano.github.io/language-learning-client/
---


