
---
# PROMPT
Utilizá la skill desarrollada para resolver el siguiente ejercicio.


Refine los siguientes requerimientos en términos de escenarios de atributos de calidad, con
ayuda de los respectivos templates de escenarios (6 partes). En caso de ser necesario, asuma
las partes faltantes.

a) Un sistema de cajero automático debe ser fácil de usar por una persona mayor.

b) Se desea desarrollar un procesador de texto que sea tolerante a fallas, particularmente
en casos de errores al hacer el rendering (pre-visualización) de un documento
previamente a su impresión.

c) Un sistema de monitoreo de radares debe soportar la incorporación de varios dispositivos
(radares) con distinta tecnología para su monitoreo.

d) En un sistema de seguros debe ser posible configurar distintas políticas para el cálculo de
retenciones sobre las pólizas emitidas, en función del perfil impositivo del comprador de
la póliza.

e) Una aplicación móvil para e-commerce debe ser capaz de realizar varias búsquedas geolocalizadas de forma rápida, especialmente en períodos de promociones.


Aplicá las instrucciones, procedimientos y criterios definidos en la skill. No utilices un procedimiento diferente al establecido por la skill.

Ignorar "apendice.txt"

---
# RESPUESTA
A continuación se presenta el refinamiento de los requerimientos seleccionados, estructurados bajo el modelo de seis partes del **Software Engineering Institute (SEI)** y complementados con la **técnica Response Measure Straw Man de Michael Keeling** para abordar la ambigüedad de las métricas no especificadas. 

---

### a) Sistema de Cajero Automático (Usabilidad)

##### ESCENARIO DE CALIDAD: Facilidad de Operación para Adultos Mayores en Cajero Automático
*   **Atributo de Calidad:** Usabilidad.
*   **Fuente del Estímulo:** Usuario final (Persona de la tercera edad / Adulto mayor).
*   **Estímulo:** Intenta realizar una transacción bancaria habitual (p. ej., extracción de efectivo o consulta de saldo).
*   **Artefacto:** Interfaz de usuario (pantalla táctil y teclado físico) del cajero automático.
*   **Ambiente:** Operación normal.
*   **Respuesta:** El sistema presenta una interfaz accesible con tipografía clara, flujo asistido y confirmaciones visuales/sonoras, guiando al usuario para completar la operación sin errores irrecuperables.
*   **Medida de Respuesta:** **No especificada** — la expresión "fácil de usar" es una medida ambigua que requiere definir criterios cuantitativos y verificables con los stakeholders.
*   **Justificación:** El requerimiento busca reducir la barrera cognitiva y física de uso para adultos mayores, pero carece de un umbral objetivo para validar su cumplimiento.

##### BLOQUE DE REFINAMIENTO (Técnica Straw Man de Keeling)
*   **Componente Afectado:** Medida de Respuesta.
*   **Métrica Ambigua Detectada:** "fácil de usar".
*   **Honest Straw Man (Propuesta Realista):**
    *   **Propuesta:** "El 90% de los usuarios mayores de 65 años deben completar una extracción de dinero en ≤ 60 segundos al primer intento, con una tasa de error de transacción ≤ 5% y sin requerir asistencia externa".
    *   **Justificación técnica:** Define un estándar cuantitativo de tiempo de tarea y tasa de éxito independiente para evaluar la usabilidad de la interfaz.
*   **Outrageous Straw Man (Propuesta Provocadora):**
    *   **Propuesta:** "El 100% de los usuarios adultos mayores debe completar cualquier transacción en ≤ 5 segundos presionando un solo botón en pantalla".
    *   **Justificación técnica:** Establece un límite exagerado para forzar la discusión sobre las capacidades motoras/cognitivas reales del usuario y el nivel factible de simplificación.
*   **Pregunta de Elicitación:** ¿Cuál es el tiempo máximo aceptable para completar la transacción y qué porcentaje de éxito al primer intento se requiere para considerar la interfaz como accesible?

---

### b) Procesador de Texto (Confiabilidad / Tolerancia a Fallas)

##### ESCENARIO DE CALIDAD: Tolerancia a Fallas durante el Rendering de Pre-visualización
*   **Atributo de Calidad:** Confiabilidad / Disponibilidad.
*   **Fuente del Estímulo:** Subsistema interno / Excepción durante el proceso de dibujado de documentos.
*   **Estímulo:** Ocurrencia de un error inesperado al procesar o renderizar la pre-visualización previa a la impresión.
*   **Artefacto:** Módulo de rendering / Pre-visualización de impresión.
*   **Ambiente:** Operación normal durante la edición de documentos.
*   **Respuesta:** El sistema captura la excepción, aísla la falla en el módulo de vista previa sin cerrar la aplicación principal, notifica el problema al usuario y retorna al modo de edición.
*   **Medida de Respuesta:** **No especificada** — la declaración "tolerante a fallas" requiere precisar métricas de contención del error y de preservación de datos.
*   **Justificación:** Previene el colapso abrupto de la aplicación (*crash*) y la pérdida del trabajo del usuario ante un fallo en la vista previa.

##### BLOQUE DE REFINAMIENTO (Técnica Straw Man de Keeling)
*   **Componente Afectado:** Medida de Respuesta.
*   **Métrica Ambigua Detectada:** "tolerante a fallas".
*   **Honest Straw Man (Propuesta Realista):**
    *   **Propuesta:** "El 100% de las fallas de rendering deben ser aisladas en un proceso secundario (*sandbox*), garantizando 0% de pérdida de datos no guardados y un tiempo de recuperación del editor ≤ 1 segundo".
    *   **Justificación técnica:** Promueve la adopción de desacoplamiento de procesos para garantizar que un fallo secundario no afecte la disponibilidad del editor principal.
*   **Outrageous Straw Man (Propuesta Provocadora):**
    *   **Propuesta:** "Ante una falla de rendering, el sistema debe autoreparar el documento corrupto e imprimirlo correctamente en 0 milisegundos sin mostrar advertencias".
    *   **Justificación técnica:** Dispara el debate sobre si se busca autorrecuperación transparente (*self-healing*) o simplemente degradación elegante (*graceful degradation*).
*   **Pregunta de Elicitación:** ¿Es aceptable desactivar temporalmente la vista previa manteniendo el documento intacto, o se exige reintentar el rendering automáticamente?

---

### c) Sistema de Monitoreo de Radares (Modificabilidad / Extensibilidad)

##### ESCENARIO DE CALIDAD: Incorporación de Dispositivos Radar Heterogéneos
*   **Atributo de Calidad:** Modificabilidad / Interoperabilidad.
*   **Fuente del Estímulo:** Integrador / Desarrollador del sistema.
*   **Estímulo:** Solicitud de incorporar e integrar un nuevo radar con protocolo o tecnología distinta a las soportadas.
*   **Artefacto:** Capa de integración / Módulo de adaptadores de dispositivos.
*   **Ambiente:** Tiempo de mantenimiento o desarrollo.
*   **Respuesta:** El sistema permite agregar el nuevo driver/adaptador de radar sin requerir modificaciones en la lógica central de procesamiento ni interrumpir el monitoreo de los radares activos.
*   **Medida de Respuesta:** **No especificada** — "soportar la incorporación" no determina el esfuerzo, tiempo de desarrollo ni el impacto permitido en el código existente.
*   **Justificación:** Garantiza la extensibilidad frente a la evolución tecnológica del hardware sin reestructuraciones arquitectónicas mayores.

##### BLOQUE DE REFINAMIENTO (Técnica Straw Man de Keeling)
*   **Componente Afectado:** Medida de Respuesta.
*   **Métrica Ambigua Detectada:** "soportar la incorporación de varios dispositivos con distinta tecnología".
*   **Honest Straw Man (Propuesta Realista):**
    *   **Propuesta:** "La integración de un nuevo modelo de radar mediante la implementación de un componente adaptador debe requerir ≤ 3 días-persona de desarrollo y 0 líneas de código modificadas en el núcleo del sistema".
    *   **Justificación técnica:** Orienta la arquitectura hacia un patrón de diseño basado en plugins/adaptadores (*Adapter/Strategy*) para aislar las dependencias de hardware.
*   **Outrageous Straw Man (Propuesta Provocadora):**
    *   **Propuesta:** "Cualquier radar no conocido debe conectarse vía *Plug-and-Play* y ser reconocido por el sistema en ≤ 1 segundo sin necesidad de escribir código o compilar".
    *   **Justificación técnica:** Plantea el dilema entre soportar extensibilidad mediante código/drivers o requerir un motor de autodescubrimiento dinámico.
*   **Pregunta de Elicitación:** ¿La inclusión de nuevos radares se realizará mediante actualización de componentes en tiempo de desarrollo o mediante carga dinámica en tiempo de ejecución?

---

### d) Sistema de Seguros (Modificabilidad / Configurabilidad)

##### ESCENARIO DE CALIDAD: Configurabilidad de Políticas de Retención según Perfil Impositivo
*   **Atributo de Calidad:** Modificabilidad.
*   **Fuente del Estímulo:** Administrador de Negocio / Analista Impositivo.
*   **Estímulo:** Definición o actualización de una política para el cálculo de retenciones sobre pólizas emitidas.
*   **Artefacto:** Motor de reglas de negocio / Módulo de retenciones fiscales.
*   **Ambiente:** Tiempo de operación o configuración.
*   **Respuesta:** El sistema permite parametrizar las nuevas reglas de retención según el perfil impositivo del comprador y aplicarlas inmediatamente a las nuevas emisionas de pólizas.
*   **Medida de Respuesta:** **No especificada** — la posibilidad de "configurar distintas políticas" no especifica si debe realizarse por interfaz administrativa o código, ni la latencia de entrada en vigencia.
*   **Justificación:** Permite adaptar el sistema con agilidad ante cambios normativos o fiscales sin depender de ciclos de liberación de software.

##### BLOQUE DE REFINAMIENTO (Técnica Straw Man de Keeling)
*   **Componente Afectado:** Medida de Respuesta.
*   **Métrica Ambigua Detectada:** "posible configurar distintas políticas".
*   **Honest Straw Man (Propuesta Realista):**
    *   **Propuesta:** "Un usuario de negocio calificado debe poder ingresar una nueva política de retención a través de un panel de administración en ≤ 15 minutos, entrando en vigencia sin reiniciar los servicios".
    *   **Justificación técnica:** Favorece el uso de un motor de reglas (*Rule Engine*) que desacople la lógica fiscal del código compilado.
*   **Outrageous Straw Man (Propuesta Provocadora):**
    *   **Propuesta:** "Modificar una política de retención debe requerir la reprogramación en el código fuente por parte de un desarrollador, con un despliegue de 8 horas en ventana de mantenimiento".
    *   **Justificación técnica:** Provoca la confirmación de si la "configuración" es 100% autogestionada por negocio o si se toleran cambios por desarrollo.
*   **Pregunta de Elicitación:** ¿Quién será el actor responsable de configurar las políticas y si los cambios deben impactar en tiempo real o en diferido?

---

### e) Aplicación Móvil E-commerce (Performance / Escalabilidad)

##### ESCENARIO DE CALIDAD: Rendimiento de Búsquedas Geolocalizadas en Eventos de Alta Carga
*   **Atributo de Calidad:** Performance / Escalabilidad.
*   **Fuente del Estímulo:** Usuarios finales de la aplicación móvil (compradores concurrentes).
*   **Estímulo:** Envío masivo de peticiones de búsquedas geolocalizadas de productos o promociones.
*   **Artefacto:** Servicio de búsquedas geolocalizadas / Base de datos espacial / API Gateway.
*   **Ambiente:** Período de promociones (pico de tráfico / sobrecarga de peticiones).
*   **Respuesta:** El sistema procesa las peticiones espaciales, calcula la geolocalización y retorna la lista de resultados ordenados al dispositivo móvil.
*   **Medida de Respuesta:** **No especificada** — "de forma rápida" y "períodos de promociones" son términos cualitativos que no definen tiempos de respuesta ni volumen de concurrencia.
*   **Justificación:** En eventos masivos (*CyberMonday, Black Friday*), la latencia en las búsquedas geográficas impacta directamente en las ventas y la conversión del negocio.

##### BLOQUE DE REFINAMIENTO (Técnica Straw Man de Keeling)
*   **Componente Afectado:** Medida de Respuesta y Ambiente.
*   **Métrica Ambigua Detectada:** "de forma rápida" / "períodos de promociones".
*   **Honest Straw Man (Propuesta Realista):**
    *   **Propuesta:** "Soportar una carga pico de 5.000 búsquedas geolocalizadas por segundo durante días de promoción, entregando el 95% de las respuestas en la app móvil en ≤ 1,5 segundos".
    *   **Justificación técnica:** Define un umbral de concurrencia realista y una latencia móvil aceptable para mantener la fluidez de la experiencia de usuario.
*   **Outrageous Straw Man (Propuesta Provocadora):**
    *   **Propuesta:** "Soportar 1.000.000 de búsquedas geolocalizadas por segundo con una latencia de respuesta ≤ 10 milisegundos bajo redes 3G".
    *   **Justificación técnica:** Obliga a discutir los límites reales de la infraestructura en la nube, la indexación geoespacial y el uso de cachés geográficas.
*   **Pregunta de Elicitación:** ¿Cuál es la cantidad estimada de usuarios concurrentes en eventos de promoción y cuál es el tiempo máximo de espera tolerado en el dispositivo?

---

### Árbol de Utilidad Consolidado

A continuación se sintetizan y priorizan los escenarios dentro del **Árbol de Utilidad**, considerando la importancia para el negocio y el riesgo/dificultad arquitectónica de cada uno:

##### ÁRBOL DE UTILIDAD
**Objetivo del sistema:** Consolidado de Requerimientos Significativos Arquitecturalmente (ASRs)

```text
[Objetivo del Sistema]
│
├── Usabilidad
│   └── [Operación de Cajero Automático por Adultos Mayores]
│       Importancia: Alta
│       Dificultad: Media
│       Prioridad: Alta
│
├── Confiabilidad / Disponibilidad
│   └── [Aislamiento de Fallas en Rendering de Pre-visualización]
│       Importancia: Alta
│       Dificultad: Alta
│       Prioridad: Alta
│
├── Modificabilidad
│   ├── [Extensibilidad para Nuevas Tecnologías de Radar]
│   │   Importancia: Media
│   │   Dificultad: Alta
│   │   Prioridad: Alta
│   │
│   └── [Configurabilidad de Políticas de Retención de Seguros]
│       Importancia: Alta
│       Dificultad: Media
│       Prioridad: Alta
│
└── Performance / Escalabilidad
    └── [Búsquedas Geolocalizadas en Picos de Tráfico de E-commerce]
        Importancia: Alta
        Dificultad: Alta
        Prioridad: Alta
```

*(Nota: La prioridad se ha calculado alineada con los criterios estándar de la matriz de priorización).*

---

💡 **¿Siguiente paso sugerido?**
Podemos profundizar en las **tácticas arquitectónicas específicas** (p. ej., patrones de aislamiento para el rendering, motores de reglas para los seguros o estrategias de indexación geoespacial) necesarias para satisfacer los escenarios priorizados con más alta dificultad.