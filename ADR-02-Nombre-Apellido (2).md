# ADR-02: [Vistas Arquitectónicas de PriorityGrad]

| Campo  | Valor |
|--------|-------|
| Autor  | [ Danna Albertos ] |
| Fecha  | 05/06/2026|
| Estado | `Propuesto` |

---

## Contexto

Una vez definida la arquitectura base del sistema en el ADR-01, es necesario documentar cómo se organiza el sistema desde distintas perspectivas. Cada vista responde a una pregunta diferente sobre el diseño: cómo se estructura el código, dónde se ejecuta físicamente, cómo se despliega y cómo se comporta en tiempo de ejecución.

Estas vistas permiten que cualquier persona del equipo entienda el sistema sin necesidad de revisar todo el código, y sirven como referencia para tomar decisiones futuras de escalabilidad o mantenimiento.

---

## Decisión

He decidido documentar la arquitectura de PriorityGrad utilizando el modelo de vistas 4+1, seleccionando las cuatro vistas principales que aplican al alcance actual del proyecto:

Vista lógica — organización interna del código en capas y responsabilidades
Vista física — infraestructura de hardware y red donde opera el sistema
Vista de despliegue — distribución de los artefactos de software en los nodos físicos
Vista de procesos — comportamiento del sistema en tiempo de ejecución durante un flujo clave


### ¿Por qué?

Elegí el modelo 4+1 ya que me permite comunicar la arquitectura desde múltiples ángulos sin ambigüedad. Cada vista está dirigida a un stakeholder diferente: la vista lógica le sirve al desarrollador para saber dónde colocar código nuevo, la vista física al equipo de infraestructura para dimensionar recursos, la vista de despliegue para entender qué componente corre en qué servidor, y la vista de procesos para verificar que los flujos principales funcionan correctamente.


### Alternativas consideradas

*(Mínimo 3 filas)*

| Alternativa | Por qué la descarté |
|-------------|---------------------|
| Documentar solo con texto sin diagramas         | No permite visualizar relaciones entre componentes de forma clara. Un párrafo describiendo la arquitectura se vuelve ambiguo rápidamente.                |
| Usar solo la vista lógica         | Una sola vista no cubre aspectos de infraestructura ni comportamiento en ejecución. El sistema necesita entenderse desde más de una perspectiva.                 |
| Modelo C4 completo (4 niveles de zoom)         | El nivel 3 (componentes) y nivel 4 (código) requieren un grado de detalle que aún no existe en el proyecto. Las 4 vistas del modelo 4+1 cubren mejor las necesidades actuales.                 |

---

## Consecuencias

**✅ Lo que gano:**

Técnica: Tener la vista lógica documentada facilita que cualquier nuevo desarrollador entienda la separación en capas (Controllers, Services, Models, Data) y sepa exactamente dónde agregar una nueva funcionalidad sin romper la estructura existente.

Proceso y equipo: Las vistas de despliegue y física sirven como guía para configurar los ambientes de desarrollo y producción. Esto evita que cada miembro del equipo configure el entorno de manera diferente y reduce errores de integración.

**⚠️ Lo que sacrifico o asumo:**

Limitación técnica: Los diagramas reflejan el estado actual del MVP. Cuando se agreguen funcionalidades como WebSockets para notificaciones en tiempo real o colas de mensajes para procesamiento asíncrono, las vistas de procesos y despliegue deberán actualizarse.

Deuda o riesgo: La vista física asume un despliegue sencillo en un solo servidor de aplicaciones. Si el proyecto escala a múltiples instancias o se migra a contenedores, la infraestructura cambiará significativamente y estos diagramas quedarán desactualizados.



## Diagrama

Maestro una disculpa, lo hice en canva por cuestión de tiempos :((

Vista Lógica : 

<img width="470" height="533" alt="Captura de pantalla 2026-06-05 234921" src="https://github.com/user-attachments/assets/de5ca02e-85f6-450c-8629-f38084a20221" />


Vista Física : 

<img width="610" height="518" alt="Captura de pantalla 2026-06-05 234959" src="https://github.com/user-attachments/assets/660341cc-9cdb-48eb-b50d-cd7f8f8fadbb" />


Vista de despliegue :

<img width="1221" height="473" alt="Captura de pantalla 2026-06-05 234728" src="https://github.com/user-attachments/assets/9b3d5c35-d92b-4eab-932d-49d14bf185c7" />


Vista de procesos : 

<img width="676" height="172" alt="Captura de pantalla 2026-06-05 234845" src="https://github.com/user-attachments/assets/d4ecaeb8-7ad5-4b20-8435-cb914307e4d1" />


## Declaración uso de AI
Yo Danna Pamela Albertos Sosa, declaro que efectivamente si utilicé AI para la finalización de la entrega de esta actividad.

