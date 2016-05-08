# microservices

### Microservicio

Si bien no existe una definición precisa de este estilo arquitectónico, hay ciertas características comunes como son: se ejecuta dentro de su propio proceso, provee mecanismos de comunicación livianos, el despliegue es automatizado, Smart end points, es independiente del lenguaje y de los datos. Además es importante decir que muchas de las características de diseño de estos sistemas se basan en lo principios de diseño de Unix.

### API

Un grupo de microservicios convertidos en una API (Application program interface) puede definirse como un sistema distribuido ya que debido a que cada uno de estos puede ser desplegado en una computadora diferente y seguir brindando al usuario la impresión de estar interactuando con un solo sistema.

Bajo acoplamiento y alta cohesión [Wikipedia](https://en.wikipedia.org/wiki/Cohesion_%28computer_science%29)

### Origen de los microservicios

Para entender por qué existen los microservicios hay que primero entender la frustración de los desarrolladores de servicios y aplicaciones monolíticas actuales, por lo que en este punto es necesario describir un monolito y encontrar los “puntos de frustración”.
Un monolito es el estilo arquitectónico más común para construir aplicaciones, que consta básicamente de 3 capas: una interfaz de usuario que generalmente corre en un navegador web, una capa de datos generalmente en un modelo relacional y una capa de aplicación que corre generalmente en un servidor de aplicaciones encargada de recibir las peticiones que provienen del navegador para realizar transacciones del negocio que persisten en el sistema de base de datos. Dicho esto cuales son entonces los “puntos de frustración” de este estilo arquitectónico:



* Un cambio en una sola función requiere el despliegue total de la aplicación “monolito”.
* Incrementar las capacidades de cómputo para una sola función requiere ampliar las capacidades para todo el monolito lo cual lo hace más complejo y más costoso.
* Una falla de un módulo o función significa una falla para todo el sistema, por lo que todos los atributos de calidad deben ser garantizadas para todos los componentes, módulos, funciones… del monolito (por ejemplo la autenticación), esto es especialmente frustrante máxime cuando algunos módulos o funciones no requieren ser asegurados o no requieren estar 99.8% de disponibilidad.
* Un monolito pone todas sus funcionalidades en un solo proceso, generalmente el proceso con el que se inició el servidor de aplicaciones, por lo que si falla este proceso fallaran todas las aplicaciones. Una solución para este caso que hoy se usa en la industria es crear clusters de estos servidores, pero piense en el costo de esto.

![Monolito](http://imagesnel.appspot.com/microservicios/monolithic.png)

En contraste una aplicación con microservicios consta de un conjunto de funcionalidades distribuidas en múltiples servicios separados e independientes de la infraestructura, los datos, las comunicaciones y los lenguajes de programación. Esto significa que:

* Cambiar una función solo impacta a esa función, por lo que solo requiere reiniciar o redesplegar esa función, las demás funciones siguen corriendo sin interrupción.
* Si un a función requiere mayores capacidades de computo (RAM, CPU, …) pues solo esta función recibe el incremento de esta capacidad, las demás no. Esto hace que el cambio sea más rápido, menos complejo y mucho menos costoso.
* Si una función falla, solo se debe trabajar en la recuperación de un microservicio, las demás funciones o microservicios no se ven afectados y siguen funcionando sin interrupciones. 
* Las calidades sistémicas que requiere un sola función solo se le proveen a esa función. Por ejemplo si una función requiere un nivel de disponibilidad crítico está y solo esté será puesta en una zona del data center especial y monitoreada con herramientas especializadas para garantizar su buen desempeño; esto permite optimizar el uso de lo recursos de computo, destinándolos  a las funciones que realmente los requieren.
* 
 [Continue leyendo sobre este tema en la wiki](https://github.com/nelsonmoreno/microservices/wiki)
