# Conceptos de Sistemas Operativos (SO)

## Tipos de Kernel y sus Diferencias

El **Kernel** de un sistema operativo es el núcleo, derivado de la palabra germánica "Kern", que se traduce como núcleo o hueso. Es el software base que permite la coordinación entre la parte digital y física de un equipo.

### Tipos de Kernel en la Actualidad

No hay un Kernel universal. Existen varios tipos con características propias para distintos sistemas operativos. A grandes rasgos, conocemos tres tipos:

- **Kernel Monolítico:** Núcleo grande que aglutina todos los procesos y permisos de un sistema. Se utiliza en sistemas como Linux, Windows, iOS y Android.
- **Microkernel:** Modelo más pequeño distribuido en módulos para la repartición de funciones. Aún ningún sistema trabaja exclusivamente con este tipo.
- **Kernel Híbrido:** Unión del primero con el segundo para una mayor eficiencia en el proceso de gestión de información. Puesto en práctica por Linux y OS X.

También, los Kernels se diferencian por su código. Tanto el Kernel de Windows como el de macOS son privados, mientras que Linux tiene parte del código público.

## User vs Kernel Mode

El **modo usuario** y el **modo kernel** son dos niveles de privilegio o modos distintos que un sistema operativo utiliza para ejecutar procesos.

### Modo Usuario:

- **Privilegios:** Acceso limitado a recursos del sistema y hardware. No pueden acceder directamente a dispositivos de hardware ni ejecutar instrucciones privilegiadas.
- **Responsabilidad:** Ejecución de software de aplicación regular. Interacción con el sistema operativo para solicitar servicios o recursos.
- **Aislamiento:** Proporciona una capa de aislamiento, evitando interferencias entre aplicaciones o con funciones centrales del sistema operativo.

### Modo Kernel:

- **Privilegios:** Acceso total al hardware y ejecución de instrucciones privilegiadas. Control total sobre los recursos del sistema.
- **Responsabilidad:** Ejecución de funciones centrales del sistema operativo, como planificación de procesos, gestión de memoria y controladores de dispositivos.
- **Aislamiento:** Opera en un nivel de privilegio más alto, permitiendo controlar y coordinar actividades de programas en modo usuario.

#### Diferencias Clave:

- Modo usuario para software de aplicación regular, modo kernel para funciones centrales del sistema operativo.
- En modo usuario, programas tienen acceso restringido al hardware y están aislados entre sí. En modo kernel, el sistema operativo tiene control total sobre los recursos de hardware.
- Modo usuario es donde se ejecutan la mayoría de las aplicaciones y proporciona una capa de protección y aislamiento. Modo kernel es donde el sistema operativo realiza tareas críticas que requieren control directo sobre el hardware.

El cambio entre modos es fundamental en los sistemas operativos modernos para mantener seguridad, estabilidad y adecuada asignación de recursos. Las llamadas al sistema y las interrupciones son métodos comunes utilizados para hacer la transición entre estos modos, permitiendo que programas de usuario soliciten servicios al sistema operativo o respondan a eventos de hardware.

## Interrupciones vs Trampas

### Interrupciones:

- **Definición:** Eventos externos que ocurren asíncronamente con la ejecución normal de un programa. Pueden ser generadas por dispositivos de hardware, como un temporizador o un teclado.
- **Origen:** Proviene de fuentes externas al procesador. Propósito puede ser notificar eventos o solicitar atención del sistema operativo.
- **Manejo:** Cuando ocurre una interrupción, el procesador suspende temporalmente la ejecución, guarda el estado y salta a un manejador específico.

### Trampas:

- **Definición:** Eventos generados internamente durante la ejecución de un programa debido a condiciones anómalas, como una división por cero o un acceso a memoria no permitido.
- **Origen:** Proviene de condiciones internas al procesador o del propio programa en ejecución.
- **Manejo:** Cuando ocurre una trampa, el procesador interrumpe inmediatamente la ejecución normal, guarda el estado y salta a un manejador específico.

En resumen, las interrupciones son eventos externos que requieren atención del sistema operativo, mientras que las trampas son eventos internos que indican condiciones anómalas durante la ejecución de un programa. Ambos mecanismos permiten al procesador cambiar temporalmente su flujo de ejecución para manejar situaciones específicas.
