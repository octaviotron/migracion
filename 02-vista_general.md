# Vista General: lo fundamental en una migración

Migrar a Software Libre requiere tiempo y esfuerzo, sobre todo en organizaciones con sistemas complejos que resguardan datos sensibles y donde es posible que existan procesos que se realizan usando piezas de software antiguas, desatendidas (sin soporte) o poco documentadas y donde algunas configuraciones "cableadas" (definidas estáticamente) pueden complicar algunos cambios.

Cualquiera sea el caso, es posible optimizar mucho los esfuerzos si se tiene un plan con etapas y objetivos definidos y sólo será posible una buena migración si se realiza ordenadamente. A groso modo, este documento plantea que se consideren las siguientes etapas, posteriormente descritas con detalle:

**1) Creación de un laboratorio de pruebas**: 

Antes de cualquier actividad de migración, se recomienda disponer un área destinada al trabajo de migración, con las condiciones mínimas necesarias para llevar a cabo las distintas tareas de estudio, prueba y documentación, identificado como "Laboratorio de Migración" (o algún nombre similar).

Además de facilitar y motivar al equipo de trabajo, pues eso ayuda a sentir pertenencia, un espacio definido explícitamente para realizar las múltiples actividades optimiza la fuerza de trabajo y la concentración de esfuerzos, la disponibilidad de herramientas y equipos donde se puedan realizar pruebas y estudiar resultados fuera del ambiente de producción.

**2) Levantamiento de información**: 

La primera y fundamental actividad a realizar en el Laboratorio de Migración, es conocer con la mayor cantidad de detalle posible la arquitectura, la topología y las relaciones (muchas veces muy entreveradas) de los sistemas que actualmente opera en las estaciones de trabajo. 

También será necesario contar con información detallada del hardware sobre el cual corren los sistemas y estudiar documentación que especifique su funcionamiento en GNU/Linux.

Finalmente, pero no menos importante, se aconseja conocer con qué talento humano se cuenta para emprender el proceso de migración, conociendo las habilidades existentes para poder integrarlas de forma coherente en el proceso.

**3) Evaluación de Alternativas**: 

Los componentes de Software Privativo a migrar (sistemas operativos, servicios y herramientas) tendrán con toda seguridad varias alternativas libres con las cuales podrá sustituirlos. No es trivial escoger entre las opciones pues unas tendrán factores que en mayor o menor grado se adapten o integren con las características particulares que tiene cada organización.

Se debe usar un método de selección que evite la arbitrariedad, pues la alternativa que "gusta mas" no necesariamente y no siempre es aquella que convendrá escoger para adaptar y hacerla funcionar por varios (a veces muchos) años. Esa alternativa preferida debe compararse para validar que es la más apropiada o para encontrar que otra supera o se integra mejor.

Este documento propone un método de evaluación cuya aplicación orientará la toma de decisiones y dará consistencia y fundamentos técnicos para cualquier caso donde se necesite más que la subjetividad para determinar la pertinencia y mayor coherencia al determinar que un componente tecnológico es el apropiado para integrarse con el resto del sistema. 

Este método propuesto sirve para escoger un programa, un dispositivo, un servicio o cualquier elemento que requiera ser seleccionado entre varias opciones similares.

**4) Diseño de Arquitectura**

Defina y de ser posible dibuje el mapa completo antes de migrar. Defina las rutas y sus pasos e incluya la mayor cantidad de detalle de cada componentes. 

Habiendo estudiado la topología y arquitectura de los servicios, escritorios y herramientas necesarias, dibuje el mapa donde se pueda ubicar cada uno de los componentes que implementará en la migración.

Reconozca e identifique los sujetos a migrar (sistemas operativos, herramientas, servicios...) y las relaciones que lo vinculan con el resto de la plataforma tecnológica.


**5) Plan de Ejecución**

Necesitará trazar la ruta que define el orden de los pasos en la migración. El nivel de complejidad de los servicios existentes obligará a tener cubiertas algunas dependencias antes de poder avanzar algunos procesos, como la integración con sistemas de autenticación y autorización de recursos en red. En muchos casos habrá convivencia con sistemas que no serán migrados, al menos no durante los procesos planificados en el plan, por lo cual se debe incluir en el plan los pasos a seguir en estos casos.

En este plan se define qué se hace, cuándo (antes, durante o después de qué), cómo (manuales y recetas) y dónde (en cuáles equipos, servicios o clientes) se realizarán actividades y en cuántas etapas.

**6) Pruebas de Migración**

Pruebe bien de Implantar. Haga esto para todos y cada uno de los elementos o cambios que incluya durante todas las etapas de migración. Evite actualizar sin probar suficientemente en un ambiente espejo del productivo y nunca use ningún software sin verificar su funcionamiento y comportamiento.

Encontrará posteriormente consejos para separar en distintos estados cada tecnología a implementar o cada cambio a realizar, en resumen, una etapa experimental (desarrollo) donde toda prueba o cambio es posible para evaluarse, una de observación y ajustes (certificación) donde las decisiones y recetas acordadas se estabilizan y aseguran y una de producción donde los únicos cambios posibles deben haber pasado estrictamente por las dos etapas anteriores. 

Esto asegurará la continuidad operativa y dará mayores certezas sobre qué componentes y configuraciones son idóneas, seguras y estables para su continuidad operativa.

**6) Implementación en Producción**

Escale progresivamente. Cuando implemente un nuevo sistema o componente, observe su funcionamiento en un numero inicialmente reducido de casos. Migre siempre un conjunto reducido y manejable de estaciones de trabajo o usuarios del sistema que le garanticen estabilidad suficiente para ir ampliando el radio de acción.

Migre primero lo más fácil. El proceso de migración debe comenzar por la migración de sistemas que tengan un bajo impacto operativo en el funcionamiento total de la organización. En muchos casos un buen número de las computadoras de una red realizan actividades en programas comunes que migrados a Software Libre no representarán mayor diferencia de rendimiento y funcionalidad en sus labores cotidianas ni de la continuidad operativa de la organización.

**7) Documentación**

Documente todo: de este factor dependerá en gran medida la optimización de los esfuerzos en la migración. En un sistema (una WiKi es uno de ellos) se deben ir recopilando todas las informaciones pertinentes a los procesos, logros, resolución de problemas y datos que sean de relevancia para la generación de la documentación final del proceso. Si esto se cumple, es decir, si se documentan todos los procesos y las actividades realizadas se tendrá un espacio donde se puedan consultar las configuraciones, topologías, soluciones y demás datos importantes para el futuro mantenimiento o escalabilidad de los sistemas de información de la organización migrada. 

