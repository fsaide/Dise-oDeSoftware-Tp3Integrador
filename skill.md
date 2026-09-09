# SKILL

1. [Objetivo](#objetivo)
2. [Alcance](#alcance)
3. [Conocimientos de respaldo](#conocimientos-de-respaldo)
4. [Conceptos claves](#conceptos-claves)
5. [Template SEI](#template-sei)
6. [Árbol de utilidad](#árbol-de-utilidad)
7. [Procedimiento de generación](#procedimiento-de-generación)
8. [Reglas de validación](#reglas-de-validación)
9. [Manejo de información faltante](#manejo-de-información-faltante)
10. [Formato de salida](#formato-de-salida)
11. [Ejemplos de testeo](#ejemplos-de-testeo)

---

## Objetivo

Esta skill permite analizar requerimientos de software **funcionales, no funcionales o declaraciones informales de stakeholders** y transformarlos en **Escenarios de Atributos de Calidad** técnicamente rigurosos, completos y verificables, utilizando el modelo de seis partes del **Software Engineering Institute (SEI)** y las dinámicas ágiles de facilitación de **Michael Keeling**.

Su objetivo principal es asistir al arquitecto en la especificación y análisis de **Requerimientos Significativos Arquitecturalmente (ASRs)**.

La skill debe:

- Identificar los atributos de calidad relevantes para un requerimiento.
- Construir escenarios de calidad utilizando el template SEI.
- Detectar escenarios incompletos, ambiguos o no verificables.
- Identificar qué información falta para completar un escenario.
- Utilizar la técnica **Response Measure Straw Man** como mecanismo de elicitación cuando sea necesario.
- Construir árboles de utilidad para organizar y priorizar escenarios de calidad.
- Mantener trazabilidad entre los escenarios generados y la información proporcionada.

---

## Alcance

La skill debe ser capaz de:

- **Identificar y clasificar** los atributos de calidad relevantes, tanto explícitos como implícitos, a partir de las necesidades expresadas.

- **Estructurar escenarios formales** utilizando las seis partes del template SEI:
  - Fuente del estímulo.
  - Estímulo.
  - Artefacto.
  - Ambiente.
  - Respuesta.
  - Medida de respuesta.

- **Auditar la completitud** de escenarios existentes, identificando:
  - Componentes faltantes.
  - Información ambigua.
  - Expresiones subjetivas.
  - Medidas de respuesta débiles o no verificables.

- **Refinar escenarios incompletos** mediante la técnica Response Measure Straw Man de Keeling, proponiendo hipótesis provisionales que faciliten la discusión con los stakeholders.

- **Garantizar la trazabilidad** entre el requerimiento original y el escenario generado.

- **Evitar inventar requisitos, valores, condiciones o restricciones** que no estén respaldados por la información proporcionada.

- **Construir árboles de utilidad**, organizando atributos de calidad y escenarios relacionados.

- **Priorizar escenarios** considerando su importancia para el negocio y su dificultad o riesgo arquitectónico.

Las inferencias realizadas por la skill deben identificarse como tales cuando no estén explícitamente presentes en el requerimiento.

Las propuestas realizadas mediante **Straw Man** son hipótesis provisionales y **no deben considerarse requisitos confirmados**.

---

## Conocimientos de respaldo

La skill debe utilizar como referencia:

- Definiciones de atributos de calidad.
- Modelos de escenarios de calidad del SEI.
- Taxonomías de atributos de calidad.
- Conceptos de arquitectura de software.
- Criterios para la construcción y evaluación de escenarios de calidad.
- Material bibliográfico proporcionado por la actividad.
- Material oficial de cátedra.

Además, debe regirse por los siguientes lineamientos:

1. **Modelo de escenarios del SEI:** estructura de escenarios, taxonomías, estímulos, respuestas y medidas de respuesta.

2. **Michael Keeling — Design It!:** dinámicas ágiles para talleres de arquitectura, Quality Attribute Workshop (QAW), participación de stakeholders y técnica Response Measure Straw Man.

3. **Material oficial de cátedra:** metodologías de diseño y ejercicios prácticos relacionados con atributos y escenarios de calidad.

Cuando exista una definición específica en el material proporcionado, debe priorizarse dicha definición.

Las propuestas basadas en Straw Man deben utilizarse como mecanismos de **elicitación y discusión**, no como sustitutos de requisitos confirmados por los stakeholders.

---

## Conceptos claves

### Atributo de Calidad

Propiedad del sistema que determina alguna característica observable de su comportamiento y que puede influir en las decisiones arquitectónicas.

Ejemplos:

- Performance.
- Seguridad.
- Disponibilidad.
- Usabilidad.
- Modificabilidad.
- Interoperabilidad.

El atributo de calidad **clasifica el escenario**, pero no constituye una de las seis partes del template SEI.

### Escenario de Calidad

Descripción concreta y verificable de cómo debe comportarse el sistema ante un estímulo determinado, bajo determinadas condiciones.

Un escenario de calidad debe especificar:

1. Fuente del estímulo.
2. Estímulo.
3. Artefacto.
4. Ambiente.
5. Respuesta.
6. Medida de respuesta.

### Response Measure Straw Man

Técnica de facilitación utilizada cuando los stakeholders no tienen definido un criterio cuantitativo para medir un atributo de calidad.

Consiste en proponer valores provisionales para generar discusión y facilitar la definición del requisito.

#### Honest Straw Man

Propuesta provisional basada en un valor razonable o habitual para el dominio de aplicación.

Debe presentarse explícitamente como una **hipótesis pendiente de validación**.

#### Outrageous Straw Man

Propuesta deliberadamente extrema o exagerada cuyo objetivo es provocar una reacción del stakeholder y ayudar a establecer el límite aceptable.

También constituye una **hipótesis pendiente de validación**.

---

## Template SEI

Cada escenario debe estructurarse explícitamente mediante las siguientes seis partes:

### 1. Fuente del Estímulo

Entidad humana, sistema externo u otro actor que genera el evento.

Ejemplos:

- Usuario final.
- Administrador.
- Sistema externo.
- Atacante.
- Servicio de terceros.

### 2. Estímulo

Evento o condición que llega al sistema y desencadena una respuesta.

Ejemplos:

- Solicitud de reporte.
- Solicitud de pago.
- Caída de una conexión.
- Intento de inicio de sesión.
- Cambio en las reglas de negocio.

### 3. Artefacto

Parte del sistema que recibe o procesa el estímulo.

Ejemplos:

- Sistema completo.
- Módulo de pagos.
- Base de datos.
- Servicio de autenticación.
- Sistema de monitoreo.

### 4. Ambiente

Condiciones operativas bajo las cuales ocurre el estímulo.

Ejemplos:

- Operación normal.
- Pico de tráfico.
- Sobrecarga.
- Mantenimiento.
- Recuperación ante desastres.

### 5. Respuesta

Comportamiento cualitativo y observable que debe realizar el sistema ante el estímulo.

Ejemplos:

- Procesa la solicitud.
- Rechaza el acceso.
- Registra el evento.
- Activa un servidor secundario.
- Notifica al administrador.

### 6. Medida de Respuesta

Criterio objetivo utilizado para determinar si la respuesta es satisfactoria.

Ejemplos:

- Tiempo de respuesta ≤ 500 ms.
- Disponibilidad ≥ 99,9%.
- Recuperación en menos de 5 minutos.
- 95% de las solicitudes procesadas correctamente.

La medida de respuesta debe ser **objetiva y, cuando sea posible, cuantificable y verificable**.

---

## Árbol de utilidad

El árbol de utilidad permite organizar y priorizar los escenarios de calidad relevantes para la arquitectura del sistema.

La estructura debe organizarse jerárquicamente:

1. **Objetivo general del sistema.**
2. **Atributo de calidad.**
3. **Escenario de calidad.**
4. **Importancia.**
5. **Dificultad o riesgo arquitectónico.**
6. **Prioridad resultante.**

Cada escenario incluido en el árbol debe corresponder a un escenario de calidad previamente identificado.

Para cada escenario se debe determinar:

- **Importancia para el negocio:** Alta / Media / Baja.
- **Dificultad o riesgo arquitectónico:** Alta / Media / Baja.
- **Prioridad resultante:** Alta / Media / Baja.

### Regla de priorización

La prioridad debe considerar conjuntamente la importancia para el negocio y la dificultad o riesgo arquitectónico.

Como criterio orientativo:

| Importancia | Dificultad | Prioridad |
|---|---|---|
| Alta | Alta | Alta |
| Alta | Media | Alta |
| Alta | Baja | Media |
| Media | Alta | Alta |
| Media | Media | Media |
| Media | Baja | Baja |
| Baja | Alta | Media |
| Baja | Media | Baja |
| Baja | Baja | Baja |

Esta tabla constituye una guía de priorización y puede modificarse si el material de cátedra establece otro criterio.

Cuando no exista información suficiente para determinar la importancia o dificultad, debe indicarse que el valor está **pendiente de validación** en lugar de inventarlo.

### Formato del árbol

```text
[Objetivo del sistema]

│
├── [Atributo de Calidad 1]
│   │
│   ├── [Escenario 1]
│   │   Importancia: Alta
│   │   Dificultad: Alta
│   │   Prioridad: Alta
│   │
│   └── [Escenario 2]
│       Importancia: Media
│       Dificultad: Baja
│       Prioridad: Baja
│
└── [Atributo de Calidad 2]
    │
    └── [Escenario 3]
        Importancia: Alta
        Dificultad: Media
        Prioridad: Alta
```

---

## Procedimiento de generación

```text
[Analizar Requerimiento]
          │
          ▼
[Identificar Requisitos]
          │
          ▼
[Mapear Atributos de Calidad]
          │
          ▼
[Estructurar Escenario SEI]
          │
          ▼
   (¿Está Completo?)
       ├── SÍ ──> [Validar Medida de Respuesta]
       │                │
       │                ▼
       │        [Generar Escenario]
       │
       └── NO ──> [Identificar Información Faltante]
                         │
                         ▼
                  [Formular Preguntas]
                         │
                         ▼
              [¿Se necesita Straw Man?]
                    ├── NO
                    │
                    └── SÍ
                         │
                         ├──> [Honest Straw Man]
                         │
                         └──> [Outrageous Straw Man]
                                  │
                                  ▼
                         [Generar Salida]
                                  │
                                  ▼
                       [Construir Árbol de Utilidad]
```

### Paso 1: Analizar el requerimiento

Analizar la descripción proporcionada e identificar:

- Objetivo del sistema.
- Actores.
- Requisitos.
- Restricciones.
- Condiciones operativas.
- Necesidades relacionadas con atributos de calidad.

### Paso 2: Identificar requisitos de calidad

Distinguir los requisitos funcionales de aquellos relacionados con atributos de calidad.

No asumir que todo requerimiento implica necesariamente un atributo de calidad específico.

### Paso 3: Identificar los atributos de calidad

Seleccionar únicamente los atributos respaldados por la información proporcionada.

No seleccionar atributos simplemente porque sean habituales en sistemas similares.

### Paso 4: Determinar el comportamiento a evaluar

Para cada atributo identificado, determinar:

- Qué evento ocurre.
- Qué parte del sistema se ve afectada.
- Bajo qué condiciones ocurre.
- Qué comportamiento se espera.
- Cómo se podría verificar.

### Paso 5: Construir el escenario SEI

Completar las seis partes:

1. Fuente.
2. Estímulo.
3. Artefacto.
4. Ambiente.
5. Respuesta.
6. Medida de respuesta.

### Paso 6: Verificar consistencia

Comprobar que cada elemento del escenario esté respaldado por el requerimiento o por una inferencia explícitamente identificada.

### Paso 7: Validar la medida de respuesta

Comprobar que la medida:

- Sea objetiva.
- Sea verificable.
- Evite términos subjetivos.
- Sea cuantificable cuando corresponda.

### Paso 8: Detectar información faltante

Si algún componente no puede determinarse, marcarlo como **No especificado** o **Pendiente de validación**.

No inventar información para completar artificialmente el escenario.

### Paso 9: Aplicar Straw Man cuando corresponda

Si la principal dificultad consiste en definir una medida de respuesta, puede utilizarse:

- Honest Straw Man.
- Outrageous Straw Man.

Ambas propuestas deben presentarse separadas del escenario principal y claramente identificadas como hipótesis provisionales.

### Paso 10: Presentar los escenarios

Utilizar el formato de salida establecido.

### Paso 11: Agrupar los escenarios

Agrupar los escenarios según su atributo de calidad correspondiente.

### Paso 12: Construir el árbol de utilidad

Incluir únicamente escenarios previamente identificados.

### Paso 13: Determinar la prioridad

Para cada escenario:

1. Evaluar importancia para el negocio.
2. Evaluar dificultad o riesgo arquitectónico.
3. Determinar la prioridad resultante.

Si la información disponible no permite determinar alguno de estos valores, indicarlo como pendiente de validación.

### Paso 14: Verificación final

Comprobar que:

- Todos los escenarios estén respaldados por la información disponible.
- No existan requisitos inventados.
- Los escenarios tengan sus seis componentes.
- Las medidas sean verificables o estén marcadas como faltantes.
- Los escenarios del árbol correspondan a escenarios generados previamente.
- Las propuestas Straw Man estén claramente diferenciadas de los requisitos confirmados.

---

## Reglas de validación

Un escenario completo debe contener las seis partes del template SEI:

- **Fuente del estímulo:** identificada.
- **Estímulo:** representa un evento concreto.
- **Artefacto:** claramente especificado.
- **Ambiente:** especificado.
- **Respuesta:** describe un comportamiento esperado y observable.
- **Medida de respuesta:** permite evaluar objetivamente el resultado.

### Expresiones ambiguas

No considerar suficientes expresiones como:

- "Rápidamente".
- "Muy rápido".
- "Con alta seguridad".
- "De manera eficiente".
- "Fácilmente".
- "Con buena disponibilidad".
- "Sin demoras".

Cuando aparezcan, deben identificarse como **medidas ambiguas** y solicitarse un criterio verificable.

### Respuesta vs. medida de respuesta

La skill debe mantener ambas partes diferenciadas:

**Respuesta:** describe **qué hace** el sistema.

**Medida de respuesta:** describe **cómo se determina si lo hizo satisfactoriamente**.

Ejemplo:

- **Respuesta:** El sistema procesa la solicitud de pago y devuelve una confirmación.
- **Medida de respuesta:** El 99% de las solicitudes debe recibir respuesta en ≤ 1,5 segundos.

### Trazabilidad

El escenario debe ser consistente con el requerimiento original.

La skill no debe introducir:

- Nuevos actores.
- Nuevas amenazas.
- Nuevos componentes.
- Nuevas restricciones.
- Nuevos valores.
- Nuevas métricas.

salvo que sean presentados explícitamente como **inferencias** o como propuestas **Straw Man**.

---

## Manejo de información faltante

Cuando no exista información suficiente para completar un escenario:

1. **No inventar** valores, requisitos, condiciones ni restricciones.

2. Identificar exactamente qué información falta.

3. Indicar qué componente del template SEI está afectado.

4. Formular una pregunta concreta para obtener la información necesaria.

5. Si el escenario puede construirse parcialmente, completarlo utilizando únicamente la información disponible.

6. Marcar explícitamente los componentes no determinados como **No especificado** o **Pendiente de validación**.

7. Si la falta de información corresponde a una métrica o umbral, evaluar la utilización de la técnica Straw Man.

### Regla para Straw Man

Las propuestas Straw Man:

- Son hipótesis provisionales.
- No son requisitos confirmados.
- Deben aparecer en un bloque separado.
- Deben identificarse explícitamente como propuestas para discusión.
- No deben incorporarse silenciosamente al escenario principal.
- Deben utilizarse para facilitar la conversación con los stakeholders.

---

## Formato de salida

### Escenario de calidad

### ESCENARIO DE CALIDAD: [Nombre descriptivo del escenario]

* **Atributo de Calidad:** [Performance / Seguridad / Disponibilidad / Usabilidad / etc.]

* **Fuente del Estímulo:** [Quién genera el estímulo]

* **Estímulo:** [Evento disparador]

* **Artefacto:** [Componente afectado]

* **Ambiente:** [Condiciones de operación]

* **Respuesta:** [Acción cualitativa observable]

* **Medida de Respuesta:** [Métrica objetiva y verificable]

* **Justificación:** [Por qué el escenario es relevante]

### Bloque de refinamiento

Incluir **únicamente cuando el requerimiento sea incompleto o ambiguo** y sea útil realizar una propuesta Straw Man.

---

### BLOQUE DE REFINAMIENTO (Técnica Straw Man de Keeling)

* **Componente Afectado:** [Medida de Respuesta / Ambiente / Fuente / etc.]

* **Métrica Ambigua Detectada:** [Expresión ambigua identificada]

* **Honest Straw Man (Propuesta Realista):**
    * **Propuesta:** "[Valor provisional]"
    * **Justificación técnica:** [Motivo de la propuesta]

* **Outrageous Straw Man (Propuesta Provocadora):**
    * **Propuesta:** "[Valor deliberadamente extremo]"
    * **Justificación técnica:** [Motivo por el cual puede provocar discusión]

* **Pregunta de Elicitación:** [Pregunta concreta para definir el requisito]

### Árbol de utilidad

### ÁRBOL DE UTILIDAD

**Objetivo del sistema:** [Objetivo general]

```text
[Objetivo del sistema]

│
├── [Atributo de Calidad 1]
│   │
│   ├── [Escenario 1]
│   │   Importancia: [Alta/Media/Baja]
│   │   Dificultad: [Alta/Media/Baja]
│   │   Prioridad: [Alta/Media/Baja]
│   │
│   └── [Escenario 2]
│       Importancia: [Alta/Media/Baja]
│       Dificultad: [Alta/Media/Baja]
│       Prioridad: [Alta/Media/Baja]
│
└── [Atributo de Calidad 2]
    │
    └── [Escenario 3]
        Importancia: [Alta/Media/Baja]
        Dificultad: [Alta/Media/Baja]
        Prioridad: [Alta/Media/Baja]
```

---

## Ejemplos de testeo

### Caso de prueba 1: Requerimiento completo — Performance

**Entrada:**

> "En horas de pico de compras, el servidor de pagos debe procesar las solicitudes de pago con un tiempo de respuesta de máximo 1.5 segundos para el 99% de las transacciones."

**Salida esperada:**

### ESCENARIO DE CALIDAD: Procesamiento de Pagos en Pico de Carga

* **Atributo de Calidad:** Performance

* **Fuente del Estímulo:** Cliente / Comprador

* **Estímulo:** El cliente envía una solicitud de pago.

* **Artefacto:** Módulo / Pasarela de Pagos

* **Ambiente:** Horas de pico de compras, con alta carga de transacciones.

* **Respuesta:** El sistema procesa la transacción mediante la pasarela de pago y emite una confirmación.

* **Medida de Respuesta:** Tiempo de respuesta menor o igual a 1,5 segundos para el 99% de las transacciones.

* **Justificación:** El requerimiento define explícitamente el ambiente de alta carga y establece una medida cuantificable y verificable.

---

### Caso de prueba 2: Requerimiento ambiguo o incompleto — Seguridad

**Entrada:**

> "El sistema de monopatines tiene que ser muy seguro para que no nos roben datos."

**Salida esperada:**

### ESCENARIO DE CALIDAD: Protección de Datos ante Accesos No Autorizados

* **Atributo de Calidad:** Seguridad

* **Fuente del Estímulo:** No especificada.

* **Estímulo:** Intento de acceso no autorizado a los datos.

* **Artefacto:** Datos del sistema.

* **Ambiente:** No especificado.

* **Respuesta:** El sistema debe impedir el acceso no autorizado a los datos.

* **Medida de Respuesta:** No especificada — requiere definir una métrica cuantificable y verificable con el stakeholder.

* **Justificación:** El requerimiento expresa una necesidad de seguridad, pero no especifica una amenaza concreta, las condiciones en las que ocurre el acceso ni una medida objetiva que permita verificar el cumplimiento.

---

### Caso de prueba 3: Construcción de árbol de utilidad

**Entrada:**

> "El sistema de comercio electrónico debe responder las solicitudes de compra en menos de 2 segundos durante períodos normales y debe estar disponible el 99.9% del tiempo. Los pagos son procesados por una pasarela externa."

**Salida esperada:**

### ESCENARIO DE CALIDAD: Procesamiento de Compras

* **Atributo de Calidad:** Performance

* **Fuente del Estímulo:** Cliente / Comprador

* **Estímulo:** El cliente envía una solicitud de compra.

* **Artefacto:** Sistema de comercio electrónico.

* **Ambiente:** Período normal de operación.

* **Respuesta:** El sistema procesa la solicitud de compra y devuelve una respuesta.

* **Medida de Respuesta:** Tiempo de respuesta menor a 2 segundos.

* **Justificación:** El requerimiento establece explícitamente un límite cuantificable de tiempo de respuesta y el ambiente en el que debe cumplirse.

### ESCENARIO DE CALIDAD: Disponibilidad del Sistema

* **Atributo de Calidad:** Disponibilidad

* **Fuente del Estímulo:** Usuario del sistema.

* **Estímulo:** Solicitud de acceso o utilización del sistema.

* **Artefacto:** Sistema de comercio electrónico.

* **Ambiente:** Operación normal del sistema.

* **Respuesta:** El sistema permanece operativo y disponible para atender las solicitudes.

* **Medida de Respuesta:** Disponibilidad del 99,9% del tiempo.

* **Justificación:** El requerimiento establece explícitamente un objetivo cuantificable de disponibilidad.

### ÁRBOL DE UTILIDAD

**Objetivo del sistema:** Proporcionar un sistema de comercio electrónico disponible y con tiempos de respuesta adecuados.

```text
Sistema de comercio electrónico

│
├── Performance
│   │
│   └── Procesamiento de compras
│       Importancia: Alta
│       Dificultad: Media
│       Prioridad: Alta
│
└── Disponibilidad
    │
    └── Disponibilidad del sistema
        Importancia: Alta
        Dificultad: Alta
        Prioridad: Alta
```

**Nota:** La dificultad arquitectónica se encuentra sujeta a validación cuando el requerimiento no proporciona información suficiente para determinarla. El hecho de que los pagos sean procesados por una pasarela externa no genera por sí mismo un nuevo escenario de calidad; únicamente constituye una restricción o contexto que debe considerarse al analizar los escenarios existentes.