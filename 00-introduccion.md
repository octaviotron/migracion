# Migrando a Software Libre

**Introducción: Definición Ampliada de Software Libre**

Por: Octavio Rossell Tabet, CC-BY-ND `<octavio@gnu.org.ve>`

Según su [definición oficial](https///www.gnu.org/philosophy/free-sw.es.html), "Software Libre" es aquel programa el cual respeta las libertades de los usuarios y otorga a quien lo usa el control de su informática y la privacidad de sus datos. Cuando se dice “usuarios”, el término se aplica indistintamente tanto a individuos, como a grupos (instituciones, organizaciones o empresas) y países.

Estas libertades que se respetan a esos “usuarios” son:

*  Ejecutar el programa, sin restricción geográfica, sin condicionar en su licencia la cantidad de usuarios o el tipo de hardware, sin condicionar el propósito el cual puede ser comercial o no, profesional o no.
*  Estudiar el código y realizar modificaciones, lo cual garantiza auditar el programa y no depender de la autorización del desarrollador para mejorarlo o adaptarlo.
*  Compartir y copiar los programas, regalando las copias o cobrando por ellas.
*  Libertad de redistribuir copias mejoradas de los programas, con o sin costo.

Hagamos un análisis detallado de cada una de estas libertades:

## Libertad 0

Llamada "libertad de uso", pues es la que garantiza que todo software que tenga una licencia libre permite a sus usuarios ejecutar el código sin restricciones.

**Sin Restricciones Geográficas**

En algunos casos, el software que no es libre contiene cláusulas en sus licencias que impiden o penalizan el uso de sus programas en determinadas ubicaciones goegráficas. Por ejmplo, si analizamos las condiciones de uso de los productos de la empresa Oracle, podremos ver que su uso está prohibido en algunos países,  específicamente la Base de Datos Oracle 10g dice explícitamente antes de aceptar los términos de la licencia "I am not a citizen, national or resident of, and am not under the control of, the government of: Cuba, Iran, Sudan, Iraq, Libya, North Korea, Syria, nor any other country to which the United States has prohibited export."

![ c ](/imgs/oracle01.png | width=400)
![ c ](/imgs/oracle02.png | width=400)

**Sin Restricciones por Cantidad de Usuarios**

Un programa Libre permite que cualquer cantidad de usuarios lo ejecuten simultáneamente, mientras la capacidad del computador lo permita y mientras el código esté hecho para aceptar esta funcionalidad. Muchos programas privaivos (pudiésemos afirmar que casi todos) limitan mediante sus licencias y mediante algoritmos internos del código que se pueda disfrutar de sus funcionalidades desde múltiples instancias o clientes. Por ejemplo, el producto "Maximo" de la empresa IBM dice en su acuerdo de licencia: "Licensee's ownership of Express Use Concurrent User Licenses cannot exceed a ratio of 8 licenses to 1 Authorized User License of Maximo Asset Management or Industry Solution."

![ c ](/imgs/ibm01.png | width=400)

**Sin Restricciones por tipo de Hardware**

En muchos casos el Software que no es libre limita su uso al tipo de hardware o "arquitectura" en donde puede ser o no ejecutado. Esto es, hay que adquirir el producto para un tipo específico de procesador en el cual se ejecutará y no es posible poder usarlo en una distinta, incluso si el código del programa pudiese hacerlo, ya que en muchas ocasiones se provee un producto que está restringido para una u otra arquitectura. Como ejemplo, tenemos los productos de la empresa Microsoft, cuyo Sistema Operativo Windows 10 dice en su acuerdo de licencia: "If when acquiring the software you were provided with multiple versions (such as 32-bit and 64-bit versions), you may install and activate only one of those versions at a time."

![ c ](/imgs/microsoft01.png | width=400)

**Otras Limitaciones de Uso**

Tanto las descritas anteriormente como cualquier otra posible limitación es contraria a la filosofía del Software Libre. En algunos casos hay personas u organizaciones que desarrollan programas en cuya licencia se pide que no sea usado para fines comerciales. Aunque en principio este gesto altruista puede ser visto como noble, restringe que las empresas o los fines privados puedan tener las mismas libertades que otras entidades, tanto públicas como privadas, lo cual además afecta negativamente la posibilidad de obtener ganancias económicas mediante el uso de tecnología ética y justa, como la es el Software Libre.


## Libertad 1

En realidad esta libertad son dos libertades:

* Estudiar el Código Fuente del programa
* Realizar Modificaciones al Programa

### Estudiar el Código

Una de las libertades más importantes para cualquier persona que desee aprender o profundizar su conocimiento en informática y en computación.

Pongamos esta situación como ejemplo:

_En una universidad se está impartiendo una clase para la asignatura de un "Doctorado en Sistemas Operativos". El profesor está explicando que cada programa ejecutado tiene un identificador de usuario (UID) y que éste está vinculado al ámbito de ejecucuión del usuario que lo invovca y por tanto genera un nuevo proceso en el sistema. En su exposición muestra que es posible que ese UID pueda cambiar para obtener privilegios especiales, de manera de poder acceder a componentes que de otra manera estarían restringidos. En ese momento un participante del curso levanta la mano y al serle otorgado el derecho de palabra pregunta:_

_- Profesor, ¿cómo es el algoritmo y rutinas del sistema para cambiar en tiempo de ejecución un UID sin que se rompa el proceso?_

_Si el profesor es sincero, sólo pudiera decirle:_

_- Para responder esta pregunta hace falta tener el código fuente de la parte del Sistema Operativo encargado de esta función. Por lo tanto, no puedo aclararte la duda. Es mas: si tuviese por alguna razón acceso a esa información, estaría impedido legalmente de compartirte mi conocimiento._

Estea situación nos lleva a varias reflexiones sobre esta libertad:

**Atrofio del Profesionalismo**

El ejemplo que se ha escogido para ilustrar el problema de un software que no es libre, deliberadamente sucede en un ambiente de altos estudios univesritarios, lo cual evidencia una preocupante carencia de acceso a la información necesaria para que un profesional pueda ampliar su nivel profesional. Esto sucede de igual forma para cualquier persona que desee aprender y ser experto (en este ejemplo) en Sistemas Operativos, pero aplica a cualquier otra área de conocimiento donde se impide estudiar cómo funciona técnicamente un producto tecnológico.

El Software Libre permite acceso al código fuente de todos y cada uno de sus programas y por tanto no genera el paradigma anteriormente descrito. Si alguien quiere entender el funcionamiento de cualquier componente de software, sólo debe leer el conjunto de instrucciones relacionadas con la funcionalidad de la cual desea saber cómo está compuesto su algoritmo o su lógica.

**Auditabilidad del Software**

Todo programa informático puede contener código malicioso. En su estructura pueden existir rutinas que vulneren la seguridad de los sistemas donde se ejecutan o la privacidad de los usuarios que lo usan, pueden abrir puertas traseras ocultas o tener interfaces no documentadas que permitan ejecutar remotsmente código arbitrario.

La única forma de saber si un software tiene o no estas funcionalidades dañinas, es leyendo su código fuente para asegurarse que no existan. Si no se tienen esas fuentes, es decir, si lo único que se posee es un binario ejecutable, no se puede determinar directamente la presencia de estas rutinas maliciosas, o al menos sólo mediante la ingeniería inversa se pudiesen detectar, pero este método es muy difícil de aplicar y muchas veces arroja resultados imprecisos. Si el programa es parte de un sistema complejo, la dificultad aumenta hasta niveles donde es prácticamente imposible determinarlo con certeza y certificar o no la seguridad del software.

Lo mismo aplica para programas encargados de "asegurar" comunicaciones, aplicando métodos de cifrado que dicen ser confiables, pero que en la práctica desvían o registran secretamente todas las conexiones y datos transmitidos. Si no se conoce el código fuente sólo es posible tener la "fe ciega" de que los sistemas realmente proveen blindaje a la privacidad que ofrecen estos productos.

### Realizar Modificaciones al Programa

Si un usuario (persona, organización, empresa o institución) tiene un programa en Software Libre y por tanto cuenta con acceso al código fuente de los ejecutables que corren en sus sistemas, puede aplicarle mejoras o añadirle funcionalidades adicionales.

Veamos los principales beneficios de esta libertad:

**Corrección de Errores**

Un software puede contener rutinas que en ciertas condiciones puedan generar un comportamiento no deseado, ya sea arrojando resultados incorrectos, bloqueando el funcionamiento del programa o consumiendo recursos que atenten contra la estabilidad o desempeño de los sistemas donde esté siendo ejecutado.

Si hay acceso al código fuente es posible estudiar la lógica que afecta a los procesos que presentaran esta situación y por tanto corregirlos.

Pongamos el ejemplo de un desarrollador que coloca deliberadamente una rutina en un programa de contabilidad que produce un error desconocido un día antes de cerrar procesos importantes para el funcionamiento de quienes ejecutan el software, obligando a llamar a la empresa que les provee el soporte, quien en acuerdo con el desarrollador han pautado una forma injusta de obtener ganancias por su producto.

**Nuevas Funcionalidades**

Un sistema puede necesitar que sea añadida una nueva funcionalidad o que provea un conjunto adicional de recursos. Pongamos como ejemplo un caso cotidiando de la vida real:

Estamos usando un procesador de palabras para enseñar a niños a usar un computador en una escuela de un lugar del mundo donde se hable un idioma que sólo es hablado en esa localidad. Digamos que es una comunidad indígena que tenga lengua escrita. Muy probablemente estos niños tengan que dejar de usar su dialecto y usar en otro idioma las herramientas informáticas, con lo cual la tencnología estaría debilitando la preservación de su cultura.

Es muy probable que en esa situación el sistema no tenga los menúes y diálogos en su idioma. Si es un procesador de palabras hecho en Software Libre (LibreOffice, por ejemplo) no sólo es posible añadirle el soporte para su idioma (llamdado técnicamente "localización de lenguaje"), sino que además está documentado cómo hacerlo.

<img src='/imgs/libreoffice01.png' width='400'>

Otro ejemplo, mas común que el anterior, es tener un programa al cual queremos personalizarle el tema visual y adaptarlo para identificarlo con la imagen corporativa de nuestro proyecto, organización o empresa. Con Software Libre esto es muy Sencillo.

En los ejemplos anteriores, si nuestro software no es libre, la única forma de obtener el resultado deseado es contactar al desarrollador del programa, para lo cual será necesario obtener respuesta y que sea de su interés aplicar estos cambios, muy probablemente a cambio de una suma de dinero. En el caso del procesador de palabras podemos imaginar el proceso para que un producto como Microsoft Word añada esta característica.

**Localización**


* Estudiar el código y realizar modificaciones, lo cual garantiza auditar el programa y no depender de la autorización del desarrollador para mejorarlo o adaptarlo.




El Software que no es Libre se le llama “Privativo” porque priva a los usuarios y usuarias de esas libertades.

Llamar al software que no es libre “Software Propietario” puede ser engañoso, pues Software Libre tiene también sus propietarios y las licencias libres defienden sus derechos de autor; estos autores, los desarrolladores de Software Libre, deciden que tú también puedes usarlo, copiarlo, estudiarlo y compartir cualquier modificación.

El Software que no es Libre puede contener alguna de estas condiciones no deseadas:


*  Restricción de funciones para el usuario: El programa tiene funciones bloqueadas o impide al usuario acceder a ellas.
*  Extracción de datos privados: sin autorización el código de un programa privativo puede acceder a datos en el sistema y enviarlos a alguna entidad o voluntad externa.
*  Apertura de puertas traseras: un programa privativo puede permitir la ejecución de instrucciones remotamente, vulnerando la seguridad del sistema y pudiendo añadir otras funciones para espionaje o vigilancia.

No todo el Software Privativo tiene estas características indeseadas, pero pueden ocultarlas y es casi imposible y muy difícil distinguir cuál programa privativo las oculta y cual no. Para mayor información se pueden revisar el reporte de estas funciones [detectadas y demostradas](https///www.gnu.org/malware/) por la comunidad del Proyecto GNU.

## La "Resistencia al Cambio"

*Un miembro de la comunidad cuenta que en una de sus primeras migraciones, los usuarios se manifestaron molestias debido a las diferencias del navegador web (primeras versiones de "Mozilla", ahora conocido como "Firefox"), cuya costumbre de uso les chocaba ahora con el nuevo producto en Software libre. Hizo lo siguiente: le cambió el color del menú y el icono de Firefox e informó al próximo grupo al cual le tocó realizar el cambio que esa era la nueva versión de Internet Explorer, recién publicada. Los usuarios estaban muy animados y ninguno expresó desagrado ni resistencia para aprender a usarlo.*

En primer lugar esta historia relata cómo los usuarios tienen resistencia al cambio por y encima de cualquier mejora, así sea sustancialmente positiva, valoran mucho más la facilidad que les brinda la costumbre.

En segundo lugar y mas importante, este comportamiento en los usuarios señala que un proceso de migración no es algo meramente técnico y pragmático, pues puede ser factor influyente la simpatía o la voluntad de quienes operan los sistemas migrados.

Esto da lugar a la siguiente reflexión: Los programas y los sistemas se pueden cambiar con una instrucción pero la aprobación de los usuarios no.

## ¿Por qué Software Libre?

Quienes hayan intentado migrar, aunque sea una sola vez, podrán fácilmente llenar una lista con argumentos escuchados en contra del Software Libre, pero repasemos los factores que realmente sustentan y justifican adoptar esta tecnología:

**Ahorro por costos de licencias**

El argumento que con frecuencia se acostumbra a nombrar como primero, principal o de mayor importancia es el ahorro por costos de licencia. Paradójicamente, se sabe que en la práctica muchas veces el ahorro no es inmediato e incluso en las primeras etapas de una migración puede igualar estos costos. De hecho, para que una migración sea exitosa debe comprender presupuesto suficiente para integrar gente con el talento y la experiencia necesaria, puede requerir la asignación de equipos informáticos adicionales, deberá tener un espacio y talento humano dedicado a la actividad, así como el tiempo asociado a la investigación, el desarrollo, las pruebas y la implementación.

Lo cierto es que después de haber culminado el proceso inicial y ya se están migrando servicios y estaciones de trabajo, sí habrá un importante ahorro. Es importante recordar que algunos productos privativos obligan a la actualización de sistemas (con costos e impacto asociado) condicionando el soporte sólo para las versiones mas nuevas. Las tecnologías libres tienden a sostener el soporte y actualizaciones de seguridad por mucho tiempo y no desecha compatibilidad o vigencia de versiones anteriores para condicionar y obligar la renovación de sus licencias de uso.

**Seguridad Informática**

El Software Libre se ha ganado justamente fama de robusto, estable y seguro. Por estar disponible el código fuente de todos los componentes en el sistema operativo y por estar expuesto al estudio, escrutinio y auditoría pública, las fallas y vulnerabilidades rara vez se escapan a la observación. De igual modo el hallazgo de un error o brecha es agradecido por toda la comunidad e inmediatamente mejorado para todos, al contrario del software donde la evidencia de un fallo es negada y las personas con talento para detectarlas pueden ser perseguidas o castigadas.

El Software Libre no tiene "seguridad por oscuridad", frase usada para definir la práctica donde ocultar un error o vulnerabilidad intenta proteger al sistema de ser afectado, resultando en una de las principales causas de que existan y sean tan comunes las fallas y se terminan percibiendo los virus, troyanos y demás aflicciones como normales y comunes.

Asimismo, el Software Libre es sinónimo de *privacidad* puesto que se puede saber y constatar que el software no extrae información de los usuarios y servicios de la red para almacenarlos externamente sin autorización.

Respecto a *cifrado* de los datos, usado para proteger cuando se transmite o almacena información, los algoritmos de cifrado en los programas de Software Libre permiten igualmente auditoría pública para asegurar la fortaleza de las llaves e impedir formas de acceder universalmente mediante algún otro método oculto con fines de espionaje.

Finalmente, el Software Libre carece de *puertas traseras* ocultas que puedan ser activadas para instalar otros componentes adicionales que vulneran aún mas al usuario o que puedan afectar la operatividad o estabilidad al ser posible variar cualquier configuración o componente del sistema sin autorización.

**Flexibilidad, Adaptabilidad y Versatilidad**

El Software Libre permite sustituir cualquiera de sus componentes. Esto hace que se pueda construir un sistema a la medida.

Existe una frase que pudiera sonar soberbia, pero en la práctica es tan lapidaria como cierta: "con Software Libre uno no debe preguntar si se puede hacer tal o cual función, por el contrario se busca documentación sobre las distintas formas en las cuales es posible lograrlo".

**Interfaces Documentadas**

El Software Libre acostumbra a usar estándares internacionales para ofrecer **compatibilidad**. Cualquier programa o componente libre incluirá soporte para abrir o leer cualquier estándar libre, es decir, que las especificaciones de los formatos, protocolos e interfaces estén documentadas y públicamente disponibles para el correcto uso e intercambio de datos.

Muy frecuentemente se califica de incompleto o deficiente un programa en Software Libre por la imposibilidad de abrir un tipo de archivo, usar algún protocolo, comunicarse con un dispositivo o conectarse y acceder a algunos sistemas o servicios, cuando en realidad esto es debido a información técnica inexistente que impide programar funciones para procesar o integrar estos componentes privativos.

**Razones Legales**

En el caso venezolano, las instituciones públicas tienen un conjunto de leyes que ordenan el uso (exclusivo) de Software Libre en todos sus equipos informáticos y sistemas de información y comunicación. Esto es distinto para cada país y en el caso latinoamericano se puede ver la información que publica [FSFLA](https///www.fsfla.org/ikiwiki/legis/index.es.html) al respecto.

**Mas razones a favor**:

Para calificar apropiadamente un producto tecnológico es normal tomar en cuenta sólo cuestiones prácticas y "pragmáticas". Con el Software Libre hay factores asociados a los asuntos técnicos que añaden otros beneficios y ventajas.

Por ejemplo, la amplitud y pluralidad de software disponible es un factor especial cuando se trabaja con esta tecnología. Esta vastedad permite poder elegir entre las distintas formas de resolver una necesidad informática.

Por otra parte, frecuentemente un programa de Software Libre (o al menos los más populares) incluyen manuales de uso y documentación de funcionamiento, wikis, foros y canales de chat con los desarrolladores conectados en línea. Igualmente es común obtener junto al código o junto con los ejecutables el correo de contacto del desarrollador del programa.

Comprender que el Software Libre es antes que un producto tecnológico una forma de pensar la informática y que esa forma sea distinta al componerse de valores éticos que condiciona el resultado, en forma de software, hay argumentos técnicos que se sustentan en estos valores, como la buena voluntad, la generosidad y la solidaridad. Esto hace que no sea apropiado ni justo comparar al Software Libre con el privativo usando sólo criterios formales, tradicionales y de orientación ética distinta o inexistente.

### ¡Suficiente Filosofía! ¡Vamos a lo técnico!

Esta introducción teórica concluye con una frase del fundador del movimiento por el Software Libre:


    En los argumentos técnicos cuando se discute sobre una migración
    a Software Libre, “pragmatismo” usualmente significa:
    tomar decisiones a largo plazo por razones del corto plazo

                                                  Richard Stallman
