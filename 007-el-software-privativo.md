# El Software que no es Libre

Un programa informático es Software Libre cuando cumple con las 4 libertades escenciales descritas anteriormente.

El Software que no es Libre se le llama “Privativo” porque priva a los usuarios y usuarias de esas libertades.

Llamar al software que no es libre “Software Propietario” puede ser engañoso, pues Software Libre tiene también sus propietarios y las licencias libres defienden sus derechos de autor; estos autores, los desarrolladores de Software Libre, deciden que tú también puedes usarlo, copiarlo, estudiarlo y compartir cualquier modificación.

### El Software 99.9% Libre no existe en la práctica 

Algunas veces es visto como poco importante incluir o mezclar componentes privativos con Software Libre y por tanto creer que por constituir el 0.01% o menos del total del software esto impacta en igual magnitud despreciable de influencia en los beneficios, seguridades y libertades del usuario.

Un binario colocado estratégicamente dentro de un sistema operativo, puede albergar una rutina muy simple que permita la ejecución de instrucciones llamadas o recibidas remotamente. Por ejemplo, un driver que por ser un componente del kernel tendrá permisos de ejecución de bajo nivel y puede abrir un puerto donde queda a la escucha de instrucciones remotas. Este binario pudiese ser tan pequeño como sea posible, de manera que al ejecutarse por primera vez instale el resto de sus funciones desde una URL y sea tan grande y complejo como se quiera.

Asimismo un componente privativo del menor tamaño posible que se pueda construir, puede tener en su licencia condiciones que limiten, anulen o impidan las libertades en el resto del sistema. Por ejemplo, un ejecutable fundamental para el funcionamiento del sistema que tenga restricciones de copia o que sólo funcione actualizando una suscripción.

# El problema del Software Privativo

El Software que no es Libre puede contener alguna de estas condiciones no deseadas:

* Restricción de Funcionalidades
* Anulación de la Privacidad
* Creacion de Puertas Traseras

No todo el Software Privativo tiene estas características, pero pueden ocultarlas y es casi imposible y muy difícil distinguir cuál programa privativo las oculta y cual no. Para mayor información se pueden revisar el reporte de estas funciones [detectadas y demostradas](https///www.gnu.org/malware/) por la comunidad del Proyecto GNU.

Veamos en detalle a cada una:

### Restricción de Funcionalidades

Un programa privativo contiene o puede contener algunas funciones que no le sean mostradas o no puedan ser accedidas por el usuario, limitando al usuario de ejecutarlas.

Un ejemplo de esto se aprecia en los dispositivos móviles con el Sistema Operativo Android, donde no se permite desinstalar aplicaciones, siendo estas componentes adicionales y no fundamentales para el funcionamiento del resto de las funciones del equipos. En muchos casos esas aplicaciones exportan datos que el usuario no ha autorizado para compartir a terceros.

Otro caso ilustrativo de esta privación al usuario es el de las interfaces administrativas para la configuración de dispositivos de hardware que teniendo la capacidad para proveer algunas funcionalidades, estas deliberadamente se omiten en las opciones del menú. Por ejemplo la imposibilidad de acceder a los parámentros de regulación de ancho de banda o calidad de sericios (QoS) en enrutadores WiFi o la inexistencia de una opción que habilite la virtualización en el CPU de los computadores.

### Anulación de la Privacidad

Un software puede contener funciones y rutinas que comparta cualquier tipo de información almacenada en la memoria o el sistema de archivos. Esto incluye desde el registro de las páginas visitadoas y de las aplicaciones ejecutadas, incluyendo hora, ubicación geográfica precisa y tiempo de uso. De igual forma puede compartir libretas de direcciones, números marcados (en el caso de los teléfonos celulares), audios grabados y recibidos, textos, imágenes, archivos multimedia e incluso el registro de todas las teclas presionadas en el teclado.

Si no se puede estudiar el código fuente no es posible saber si almacena capturas o registra en video lo que está en la pantalla mientras el usuario tenga actividad reciente.

### Puertas Traseras

Un programa privativo puede permitir la ejecución de instrucciones remotamente sin informar al usuario, logrando con esto vulner ejecutar funciones para espionaje o vigilancia, añadiendo compomentes ocultos que aumenten la capacidad de control remoto o eliminando arbitrariamente datos como archivos o cinfiguraciones. 

Un caso famoso es el lector de documentos "Kindle" de Amazon, el cual puede borrar en cualquier momento cualquier libro que tenga almacenado el usuario. La vez que esto se demostró les fue eliminado el libro "1984" de George Orwell a todos los usuarios que lo tenían en su dispositivo, lo cual añade una conición de hecho paradójico tomando el cuenta el contenido metafórico de esa obra.

Fuente: https://www.npr.org/templates/story/story.php?storyId=106989048

Cabe añadir la observación que ese mismo producto de Amazon también contiene una restricción de funcionalidades, explicada anteriormente en este capítulo, pues impide a los usuarios intercambiar libros, lo cual es y ha sido siempre una práctica común y natural entre los lectores.


# ¿Open Source? ¿Código Abierto?

Hay una definición de Software llamada "Open Source", en español "Código Abierto", que está tan intrínsecamente vinculado como fundamentalmente diferenciado de lo que es el Software Libre.

Esta vinculación hace que pueda ser indistinto que un programa cuyo desarrollador identifique como Software Libre pueda también en muchos casos coincidir con la definición de Open Source sin generar contradicciones legales ni formales. Por ejemplo un software desarrollado y publicado por el consorcio que promueve el Open Source puede tener una licencia como la "GNU GPL" y a su vez un miembro de la Fundación del Software Libre puede publicar un código fuente bajo la licencia "BSD Modificada".

La diferencia fundamental, de la cual se derivan otras tanto determinantes como sutiles, consiste en que el Software Libre habla explícitamente de Libertad y de Derechos Fundamentales del Usuario, mientras que el Open Source cuidadosamente evita estos temas y reduce su definición y ámbito con términos relacionados con aspectos meramente técnicos con la aspiración de acercarse con mayor facilidad al lenguaje y las condiciones del mercadeo, generando algunas debilidades en el control de los usuarios a quienes se les acerca y confunden los productos definidos como "Open Source" con el Software Privativo suavizando algunas diferencias y por tanto confiscando algunas de las libertades esenciales que mantiene y defiende el Software Libre.

Para una definición y explicación más completa y detallada, visitar https://www.gnu.org/philosophy/open-source-misses-the-point.es.html



