# Migrando a Software Libre

Por: Octavio Rossell Tabet, CC-BY-ND `<octavio@gnu.org.ve>`

Según su [definición oficial](https///www.gnu.org/philosophy/free-sw.es.html), "Software Libre" es aquel programa el cual respeta las libertades de los usuarios y otorga a quien lo usa el control de su informática y la privacidad de sus datos. Cuando se dice “usuarios”, el término se aplica indistintamente tanto a individuos, como a grupos (instituciones, organizaciones o empresas) y países.

Estas libertades que se respetan a esos “usuarios” son:

*  Ejecutar el programa, sin restricción geográfica, sin condicionar en su licencia la cantidad de usuarios o el tipo de hardware, sin condicionar el propósito el cual puede ser comercial o no, profesional o no.
*  Estudiar el código y realizar modificaciones, lo cual garantiza auditar el programa y no depender de la autorización del desarrollador para mejorarlo o adaptarlo.
*  Compartir y copiar los programas, regalando las copias o cobrando por ellas.
*  Libertad de redistribuir copias mejoradas de los programas, con o sin costo.

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
