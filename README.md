# PriorityGrad

PriorityGrad es un organizador de tareas inteligentes para estudiantes. El sistema ayuda a resolver el desorden de las entregas acumuladas calculando automáticamente qué tareas debes hacer primero para asegurar el promedio.

## El Problema que Resuelve

Como estudiantes, muchas veces hacemos primero la tarea que vence mañana aunque valga muy pocos puntos, dejando de lado el proyecto final que vale la mitad de la calificación. PriorityGrad elimina esa indecisión ordenando tus pendientes mediante un algoritmo que analiza la fecha de entrega y el valor de cada actividad.

## Características Principales

* **Registro de Materias:** Organiza tus tareas por cada clase.
* **Algoritmo de Prioridad:** El sistema calcula un puntaje automático para cada pendiente.
* **Tablero Visual:** Una lista limpia que te dice exactamente en qué enfocarte hoy.

## Arquitectura del Software

Para este proyecto utilicé el patrón **MVC (Modelo-Vista-Controlador)**. Esto mantiene el código ordenado y separado en tres partes:

1. **Modelo:** Guarda los datos de las tareas y procesa la fórmula matemática de las prioridades.
2. **Vista:** La pantalla limpia y los formularios con los que interactúa el estudiante.
3. **Controlador:** El intermediario que recibe las acciones de la pantalla y le pide al modelo actualizar la información.

Gracias a esta estructura, si en el futuro se quiere cambiar el diseño visual o pasar el proyecto a una aplicación móvil, la lógica interna del algoritmo seguirá funcionando sin cambiar una sola línea de código.


