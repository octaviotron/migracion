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

_La libertad de ejecutar el programa como se desee, con cualquier propósito_ (https://www.gnu.org/philosophy/free-sw.es.html)

Llamada "libertad de uso", pues es la que garantiza que todo software que tenga una licencia libre permite a sus usuarios ejecutar el código sin restricciones.

**Sin Restricciones Geográficas**

En algunos casos, el software que no es libre contiene cláusulas en sus licencias que impiden o penalizan el uso de sus programas en determinadas ubicaciones goegráficas. Por ejmplo, si analizamos las condiciones de uso de los productos de la empresa Oracle, podremos ver que su uso está prohibido en algunos países,  específicamente la Base de Datos Oracle 10g dice explícitamente antes de aceptar los términos de la licencia "I am not a citizen, national or resident of, and am not under the control of, the government of: Cuba, Iran, Sudan, Iraq, Libya, North Korea, Syria, nor any other country to which the United States has prohibited export."

<img src='/imgs/oracle01.png' width='400'>
<img src='/imgs/oracle02.png' width='400'>

**Sin Restricciones por Cantidad de Usuarios**

Un programa Libre permite que cualquer cantidad de usuarios lo ejecuten simultáneamente, mientras la capacidad del computador lo permita y mientras el código esté hecho para aceptar esta funcionalidad. Muchos programas privaivos (pudiésemos afirmar que casi todos) limitan mediante sus licencias y mediante algoritmos internos del código que se pueda disfrutar de sus funcionalidades desde múltiples instancias o clientes. Por ejemplo, el producto "Maximo" de la empresa IBM dice en su acuerdo de licencia: "Licensee's ownership of Express Use Concurrent User Licenses cannot exceed a ratio of 8 licenses to 1 Authorized User License of Maximo Asset Management or Industry Solution."

<img src='/imgs/ibm01.png' width='400'>

**Sin Restricciones por tipo de Hardware**

En muchos casos el Software que no es libre limita su uso al tipo de hardware o "arquitectura" en donde puede ser o no ejecutado. Esto es, hay que adquirir el producto para un tipo específico de procesador en el cual se ejecutará y no es posible poder usarlo en una distinta, incluso si el código del programa pudiese hacerlo, ya que en muchas ocasiones se provee un producto que está restringido para una u otra arquitectura. Como ejemplo, tenemos los productos de la empresa Microsoft, cuyo Sistema Operativo Windows 10 dice en su acuerdo de licencia: "If when acquiring the software you were provided with multiple versions (such as 32-bit and 64-bit versions), you may install and activate only one of those versions at a time."

<img src='/imgs/microsoft01.png' width='400'>

**Otras Limitaciones de Uso**

Tanto las descritas anteriormente como cualquier otra posible limitación es contraria a la filosofía del Software Libre. En algunos casos hay personas u organizaciones que desarrollan programas en cuya licencia se pide que no sea usado para fines comerciales. Esta condición restringe que las empresas o los fines privados puedan tener las mismas libertades que otras entidades, tanto públicas como privadas, lo cual además afecta negativamente la posibilidad de obtener ganancias económicas mediante el uso de tecnología ética y justa, como la es el Software Libre.


## Libertad 1

_La libertad de estudiar cómo funciona el programa, y cambiarlo para que haga lo que usted quiera (libertad 1). El acceso al código fuente es una condición necesaria para ello._ (https://www.gnu.org/philosophy/free-sw.es.html)

En realidad esta libertad son dos libertades:

* Estudiar el Código Fuente del programa
* Realizar Modificaciones al Programa

### Estudiar el Código

Una de las libertades más importantes para cualquier persona que desee aprender o profundizar su conocimiento en informática y en computación.

Pongamos esta situación como ejemplo:

_En una universidad se está impartiendo una clase para la asignatura de un "Doctorado en Sistemas Operativos". El profesor está explicando que cada programa ejecutado tiene un identificador de usuario (UID) y que éste está vinculado al ámbito de ejecucuión del usuario que lo invoca y por tanto genera un nuevo proceso en el sistema. En su exposición muestra que es posible que ese UID pueda cambiar para obtener privilegios especiales, de manera de poder acceder a componentes que de otra manera estarían restringidos. En ese momento un participante del curso levanta la mano y al serle otorgado el derecho de palabra pregunta:_

_- Profesor, ¿cómo es el algoritmo y rutinas del sistema para cambiar en tiempo de ejecución un UID sin que se rompa el proceso?_

_Si el profesor es sincero, sólo pudiera decirle:_

_- Para responder esta pregunta hace falta tener el código fuente de la parte del Sistema Operativo encargado de esta función. Por lo tanto, no puedo aclararte la duda. Es mas: si tuviese por alguna razón acceso a esa información, estaría impedido legalmente de compartirte mi conocimiento._

Estea situación nos lleva a varias reflexiones sobre esta libertad:

**Atrofio Profesional**

El ejemplo que se ha escogido para ilustrar el problema de un software que no es libre, deliberadamente sucede en un ambiente de altos estudios universitarios, lo cual evidencia una preocupante carencia de acceso a la información necesaria para que un profesional pueda ampliar su nivel profesional. Esto sucede de igual forma para cualquier persona que desee aprender y ser experto (en este ejemplo) en Sistemas Operativos, pero aplica a cualquier otra área de conocimiento donde se impide estudiar cómo funciona técnicamente un producto tecnológico.

El Software Libre permite acceso al código fuente de todos y cada uno de sus programas y por tanto no genera el paradigma anteriormente descrito. Si alguien quiere entender el funcionamiento de cualquier componente de software, sólo debe leer el conjunto de instrucciones relacionadas con la funcionalidad de la cual desea saber cómo está compuesto su algoritmo o su lógica.

**Auditabilidad del Software**

Todo programa informático puede contener código malicioso. En su estructura pueden existir rutinas que vulneren la seguridad de los sistemas donde se ejecutan o la privacidad de los usuarios que lo usan, pueden abrir puertas traseras ocultas o tener interfaces no documentadas que permitan ejecutar remotsmente código arbitrario.

La única forma de saber si un software tiene o no estas funcionalidades dañinas, es leyendo su código fuente para asegurarse que no existan. Si no se tienen esas fuentes, es decir, si lo único que se posee es un binario ejecutable, no se puede determinar directamente la presencia de estas rutinas maliciosas, o al menos sólo mediante la ingeniería inversa se pudiesen detectar, pero este método es muy difícil de aplicar y muchas veces arroja resultados imprecisos. Si el programa es parte de un sistema complejo, la dificultad aumenta hasta niveles donde es prácticamente imposible determinarlo con certeza y certificar o no la seguridad del software.

Lo mismo aplica para programas encargados de "asegurar" comunicaciones, aplicando métodos de cifrado que dicen ser confiables, pero que en la práctica desvían o registran secretamente todas las conexiones y datos transmitidos. Si no se conoce el código fuente sólo es posible tener la "fe ciega" de que los sistemas realmente proveen blindaje a la privacidad que ofrecen estos productos.

### Realizar Modificaciones al Programa

Si un usuario (persona, organización, empresa o institución) tiene un programa en Software Libre y por tanto cuenta con acceso al código fuente de los ejecutables que corren en sus sistemas, puede aplicarle mejoras o añadirle funcionalidades adicionales.

Veamos los principales beneficios de esta libertad:

**Corrección de Problemas**

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


## Libertad 2

_La libertad de redistribuir copias para ayudar a otros._ (https://www.gnu.org/philosophy/free-sw.es.html)

Esta libertad nos permite hacer copias de un programa y dárselas, con o sin costo a cambio, a cualquier persona.

**Compartir es Bueno**

Cuando somos niños nos enseñan que es bien visto compartir con nuestro prójimo. Cuando practicamos deportes en equipo aprendemos que es mejor para el bien común compartir la ventaja obtenida. Permanentemente en nuestra formación como individuos participamos en dinámicas grupales para resolver problemas o completar tareas donde hacemos consciente lo provechoso y útil que es la cooperación.

Ahora bien, cuando llegamos al campo científico o profesional nos encontramos con que hay tendencia a que se nos aconseje hacer lo contrario y ocultar nuestros logros, bajo la errónea premisa de sacar provecho a nuestro esfuerzo individual y no permitir que otros puedan beneficiarse de algún descubrimiento o idea.

Antes del Siglo XX, todo descubrimiento o estudio publicado. Cuando un científico llegaba a un descubrimiento lo primero que hacía era hacerlo del conocimiento para toda la comunidad, lo cual además de otorgarle reconocimiento, hacía posible que otros expandieran su hallazgo o basado en él, encontraran otras aplicaciones o implicaciones gracias a esa publicación. Después del establecimiento de las patentes esta práctica se redujo a pocas comunidades científicas y se creó un ecosistema que mercantilizó y limitó el intercambio de ideas y la construcción colectiva del saber. 

Si tienes una fruta y alguien te pide que la compartas, cada uno obtendrá y podrá comerse una fracción. Si tienes una idea y la compartes, todos tendrán esa idea y podrán multiplicarla con su aporte.

**Libertad y Gratuidad**

A veces es interpretada de manera errónea al afirmar que "el Software Libre es gratis". En inglés "Software Libre" se dice "_Free Software_" y la palabra "_free_" tiene en ese idioma dos acepciones: significa "libre" y significa "gratis". En español no es necesario contextualizar el término para saber que se habla de libertades y no de gratuidad.

Comunmente el Software Libre puede recibirse gratuitamente: la mayoría de las versiones modificadas del Sistema Operativo GNU/Linux (llamadas distribuciones) y casi todos los componentes y programas que vienen instalados o se pueden añadir desde el manejador de paquetes (conocido como "tienda virtual" en otros sistemas operativos) son libres y son gratuitos. 

Lo anterior no quiere decir que sea obligatorio regalar un software desarrollado al cual se le haya colocado una licencia libre. El fundador del movimiento de Software Libre (Richard Stallman) vivió muchos años de vender GNU EMACS, un editor extensible que él desarrolló. La gran mayoría de las distribuciones de GNU/Linux se pueden descargar, copiar y vender. Cualquier persona puede tomar una distribución de GNU/Linux, realizarle modificaciones y venderla o puede ofrecer servicios profesionales por adaptarla y entregar como producto una copia modificada.

Algunas modificaciones del Sistema Operativo GNU/Linux contienen componentes privativos que pueden restringir esta libertad, por ejemplo "SuSe Enterprise" y "RedHat Enterprise" sólo se pueden obtenerse e instalarse habiendo firmado un contrato y pagado un costo asociado. Esto no contradice ni rompe las licencias de todos los programas libres contenidos en estos productos. Todos los programas libres contenidos en estas distribuciones "no gratuitas" siguen siendo libres y aquellos con "copyleft" que han sido modificados tienen su código fuente disponible.

Para mayor información sobre la diferencia entre Software Libre y Software Privativo puede ver: COLOCAR VINCULO AQUI

**El término "Software Pirata"**

Con frecuencia se lee o escucha que un programa copiado sin autorización del desarrollador es un acto de "piratería" y se le llama una "copia pirata". Es incorrecto usar este término, veamos por qué:

Copiar un programa y regalárselo a otra persona es una acción de solidaridad y es un gesto de "buen vecino". Asaltar y robar un barco es algo malo y quienes lo hacen se llaman "piratas". Comparar el acto de compartir con asaltar un barco es una trampa semántica que debemos advertir y evitar.

Cuando tenemos un programa privativo y alquien nos lo pide, podemos hacer dos cosas y ambas están mal:

* Le damos la copia. Esto hace que se viole un acuerdo de licencia y por tanto se esté cometiendo una falta que en muchos casos puede ser catalogada como delito en las leyes que regulan las marcas y las patentes.
* Le negamos la copia. Esto es una acción de egoísmo y falta de solidaridad. Si quien nos pide la copia es un familiar querido o un buen amigo es un acto que será visto muy negativamente.

Alguna de estas dos opciones decidiremos tomar. Ambas son malas. Escogeremos la que nos parezca menos mala, pero eso no la hace buena. El Software Libre no da este problema moral, siempre será posible regalar la copia (o venderla) sin que acaree faltas a la ley o a la solidaridad social.

## Libertad 3
_La libertad de distribuir copias de sus versiones modificadas a terceros (libertad 3). Esto le permite ofrecer a toda la comunidad la oportunidad de beneficiarse de las modificaciones. El acceso al código fuente es una condición necesaria para ello._ (https://www.gnu.org/philosophy/free-sw.es.html)

Comencemos describiendo esta libertad usando un ejemplo comparativo:

_En una familia, hay un tío que es repostero y hace unas tortas deliciosas. Cada vez que la familia se reúne el tío lleva hecha una torta que a todos agrada y siempre le piden que lleve. Cuando le piden la receta el les dice que es un secreto y que quiere que sólo él sepa cómo hacer un postre tan delicioso. La familia necesita que él haga siempre la torta y que pueda llevarla para poderla disfrutar. Cuando el tío no puede ir o está indispuesto la familia no puede compartir ese gusto._

_En otra familia, quien hace las mejores tortas es la abuela. Ella unas horas antes de las reuniones familiares prepara en la cocina su deseado postre junto con quienes le quieran acompañar y goza enseñando a los mas chicos y a todos los demás su receta. Con los años dos de sus hijos y una nieta han aprendido su técnica y suelen traer en esas ocasiones sus tortas y comparten entre ellos las modificaciones que le hacen a la receta de la abuela._

Se necesita poca o ninguna explicación adicional sobre la moraleja que nos deja esta narración. 

La libertad 3 es la que permite e incentiva a que quien quiera pueda publicar una versión propia de un programa libre, al cual se le pudo haber mejorado el desempeño, ampliado características, agregado funciones o proponen una forma completamente distintta de presentar el aspecto visual de su interfaz gráfica. 

Es por esto que existen tantas distribuciones y hay tanta diversidad de programas y modificaciones de estos programas para las tareas que realizamos con nuestra informática. Es raro encontrar que en Software Libre hay un solo programa para realizar una tarea, cualquiera sea y cuando se desarrolla uno por primera vez (ya sea que antes no se había hecho o que responde a trabajar con tecnologías de reciente data) en poco tiempo se hacen versiones modificadas y posteriormente otros desarrollos con lenguajes o herramientas de programación distintas aparecen.

En el caso de las distribuciones del Sistema Operativo GNU/Linux, existen junto a las más populares y de uso general, infinidad de versiones modificadas para ámbitos específicos.

## Ninguna Libertad es Obligatoria

Las 4 libertades son opcionales para los usuarios, no obligatorias.

* Si tienes un programa de Software Libre puedes ejecutarlo para cualquier propósito y en cualquier parte del mundo en cualquier hardware donde pueda funcionar. Si no lo deseas no lo usas.
* Puedes aprender estudiando el código fuente y puedes hacerle modificaciones a tus programas, sólo si lo necesitas o deseas hacerlo.
* Puedes hacer copias del programa y puedes vender o regalar esas copias, no estás obligado a hacerlo.
* Puedes redistribuir las mejoras que le hagas a tus programas, sin embargo puedes mantenerlas para tí y no publicarlas.


**Casos Insignes (Pendiente por redactar)**
 
* Historia Netscape - Mozilla - Firefox - Iceweasel
* Caso Xfree86 - Xorg
* Evolución StarOffice - OpenOffice - LibreOffice
* Modelo Blender y Ardour






El Software que no es Libre se le llama “Privativo” porque priva a los usuarios y usuarias de esas libertades.

Llamar al software que no es libre “Software Propietario” puede ser engañoso, pues Software Libre tiene también sus propietarios y las licencias libres defienden sus derechos de autor; estos autores, los desarrolladores de Software Libre, deciden que tú también puedes usarlo, copiarlo, estudiarlo y compartir cualquier modificación.

El Software que no es Libre puede contener alguna de estas condiciones no deseadas:


*  Restricción de funciones para el usuario: El programa tiene funciones bloqueadas o impide al usuario acceder a ellas.
*  Extracción de datos privados: sin autorización el código de un programa privativo puede acceder a datos en el sistema y enviarlos a alguna entidad o voluntad externa.
*  Apertura de puertas traseras: un programa privativo puede permitir la ejecución de instrucciones remotamente, vulnerando la seguridad del sistema y pudiendo añadir otras funciones para espionaje o vigilancia.

No todo el Software Privativo tiene estas características indeseadas, pero pueden ocultarlas y es casi imposible y muy difícil distinguir cuál programa privativo las oculta y cual no. Para mayor información se pueden revisar el reporte de estas funciones [detectadas y demostradas](https///www.gnu.org/malware/) por la comunidad del Proyecto GNU.

