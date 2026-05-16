# ADR-01: [Título corto de la decisión]

| Campo  | Valor |
|--------|-------|
| Autor  | Danna Albertos |
| Fecha  | 15/05/2026 |
| Estado | `Propuesto`|

---

## Contexto

Para este proyecto estoy construyendo PriorityGra que es un organizador de tareas diseñado para estudiantes universitarios y/o de cualquier grado de escuela que enfrentan una alta carga de tareas y proyectos además de mantener una vida personal y profesional. Este sistema resuelve de manera directa el problema del sesgo de urgencia, el cual provoca que los alumnos dediquen su tiempo a actividades sencillas o de última hora en lugar de enfocarse en los entregables que realmente tienen un impacto crítico en su promedio final. Como restricciones principales para el diseño de este software, debo considerar que me encuentro en el tercer cuatrimestre de la ingeniería, por lo que requiero una estructura técnica que sea sólida y que demuestre un control claro sobre la separación de responsabilidades, pero sin añadir capas de infraestructura complejas que pongan en riesgo la entrega del proyecto en el límite de tiempo de menos de cuatro meses que dura el periodo escolar.

---

## Decisión

Para estructurar de forma correcta el código del sistema, tomé la decisión de implementar el patrón arquitectónico MVC estructurado bajo una arquitectura en capas. De acuerdo a este esquema la Vista se encargará exclusivamente de renderizar las pantallas con las que interactúa el estudiante. Por otro lado, el Controlador actuará como el intermediario que recibirá los eventos de la interfaz y se comunicará con el Modelo para procesar la información y por último, el Modelo representará la estructura de los datos del sistema y encapsulará de forma estricta las reglas, albergando en su interior el algoritmo de cálculo de prioridad que ordenará la lista de pendientes en automático.

### ¿Por qué?

Elegí el patrón MVC porque separa la interfaz de usuario, la lógica de negocio y el almacenamiento de datos, cumpliendo directamente con el principio de responsabilidad única como me lo solicitan. Esta separación elimina el acoplamiento en el código, lo que garantiza que cualquier cambio o rediseño en las pantallas de la aplicación no afecte ni altere el algoritmo matemático que calcula las prioridades académicas. Asimismo, el aislamiento de la lógica de negocio en el Modelo permite realizar pruebas de funcionamiento independientes sobre el algoritmo antes de construir la interfaz visual lo que optimiza el proceso de desarrollo individual, permitiendo avanzar por componentes modulares que se alinean con los tiempos de entrega y revisiones parciales del cuatrimestre sin generar desorden técnico.

### Alternativas consideradas

*(Mínimo 3 filas)*

| Alternativa | Por qué la descarté |
|-------------|---------------------|
| MVVM        | Por su enlace de datos ya que eso hace que sea más complejo al añadirse una curva por la información                 |
| MVP         | Obliga a programar manualmente las interacciones de pantalla a través del presentador y eso incrementa las líneas de código                 |
| Spaguetti   | Mezcla todo el código y hace que que dificíl de modificar en un futuro           |

---

## Consecuencias

**✅ Lo que gano:**

Al elegir este patrón, gano la ventaja técnica de que modificar el algoritmo o corregir errores en los datos será mucho más rápido y seguro, ya que el código no está mezclado con las pantallas de la aplicación. En cuanto al proceso de trabajo, esto me permite avanzar por partes de forma independientporque puedo programar y probar toda la lógica interna del sistema antes de perder tiempo diseñando la interfaz visual, lo que me ayuda a cumplir fácilmente con las revisiones.

**⚠️ Lo que sacrifico o asumo:**

Por otro lado, acepto la limitación técnica de que las peticiones del usuario tardarán un poco más en procesarse porque deben pasar si o si por el intermediario antes de llegar a los datos, aunque para el uso diario de un estudiante este retraso será imperceptible. Como riesgo del proyecto, asumo el peligro de acumular desorden en el código si, por las prisas de las entregas finales, cometo el error de meter lógica de cálculos directo en los archivos de la pantalla, rompiendo la separación que planifiqué.

## Diagrama

![Diagrama del sistema]

<img width="461" height="321" alt="PriorityGrad drawio" src="https://github.com/user-attachments/assets/d1bc42b3-8e23-47e6-9860-e3c53c97112c" />

