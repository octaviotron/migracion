
# Procesos fundamentales en una migración

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



# El Laboratorio de Pruebas

La creación de una unidad de trabajo dedicada al proceso de migración es fundamental y debe contar con las condiciones necesarias para poder disminuir al máximo posible los riesgos y el impacto de una migración. Es en este espacio donde toda tecnología en Software Libre se estudia, se analiza, se asegura y se prepara para ser usada en producción.

La construcción de esta unidad variará con la complejidad o el tamaño de una organización, pero se recomienda contar con estos elementos:


*  **Espacio Físico**: mesones de trabajo, sillas ergonómicas y abundantes y accesibles tomas eléctricas.

*  **Equipos Informáticos**: 
    * **Equipos de Escritorio**: Se sugiere contar con al menos un modelo de cada uno de las estaciones de trabajo o equipos portátiles que se usan a diario en la organización. Si el conjunto es muy heterogéneo, tenga al menos los modelos más frecuentes o una suficiente representación del parque de hardware de la organización.
    * **Servidores**: Será necesario crear muchas máquinas virtuales, por lo cual se debe procurar una suficiente capacidad de hardware para uno o varios hypervisores. Neceitará unas decenas de núcleos, la misma cantidad de GB de memoria RAM y espacio de almacenamiento equivalente a 20GB para cada una.
    * **Impresoras**:  al igual que en el caso de los equipos de escritorio, se requiere contar (al menos temporalmente en el momento de las pruebas) con un ejemplar de cada modelo de impresora existente en la red.
    * **Dispositivos de red**: Se requerirán Conmutadores (switches), Enrutadores (Routers) tanto cableados como inalámbricos y un conjunto suficiente de cables UTP de la categoría que se usa actualmente en la red.

*  **Conectividad**: Acceso a Internet, sin restricción de puertos de salida y de tener Proxy, debe ser transparente.

**Herramientas Informáticas**:


*  **Repositorio** actualizado diariamente de todas las distribuciones involucradas o si las desconoce al menos contar con repositorios de Debian Estable, Ubuntu LTS y CentOS

*  **Wiki** para documentar o compartir anotaciones y registros. Se recomienda [DokuWiki](https///www.dokuwiki.org/dokuwiki).

*  **FTP/NFS** donde puedan alojarse documentos, archivos, paquetes y demás recursos digitales

*  **Scrum** para organizar y visualizar las tareas. Se recomienda el uso de [Taiga](https///taiga.io/).

*  **Sistema de Tickets** para canalizar las peticiones de soporte o incidencia de bugs de los usuarios 

*  **Hypervisor** donde levantar Máquinas Virtuales para las distintas pruebas de servicios y escritorios. Se recomienda el uso de [Proxmox](https///www.proxmox.com/en/).

Se recomienda crear en el laboratorio distintos ambientes. Un ambiente significa en este contexto, cada conjunto de equipos, sistemas y direcciones de red separados y aislados, donde se puedan realizar pruebas y cambios sin afectar la continuidad operativa de la organización.

**Ambiente de Pruebas**:

Todo nuevo programa, herramienta, servicio o componente debe observarse primero en este ambiente. Acá se instalan alternativas nuevas que puedan sustituir algún otro software usado en la red. Igualmente en este ambiente es donde por primera vez se realizan actualizaciones o cambio de versiones (upgrade o downgrade) y todo cambio de configuración que se proponga es en esta instancia donde se aplica la primera vez.

Este ambiente sirve para observar el funcionamiento del cambio, mejora o novedad y asegurar que no manifiesta ningún comportamiento inesperado o no deseado. Por ejemplo, asegurar que el programa se pueda instalar sin problemas de dependencias o si requiere algún paquete extra, si el programa corre y se puede operar, si corre con estabilidad o se experimenta algún resultado inusual.

Asimismo en este ambiente es donde se realiza cualquier experimento, invento, innovación o verificación.

**Ambiente en Producción**:

El laboratorio debe tener acceso al conjunto de sistemas usados en los procesos diarios de la organización para poder comparar y estudiar cualquier componente de los sistemas o programas que se planean migrar.

**Ambiente de Estabilización**:

También llamado Q&A (//Quality Assurance// o Aseguramiento de Calidad) o "Ambiente de Certificación", es un estadio intermedio entre los experimentos y la estabilidad. En organizaciones de mediana o alta complejidad este ambiente es una copia del ambiente de producción, donde se pueden efectuar pruebas en condiciones similares al ambiente de producción pero con la seguridad de no afectar al mismo. 



# Levantamiento de Información

La primera tarea antes de formular cualquier plan consiste en conocer toda información que se tenga sobre el ecosistema donde se integran los sistemas o programas a migrar. Realizado el arqueo de lo que se pueda obtener, se debe proceder a conocer qué otra información es necesaria para proceder antes de migrar.

Los siguientes factores deben conocerse con el mayor detalle posible:

## Hardware

Es importante identificar y conocer cada dispositivo de hardware que conforma la red o al menos aquellos los cuales depende el funcionamiento de los procesos informáticos en la organización, con el objetivo de determinar la funcionalidad de cada equipo con Software Libre.

**Estaciones de Trabajo y Servidores:**

*  Tarjeta Madre: Marca y modelo (en caso de las portátiles marca y modelo del equipo)

*  Procesador o CPU: 
    * Arquitectura: i386, x64, Mips, ARM, etc.
    * Marca: Intel, AMD
    * Modelo y Serie: ejemplos: Celeron Conroe, Core i5, Phenom II, etc

*  Memoria RAM:
    * Cantidad en MB: 512, 1024, 2048, 4096...
    * Tipo de Memoria: SIMM, DIMM, DRAM, etc.
    * Opcional: cantidad de slots usados y libres

*  Disco Duro:
    * Capacidad de Almacenamiento en GB
    * Tipo: SATA, IDE, Scsi, SSD

*  Tarjetas de Red:
    * Marca y modelo tanto cableadas como inalámbricas
    * Opcional: módulo del kernel requerido
    * Opcional: Firmware requerido

*  Tarjeta Gráfica
    * Marca y modelo
    * Opcional: cantidad de memoria en MB
    * Opcional: tipo de memoria (compartida, RAMBUS, SDRAM)

**Impresoras:**

*  Marca (mostrada en la carcasa)

*  Fabricante (puede diferir de la marca)

*  Modelo

*  Driver CUPS

*  Filtro PPD

*  Funcionalidades extra de impresión (doble cara, engrapado, etc)

**Otros (scanners, Cámaras de Video, Captahuellas, etc):**

*  Marca (mostrada en la carcasa)

*  Fabricante (puede diferir de la marca)

*  Modelo

*  Módulo del Kernel (si aplica)

*  Arquitectura (si aplica)

Es posible usar un sistema en Software Libre como [OSC Inventory](https///www.ocsinventory-ng.org/en/) para acopiar de manera rápida y ordenada esta información. 

###  Clasificación de Hardware 

Una vez obtenidos estos datos, se recomienda añadir la categoría "compatibilidad" a cada componente encontrado, determinando luego de probar el comportamiento de cada uno en un Sistema con Kernel Linux:


*  **Hardware Compatible**: Funciona con [Linux-Libre](https///www.fsfla.org/ikiwiki/selibre/linux-libre/), es decir, no requiere ningún módulo privativo o "blob" oculto. Ejemplo: cualquier teclado o mouse genérico.

*  **Hardware Privativo**:
    * **Tipo A**: Hardware en el cual algunas funcionalidades sólo se acceden mediante el uso de componentes privativos y sin ellos el funcionamiento es parcial. Ej: tarjetas de Video que sólo aceleran con el driver privativo o algunas NIC cuya velocidad es 10/100/1000 con driver privativo y 10/100 sin él. 
    * **Tipo B**: Hardware que funciona sólo en versiones del Kernel con Blobs o mediante módulos o Firmware privativo. Ejemplo: algunas tarjetas WiFi o algunos escáneres.
    * **Tipo C**: Hardware que funciona de forma inestable o muy limitadamente en un kernel Linux aún usando componentes privativos, ejemplo: algunas Tarjetas de TV.

*  **Hardware Incompatible**: No está documentado ni comprobado su funcionamiento en un Kernel Linux. Ejemplo: dispositivos USB muy específicos.

## Talento Humano

Es recomendable integrar desde temprano a quienes asumirán las tareas administrativas de mantenimiento y escalamiento de los sistemas migrados. Si se tiene disponible talento humano de la organización para sumarse a las actividades de migración, será útil caracterizar sus habilidades y conocimientos. Es muy probable que la organización ya tenga clasificados sus trabajadores y les tengan asignados sus roles, lo importante es conocer a quiénes se les puede consultar ciertos aspectos durante las distintas actividades de la migración.

Los siguientes son algunos criterios para identificar perfiles básicos, se pueden evaluar en una escala del 1-5 donde 1 es el menor nivel de conocimiento o experiencia:


*  Nivel de Conocimiento de Administración de Windows

*  Nivel de Conocimiento de uso de GNU/Linux

*  Nivel de Conocimiento de Administración de GNU/Linux (especificar servicios)

*  Nivel de Conocimiento en Programación (especificar IDE y el o los lenguajes)

*  Nivel de Conocimiento en Ofimática (especificar habilidades especiales)

*  Nivel de Conocimiento de Uso de alguna herramienta informática medular para el desempeño de las actividades diarias en la organización (ejemplo: software administrativo)

*  Conocimiento de uno o mas procesos de la organización (formatos de archivos, fuentes de datos, procesamientos manuales o semi-sistematizados, ...)

*  Habilidad y Talento para dar Soporte de usuario final (1er Nivel)

*  Conocimiento sobre el funcionamiento de algún dispositivos de hardware o sistema específico (ejemplo: sistemas biométricos, SCADA, Cámaras de Seguridad, Sistemas de Respaldo en unidades extraíbles)

*  Nivel de asistencia requerida para las funciones comunes de un computador (nivel de usuario final)

Estos criterios sirven para generar un modelo básico de personas relacionadas con los distintos aspectos en una migración. Se puede ampliar o ajustar según el grado de incidencia o participación que tendrá el equipo de trabajo de la organización en el proceso de migración.
## Software

Con el fin de conocer a fondo la cantidad de sistemas utilizados, se debe identificar y de ser posible hacer un análisis completo de cada uno de los programas instalados en el equipo de cada escritorio de trabajo en la organización. Asimismo identificar y describir con la mayor cantidad de detalle posible cada uno de los servicios en red con los cuales se integran los usuarios.

De cada programa o componente se recomienda contar con la siguiente información básica:


*  Nombre de quién desarrolla el producto, marca o casa de software

*  Nombre del Software

*  Versión exacta (con todos sus dígitos y siglas)

*  Lenguaje de programación o IDE con el cual fue desarrollado (opcional, pero muy útil)

*  Licencia de uso, copia, modificación y redistribución del Software (compatibilidad con la Licencia GPL)

*  Existencia de alguna condición especial sobre la actualización de los datos con los que funciona el programa (ejemplo: precio de materiales de construcción o listas negras de IPs)

*  Sistema Operativo (versión exacta) donde funciona actualmente

*  Sistemas Operativos y versiones donde también puede instalarse

*  Vigencia de contrato de uso, soporte y actualizaciones

*  Cantidad de usuarios que lo requieren instalado y configurado sus escritorios

*  Nivel de dependencia para la continuidad operativa o desempeño de algún proceso importante en la organización (del 1 al 5 donde 1 es sin impacto alguno)

# Clasificación del Software 

La identificación previa del universo de programas y sistemas permitirá clasificar cada componente de software existente y el criterio de mayor importancia para agruparlo es según su condición para ser migrado, a saber:

## Software Descartable 

La primera condición que se debe observar en cualquier software es si tiene pertinencia o no en un proceso de migración. Hay componentes de software que deben ser excluidos e ignorados en las posteriores actividades. Es el caso de Defragmentadores, Editores de Registro, Limpiadores del Disco y demás herramientas que no aplican ni se requieren en GNU/Linux.

Otro caso es el de los AntiVirus. Si bien es cierto que existe código malicioso que puede afectar la seguridad de un usuario, en GNU/Linux no existen "programas que se ejecutan invisiblemente, se instalan en el sistema y se replican infectando a otros usuarios". Los antivirus desarrollados para GNU/Linux se usan principalmente para analizar y revisar archivos destinados a usuarios de Windows en servicios como correo electrónico o volúmenes con carpetas compartidas en red. 

Finalmente, la lista de software existente en los escritorios de trabajo podrá contener elementos como juegos que seguramente no requerirán migrarse (salvo en excepciones como en escritorios destinados al uso de niños o terapias cognitivas) así como otros componentes descartables para el resto del proceso como malware, spyware, virus, troyanos y demás elementos similares. 

## Software Libre 

Es bastante frecuente que existan componentes de Software Libre usados en los sistemas, lo cual requiere poca o ninguna atención especial a la hora de usarlos posteriormente en un escritorio migrado al Sistema Operativo GNU/Linux. Un caso insigne es el navegador web (Firefox) o reproductores multimedia (VLC).

## Software Compatible 

Existen casos donde no es necesario o al menos no es obligatorio evaluar una alternativa que sustituya alguna herramienta o programa pues estos pueden ser instalados en GNU/Linux ofreciendo las mismas funcionalidades, mostrando los mismos elementos de su interfaz gráfica.

Existen muchas herramientas que tienen disponibles versiones ejecutables o instaladores para GNU/Linux, como aplicaciones de comunicación para Telegram o para servicios de videoconferencias.

Esta categoría sólo requiere una prueba que confirme la compatibilidad del instalador con la distribución usada y que verifique su correcto funcionamiento.

## Software Sustituible 

Esta categoría comprende los programas que aunque no están disponibles para instalarse y funcionar en GNU/Linux, tienen un sustituto que puede leer algún tipo de archivo en común del Software Privativo correspondiente. A veces el tipo de archivos nativos pueden ser procesados y en otras oportunidades se necesitará pasarlos a un formato intermedio para la conversión.

Es común que existan múltiples alternativas en Software Libre para implementar un sistema o para sustituir una herramienta. Como se expresó anteriormente, se recomienda evitar en lo posible escoger una u otra opción tomando en cuenta sólo el gusto o preferencia, así como sólo valorar la costumbre o dominio que se tenga con una de las posibles tecnologías.

Los elementos comunes en cualquier lista del Software Privativo que puede ser sustituido se compone con los componentes básicos de Software en una estación de trabajo o computador portátil:


*  **Sistema Operativo**: Entre las distribuciones de GNU/Linux [evaluadas](octaviotron/articulos/migracion/evaluacion/escritorios), la última versión estable de Debian (9 Stretch) es la alternativa que obtuvo mejor calificación y es aquella que puede instalarse sin componentes privativos.

*  **Interfaz Gráfica de Escritorio (WM)**: Entre las alternativas evaluadas [Cinnamon v4](octaviotron/articulos/migracion/evaluacion/wm) es el manejador de escritorio que obtuvo la mayor calificación (Agosto 2018).

*  **Herramientas básicas de escritorio**: Los programas que traen los sistemas operativos para funciones básicas o elementales tienen diversidad de alternativas en Software Libre, en la evaluación realizada se obtuvo una [lista de alternativas para Software Común](octaviotron/articulos/migracion/appcomunes)


## Software Migrable 

Esta categoría agrupa aquellos programas que pueden sustituir los productos de Software Privativo, mayormente ofreciendo las mismas características funcionales, pero usando formatos o protocolos que no pueden interoperar con los programas o sistemas que se migrarán.

Es necesario generar una lista con aquellas alternativas en Software Libre que pueden servir como reemplazo y luego evaluar la mejor opción. A continuación un ejemplo de posibles sustitutos para algunos servicios comunes:

 | **Función**                       | **Opciones**                                                 | 
 | ------------                       | ------------                                                 | 
 | Virtualización                    | Xen, KVM/LibVirt, KVM/Proxmox, Docker, LXC                   | 
 | Servicios de Red                   | NethServer, pfSense OPNSense, IPFire, Smoothwall, Zero Shell | 
 | Correo Electrónico                | Zimbra, Kolab, SoGo, Horde, Citadel                          | 
 | Mensajería Instantánea           | OpenFire, eJabberd, Jabberd14, Metronome IM, Prosody, Tigase | 
 | VideoConferencia                   | Jitsi, OpenMeeting, Jami                                     | 
 | Autenticación y Autorización     | FreeIpa, OpenLDAP, Samba4                                    | 
 | Orquestación y Automatización IT | Puppet, Ansible, Chef, SaltStack                             | 
 | Impresión                         | CUPS                                                         | 
 | Monitoreo                          | SNORT, Cacti, Pandora, Nagios, Zabbix                        | 

## Software Incompatible

El principal y mayor obstáculo que se encuentra ante una intención de migración a Software Libre es la dependencia con sistemas de información y programas informáticos que no satisfacen los requerimientos para poder ser sustituido por una alternativa libre.

en estos casos se proponen dos primeras aproximaciones para resolver estos casos:

### WINE

Existe una capa compatibilidad con más de 20 años desarrollándose que permite la ejecución de programas desarrollados para el sistema operativo Windows en un ambiente GNU/LINUX.

Esta solución, llamada WINE convierte las llamadas a APIs de los binarios privativos en llamadas POSIX, el cual es un estándar documentado que permite correr estos programas en el Sistema Operativo GNU/Linux.

A veces el uso de WINE requiere modificar parcial o totalmente el código fuente de los programas o sus procesos de compilación, empaquetamiento o ejecución.

### Servidor de Aplicaciones

Si no es posible instalar localmente estos componentes en WINE, existe una alternativa muy poderosa que permite en casi todos los casos [usar en GNU/Linux aplicaciones que sólo funcionan en Windows](http://gnuwiki.gnu.ve/octaviotron:articulos:migracion:windowsapps) mediante el uso de un servidor de aplicaciones. 

Esta fórmula implica usar instalaciones (y obtener licencias) de Microsoft Windows pero reduce drásticamente la cantidad de máquinas con este sistema operativo, ya que se usará una sola (o unas pocas) instancias para poder operar las herramientas que sólo funcionan bajo ese ambiente.

En el ANEXO 1 "[usar en GNU/Linux aplicaciones que sólo funcionan en Windows](http://gnuwiki.gnu.ve/octaviotron:articulos:migracion:windowsapps)" se explica a detalle cómo construir este servicio.

## Otros Criterios

Existen otros criterios para agrupar y separar el Software:

**Según su frecuencia e impacto de uso**
Determinado por la criticidad que representa para los procesos de la organización

*  **Software Común**: aquellos programas instalados en todos o casi todos los escritorios de trabajo y que se usan para desempeñar las tareas mas frecuentes como ofimática, reproducción multimedia, navegación, etc.

*  **Software Destacado**: Herramientas informáticas que se usan en labores especiales, ya sea por un reducido grupo de usuarios o para un proceso de especial relevancia. Es el caso de los programas de diseño o desarrollo de software.

*  **Software Específico**: Programas poco comunes, cuya utilidad impacta procesos medulares de la organización. Es el caso de herramientas administrativas o sistemas de información para procesos profesionales de alto nivel.

**Según su disponibilidad del Código Fuente**

*  **Software Libre**: Su código fuente es compatible con la [licencia GPL](https///www.gnu.org/licenses/licenses.es.html)

*  **Producto Privativo**: Software comercial del cual no se tiene acceso al Código Fuente

*  **Desarrollo a la medida**: Software desarrollado para la organización por un tercero cuyo acceso al código fuente sea parcial o esté condicionado

*  **Desarrollo local**: Software desarrollado por la organización del cual se tenga acceso al código fuente y opcionalmente a su documentación

## Recuerde: la migración es a Software Libre

FIXME

# Método de Evaluación de Alternativas

En el proceso de migración se sustituye un conjunto de programas por otros. Es un aspecto característico del Software Libre la diversidad de alternativas para cada necesidad y por tanto es fundamental para el éxito de una migración saber escoger la mejor opción para uno u otro componente. 

Para encontrar esta "mejor" alternativa es aconsejable evitar criterios de selección subjetivos, pues pueden estar orientados únicamente por el gusto o incluso la simpatía con la imagen del producto y de esta manera no necesariamente resultará seleccionada la alternativa idónea o al menos la mas apropiada para integrar con los sistemas existentes.

A continuación se propone un método para orientar esta selección. Este método es aplicable a cualquier conjunto de alternativas donde se necesite tomar una decisión acertada para escoger entre ellas.

Tomaremos como ejemplo el caso de la evaluación de distintas distribuciones del Sistema Operativo GNU/Linux para determinar cuáles brindan mejor rendimiento en un conjunto determinado de equipos, usando del kernel oficial mas reciente.

## Opciones a Evaluar

Primero, se eligen arbitrariamente varias alternativas, incluyendo las que parezcan obvias, las mas populares y cualquiera que proponga el equipo técnico. Cuanto mayor sea el número de posibles opciones se tendrá mayor amplitud y diversidad de elementos a evaluar y se evitará omisiones que pueden ser importantes y que no es posible saber su pertinencia e importancia sino después de realizar el proceso.

En nuestro ejemplo los expertos defienden distintas distribuciones y no resulta obvio escoger la mas apropiada. De las discusiones y debates surge la siguiente lista de candidatos:


*  **Debian Estable**: la distribución base de la cual se derivan muchas otras distribuciones populares, con la mayor comunidad de desarrollo en el mundo. Puede instalar exclusivamente componentes de Software Libre.

*  **Ubuntu LTS**: distribución con fines comerciales, desarrollada por la empresa británica Canonical.

*  **Fedora**: distribución RPM mantenida por una amplia comunidad de desarrollo. Sus versiones unos agradables fondos de pantalla y vistosas ventanas de autenticación. Invita a incluir componentes privativos durante su proceso de instalación.

*  **OpenSuSe**: proyecto auspiciado por SUSE Linux (parte de la empresa Novell) para el desarrollo y mantenimiento de una distribución GNU/Linux. Incluye componentes privativos durante su proceso de instalación.

*  **Linux Mint**: distribución basada en Ubuntu, la cual tiene un fuerte énfasis en la usabilidad y facilidad de instalación. Esta distribución desarrolla el escritorio Cinnamon. Invita a incluir componentes privativos durante su proceso de instalación.

*  **CentOS**: versión comunitaria de RedHat, la cual es una copia de sus versiones comerciales con la única diferencia de su imagen (logo y nombre). Incluye componentes privativos durante su proceso de instalación.

## Criterios de Evaluación

Una vez compuesta la lista de opciones, se deben definir los factores que esperan ser satisfechos con la elección y los elementos necesarios o funcionalidades deseadas con las cuales debe contar el producto seleccionado.

Este conjunto de criterios es propio y único para cada grupo de alternativas. Serán muy diferentes los factores que se evalúan cuando se busca escoger un servicio de correo respecto a los que se toman en cuenta para seleccionar un manejador de escritorio y a su vez estos dos serán distintos a los relacionados a la selección de un IDE para desarrollar en un lenguaje determinado. Más aún: serán distintos los criterios que se definen para escoger un IDE, dependiendo de cuál lenguaje de programación se quiere usar y será muy distinto escoger un manejador de escritorio si su uso será para una empresa tradicional o para una agencia de diseño gráfico.

En cada caso entonces deben definirse estos criterios, determinados por las condiciones propias del entorno donde se integran los elementos evaluados y las condiciones consideradas como relevantes que debe tener el producto buscado, para así tomar decisiones mas acertadas y sustentadas.

Por tanto, no habiendo una "lista estándar de criterios", se ilustrará con un ejemplo cómo se determinan cuando se desea evaluar el desempeño de la versión oficial y soportada del Kernel que trae cada una de las distribuciones mas populares de GNU/Linux en el hardware de las estaciones de trabajo de una determinada organización:


*  **Disco Duro**: pruebas realizadas bajo un sistema de archivos común (por ejemplo: EXT4)
    * Velocidad de entrada y salida
    * Velocidad del acceso a un árbol extenso de directorios

*  **Procesador (CPU)**: rendimiento del procesador en alguna tarea exclusiva
    * Velocidad de compresión (ejemplo: algoritmo Gzip)
    * Velocidad de cálculo (ejemplo: factorial de un número grande)

*  **Memoria RAM**: análisis de velocidad de almacenamiento y búsqueda de datos en memoria:
    * Copy: movimiento de datos de una localización de memoria a otra
    * Scale: Similar a Copy, pero multiplicando antes el valor por una constante
    * Add: Lee dos direcciones de memoria, los suma y escribe en una tercera dirección
    * Triad: Combina Add y Scale, con la excepción que el primer valor es multiplicado por una constante antes de ser agregado al segundo valor.

*  **Tarjeta de Video (GPU)**: Velocidad de renderizado de una compleja figura 3D con reflejos, en movimiento

## Instrumento de Evaluación

Los criterios se organizan en campos de una tabla (en una hoja de cálculo, normalmente) donde se les asigna a cada campo un valor que representa el nivel de importancia o relevancia. Este valor corresponde al "peso" o puntuación que otorga cada condición o característica evaluada. 

En nuestro ejemplo, primero colocamos los criterios de primer nivel y se otorga mayor importancia al desempeño del CPU y la Memoria RAM. Para definir el peso de cada elemento se le asigna un porcentaje, resultando en una tabla como la siguiente:

FIXME

A continuación se añaden los elementos que componen cada criterio y de igual modo se le asigna un porcentaje de relevancia con relación a los otros de su grupo:

FIXME

## Puntuación

Cada campo será evaluado en una escala entre 1 y 5 donde cada valor debe estar descrito. El valor mayor (5) se recomienda sea "por encima de lo esperado" y el valor menor (1) una condición de falla, inexistencia o deficiencia crítica.

Este es una ejemplo de la descripción de la escala para evaluar el desempeño de la velocidad del CPU ejecutando el algoritmo de compresión definido:

 1.  El sistema no puede realizar este proceso
 2.  La compresión se realiza afectando la estabilidad del sistema
 3.  El proceso se realiza en tiempo muy prolongado
 4.  La compresión se realiza satisfactoriamente
 5.  La compresión se realiza a una velocidad mayor a la esperada

Es aconsejable que la mayor puntuación sea algo extraordinario y no el resultado esperado, de manera que haya manera de evaluar lo excepcionalmente bueno.

## Selección

Finalmente, se definen dos umbrales: 

*  **mínimo aceptable**: todos los elementos que no superen este nivel se descartarán como alternativas válidas

*  **nivel esperado**: sobre este valor se esperará encontrar la opción ideal.

En principio, la mayor puntuación es la más indicada para seleccionarse, aunque cualquier opción que supere el nivel esperado será igualmente una alternativa válida. De considerarse necesario se puede repetir el proceso evaluando con otros criterios aquellas opciones con buena puntuación.

FIXME


# El Sistema Operativo

Un elemento indispensable en una migración a Software Libre es la distribución o versión del Sistema Operativo que se usará en los equipos. A la hora de elegir este componente fundamental es bueno tener en cuenta los siguientes aspectos:

FIXME 

**Ciclos de Desarrollo y Duración del Soporte**

Ubuntu publica 2 versiones por año y cada 2 años

Fedora trae siempre la más recientes versiones de los programas y el soporte brindado por sus desarrolladores es sólo para la última edición (fijado en un lapso de 6 meses).

Debian GNU/Linux tiene principalmente 3 versiones publicadas:

**Estabilidad Funcionalidad**

FIXME

Las nuevas versiones de un programa informático, en especial las herramientas que ejecutan los usuarios en la interfaz gráfica, normalmente proveen mayores o mejores funcionalidades. 

Ahora bien, por ser reciente no es posible conocer posibles fallas que pasaron desapercibidas durante su desarrollo. 

Es normal que para cualquier producto de software aparezcan parches o actualizaciones.

En el mundo del Software Libre frecuentemente los programas tienen mas de una versión oficial: la versión estable y versiones de desarrollo. A veces rolling-release

**Funcionalidad vs. Conveniencia**

Migrar a Software Libre significa algo mas que cambiar una tecnología por otra, un programa por otro, un nombre por otro. Mas que ser obvio es fundamental que el Software Libre no es el Software Privativo y precisamente a lo que compone esta diferencia hay que prestar atención.

FIXME


*  Usar sólo Software Libre: "Software Libre mientras sea posible, Software Privativo mientras haya dependencia"



*  Documentar todo cambio realizado al instalador o al sistema instalado en las estaciones de trabajo y estas modificaciones proveerlas mediante un servicio de Orquestación o Automatización de IT.

*  Actualizar sólo cuando sea para reforzar la continuidad operativa de la organización, se recomienda aplicar exclusivamente actualizaciones de seguridad del sistema operativo. No se recomienda una política de actualizaciones automáticas ni ascenso del número de versión de los programas sin haber suficientemente evaluado su implicación con los demás sistemas y con la red.

### Instalador

El proceso de instalación del Sistema Operativo junto a las modificaciones necesarias normalmente se realiza de dos maneras: 

1) Se hace una instalación del sistema base y se corre un script que realice las adaptaciones

2) Se construye un instalador a la medida (a veces llamado "semilla") que incluya e implemente estas variaciones. Hay varias maneras de hacer esto, ya sea modificando [Debian Installer](https///wiki.debian.org/DebianInstaller) o haciendo copias instalables de una estación modelo con herramientas como [SystemBack](https///launchpad.net/systemback)


#  Migración de Escritorios

Para un usuario final la migración deja de ser un concepto abstracto y comienza a ser un hecho tangible después de todos los procesos anteriores. Es recomendable que todo el sistema y cada nuevo componente que se le suministre posteriormente haya pasado obligatoriamente por pruebas y se haya certificado su estabilidad para reducir al mínimo las incidencias y poder corregir cualquier falla o mejora antes de presentarse en producción.

## Estación Piloto

Realice la migración de uno o unos pocos escritorios, de preferencia aquellos donde las herramientas de software que impacten lo menos posible los procesos diarios. Escoja usuarios finales, sin especiales habilidades en administración de sistemas o desarrollo de software. Preferiblemente seleccione un voluntario que se manifieste motivado a conocer y aprender a usar Software Libre para obtener reportes sobre incidencias importantes. Escoja otro que pueda ser muy crítico, quizás aquel quien manifieste rechazo o tenga reservas sobre la migración pues este será exigente y acucioso con mayor detalle y un tercer usuario que tenga conocimientos medios o expertos de GNU/Linux y que no pertenezca al equipo de migración o pruebas, de manera de obtener reportes de incidencias con criterios técnicos y posibles comentarios útiles.

Los integrantes del equipo de migración podrán no advertir detalles que un usuario encontrará rápidamente. Ya sea al usar herramientas y funciones que sólo se prueban en la práctica de las actividades diarias o porque el nivel técnico busca por vías distintas alguna función como desmontar un pendrive o copiar/mover un archivo.

## Escalamiento

A medida que las incidencias sean resueltas, que ningún problema importante esté por ser resuelto y que las actividades informáticas de los usuarios se consideren satisfactoriamente realizadas, se podrán ir migrando más sistemas de escritorio.

El análisis del reporte de incidencias y la documentación de técnicas y soluciones es fundamental para avanzar progresivamente de manera segura, estable y controlada.

## Evaluación de la Interfaz (WM)

Para la evaluación del comportamiento y adaptabilidad de las interfaces gráficas existentes en el sistema operativo GNU/Linux, se recomienda estudiar los escritorios más usados y de mayor aceptación por la comunidad de Software Libre, siendo estos los que vienen en la mayoría de las distribuciones de GNU/Linux a nivel mundial y en especial los que están soportados por las distribuciones estudiadas en la primera etapa de este proyecto, a saber:


*  Gnome Shell: Escritorio novedoso y sobrio, con una experiencia de usuario distinta y poderosa. GNOME es el acrónimo de (GNU Network Object Model Environment) es un entorno compuesto enteramente de software libre.

*  KDE 5: desarrollado por un equipo internacional que coopera en la distribución de software libre y de código abierto para computadoras de escritorio y portátiles, está orientado a facilitar la compatibilidad con pantallas de dispositivos móviles.

*  Cinnamon 4: desarrollado inicialmente por Linux Mint, Cinnamon está inspirado en el comportamiento de GNOME 2 con lo cual se busca ofrecer un entorno más tradicional y por tanto con menor impacto para los usuarios habituados a otros sistemas.

*  Mate 1.20: Este desarrollo es un *fork* de GNOME 2. Mantiene un aspecto conservador y simple. Es el que tiene mayor integración con las herramientas de accesibilidad en GNU/Linux.

**Variables a evaluar**

*  Intrerfaz: Elementos relacionados con apariencia, idioma y accesibilidad

*  Notificaciones: Ventanas emergentes y áreas de información

*  Multimedia: Manejo de audio, imágenes y videos

*  Carpetas y Archivos: Facilidad de uso y diseño conservador de los manejadores de archivos.

*  Mantenimiento: Herramientas administrativas del sistema incluidas

{{:octaviotron:articulos:migracion:gnome.png?400|}}{{ :octaviotron:articulos:migracion:kde.png?400|}}
{{:octaviotron:articulos:migracion:cinnamon.png?400|}} {{ :octaviotron:articulos:migracion:mate.png?400|}}

**Resultado**

En la evaluación se escogió Cinnamon debido a ser el único que supero el mínimo aceptable para superar la prueba el 80% de la escala de valoración (5,60 de 7,00)

{{ :octaviotron:articulos:migracion:escritorios.png |}}
## Dinámicas Útiles

Algunas dinámicas aplicadas a los usuarios añaden motivación y simpatía hacia el proceso de migración. Incluya a los usuarios entre las herramientas con las que cuenta para lograr los objetivos. 

Realice actividades que integren a los usuarios finales. Toda persona con acceso a un escritorio migrado puede ser de gran ayuda.

Por ejemplo, ofrezca un reconocimiento formal, placa o diploma a todo usuario quien encuentre una forma de mejorar cualquier sistema o proceso, a quien proponga una solución que optimice o arregle algún proceso informático. Invite a grabar testimonios de un minuto usando la cámara de un celular donde cuenten cómo ha sido la experiencia del cambio.

Sume a esto cualquier otra dinámica que tribute al mejoramiento de los sistemas o facilite de forma práctica la migración, será de gran ayuda.

# Diseño de Seguridad

Esta sección contiene orientaciones para la seguridad informática de los sistemas GNU/Linux, en especial el de los escritorios de trabajo.

## Arranque del Sistema Operativo

El encendido de cada computador requiere atender que se cumplan ciertas condiciones para asegurar el comportamiento esperado del arranque del Sistema Operativo en cada estación de trabajo o computador portátil dentro de la red institucional. Esta sección contiene recomendaciones para asegurar el comportamiento esperado de este proceso en todos los computadores que operan los usuarios en la red institucional.

**Orden de búsqueda de dispositivo de arranque**

Se sugiere restringir el acceso al BIOS o EFI donde puede ser modificado la secuencia de búsqueda de un dispositivo de hardware que contenga un sistema operativo. Se recomienda asegurar con una contraseña esta funcionalidad para impedir que se ejecute un Sistema Operativo distinto al previsto e instalado en el Disco Duro de cada estación, pues un sistema arbitrario que arranque desde el CD/DVD o desde los puertos USB conceden  privilegios totales de lectura y escritura de todos los datos almacenados en el equipo, otorga privilegios de ejecución de cualquier programa en ese hardware y permite realizar conexiones o accesos a algunos servicios de red. Esta posibilidad omite las políticas de seguridad que se activan cuando inicia el sistema operativo instalado en los computadores dentro de la red institucional.

**Opciones del Gestor de Arranque**

El gestor de arranque (GRUB en este caso) permite cambiar varias opciones que define los parámetros para la ejecución del kernel y demás componentes básicos del Sistema Operativo. Si no se indica lo contrario, cualquier usuario puede modificar el arranque para obtener privilegios totales sobre todos los datos almacenados en Disco Duro y permiso para ejecutar cualquier orden arbitraria en el sistema sin registro de actividades en el histórico de comandos ejecutados. Es el caso cuando se añaden parámetros como "single" o "init=/bin/sh" a las opciones de arranque lo cual debe evitarse y restringirse sólo a actividades administrativas.

## Autenticación

En esta sección se describen las consideraciones de seguridad asociadas al inicio de una sesión de usuario en cada uno de los escritorios de trabajo con el Sistema Operativo GNU/Linux vinculados a los presentes servicios implementados en Software Libre.

**Inexistencia de usuarios grupos de usuarios locales**

El presente diseño de seguridad propone la ausencia de usuarios y grupos locales en el sistema operativo. Bajo este esquema sugerido, la autenticación y autorización para iniciar sesiones se otorga exclusivamente desde el controlador de dominio. Esto se traduce técnicamente en la inexistencia entradas de usuarios en /etc/passw y por tanto en /etc/shadow.

**Restricción de usuarios con UID=0**

El presente diseño propone la restricción de asignar UID 0 a cualquier usuario del sistema y la omisión de contraseña de ROOT para impedir localmente o remotamente una sesión con privilegios totales, sin identificación de usuario y sin registro del administrador que incide con este nivel de acceso en el sistema operativo de cada cliente. 


## Autorización

En esta sección se describen las consideraciones de seguridad asociadas a la autorización de permisos de acceso a recursos locales del Sistema Operativo GNU/Linux donde los usuarios operan las funciones de los escritorios de trabajo.

**Privilegios administrativos (sudoers)**:

Cuando sea necesaria la existencia de usuarios “sudoers” con la capacidad de escalar privilegios y tener permitido ejecutar órdenes sobre cada uno de los sistemas operativos conectados al servicio y para la ejecución de comandos con privilegios de root via SUDO1, se recomienda definir en el Controlador de Dominio reglas específicas para usuarios administradores.

**Ambito (scope) de permisos para usuarios**:

Se sugiere que los archivos de cada usuario y en especial su /home tengan por defecto permisos sólo para el UID de la sesión (600 para archivos y 700 para directorios, UMASK 077). Con esto se obtiene acceso a navegación de directorio y apertura de archivos únicamente a los usuarios a los cuales les pertenecen estos datos.

Es necesario configurar que las carpetas de usuarios en /home no tengan permisos para ser accedidos por otro usuario, es decir, todos los directorios y carpetas en /home deben tener permiso "700" o "rwx------" y defina "umask 007" como valor por defecto para todo nuevo archivo de cada usuario. Esto se logra añadiendo esta directiva en ".bashrc" y en las opciones del módulo pam_umask de PAM en  /etc/pam.d/common-session.

## Acceso a SHELL

El acceso via SHELL para actividades administrativas se podrá realizar únicamente por usuarios específicos. El común de los usuarios aplicando las siguientes políticas:


*  Los escritorios tendrán inhabilitada la función de cambio de modo gráfico mediante las combinaciones de la tecla ALT con las Teclas de Función F1-F6. Con esto se restringe el acceso a TTY.

*  Los usuarios se crean por defecto con el valor “/bin/false” en la propiedad “Login Shell” en el Controlador de Dominio. Con esto se inhabilitan los componentes que otorgan una SHELL local o remota, incluyendo las aplicaciones gráficas como “gnome-shell” y similares.

*  Se elimina la combinación de teclas ALT+F2 que invoca la ventana para ejecución arbitraria de comandos desde el escritorio. Con esto se resta otra interfaz desde la cual se pudieran usar atajos para saltar las restricciones anteriores.

## Acceso remoto

Se sugiere circunscribir a un segmento o segmentos muy específicos de direcciones IP a las cuales los clientes escucharán peticiones de acceso remoto, tanto para las sesiones en SHELL como para las conexiones de asistencia técnica vía escritorio remoto. En el caso de conexiones vía VNC se debe habilitar en todos los escritorios la exigencia de aceptación explícita de permiso por parte del usuario quien opera el computador para autorizar esta funcionalidad.

## Sistema de Archivos

**Restricción de Ejecución de archivos arbitrarios**:

Se sugiere añadir la opción “NOEXEC” a todos los sistemas de archivos donde los usuarios tengan permiso de escritura. Como regla general esta condición aplica para /tmp y el directorio /home de cada usuario, incluyendo todos los subdirectorios contenidos allí. Para asignar este comportamiento al sistema de archivos se requiere que el sistema operativo se instale con una partición aparte para cada una de estas rutas. Bajo este esquema, las particiones en cada sistema operativo de los clientes se definen de la siguiente manera:

    /         defaults
    /home     noexec
    /tmp      noexec
    /usr      defaults

De igual modo se aplica esta política para las unidades de almacenamiento compartidas en red y los directorios accesibles al introducir dispositivos USB, SD, FlashCard, BlueTooth y cualquier otro medio de almacenamiento externo. Con esto se impide la ejecución de archivos con guiones (scripts) en SHELL o binarios con potencial incidencia en el sistema o el ámbito del usuario.

**Visibilidad de Carpetas Ocultas**:

Se sugiere eliminar la opción para visualizar archivos y directorios ocultos mediante el navegador de archivos. Con esto se elimina la posibilidad de realizar cambios arbitrarios en las configuraciones de ejecución de los programas y valores como variables de entorno que pueden incidir en el comportamiento estandarizado del escritorio de trabajos de los usuarios regulares en la red. Se debe complementar esta condición de acceso eliminando el botón de entrada de ruta arbitraria en el navegador de archivos.

## Acceso Local

En caso de requerir un acceso local al equipo, por ejemplo cuando fallen sus tarjetas de red y no sea posible realizar sobre los clientes asistencia remota, se sugiere el uso de un “Live CD2” o “Live USB3” con una distribución booteable del sistema operativo GNU/Linux. Para que esta opción no represente una brecha de seguridad física, se recomienda restringir por defecto la capacidad de los equipos para levantar su sistema desde un medio alternativo al Disco Duro local y restringir el acceso al BIOS o UEFI con una contraseña distinta en cada equipo y sólo conocida por los administradores que dan soporte.

## Política de Contraseñas

La gestión de las contraseñas centraliza en el servicio Kerberos, por lo tanto su comportamiento puede definirse con los siguientes parámetros:


*  Tiempo mínimo de vida de una contraseña, en horas, en las cuales una clave debe tener efecto antes que el usuario pueda cambiarla.

*  Tiempo máximo de vida de una contraseña. Este parámetro contiene el límite de días en que una contraseña está vigente antes que se haga obligatoria una actualización.

*  Número mínimo de clases de caracteres de una contraseña. Las clases pueden ser: Mayúsculas, Minúsculas, Números y Caracteres Especiales.

*  Mínima cantidad de caracteres de una contraseña para que sea considerada como válida.

*  Tamaño del historial de claves que se almacenan para prevenir su uso posterior por el usuario.

**Algoritmo de Cifrado**

Se usa el tipo de cifrado AES256-CTS-HMAC-SHA1-96 cuya nomenclatura indica los mecanismos aplicados:

AES2564: Cifrado AES con una llave de 256-bits
CTS5: Modo de Operación de los bloques de cifrado
HMAC6: Código de autentificación de mensajes en clave-hash
SHA17: Función de cifrado
96: Truncado de seguridad a 96 bits

Para mayor información sobre este tipo de cifrado se recomienda leer el capítulo 5 del documento8 publicado por National Institute of Standards and Technology.

## Servicios en un Sistema Operativo de Escritorio

Es posible que se necesiten servicios en el Sistema Operativo de un usuario final. Es el caso del acceso a escritorio remoto o a consola shell.

Es necesario restringir todos los puertos y sólo permitir peticiones externas en los clientes a los servicios conocidos, cerrando todos los demás y circunscribir a un segmento específico de direcciones IP el acceso desde la red.


# Conclusiones


*  **Involucre a sus usuarios**: El Software Libre es participativo por naturaleza. Cada uno de los usuarios es un sujeto que puede formar parte activa en los procesos inherentes a su actividad e intereses o necesidades en su uso cotidiano de la informática: aunque un usuario no sea programador o administrador de redes, es la persona que usa regularmente los sistemas y puede opinar con propiedad dónde ha observado cuellos de botella o dónde ha detectado carencia de funcionalidades que pueden optimizar los procesos de la organización. 


*  **Sensibilice**: Todos los planes de migración a Software Libre deberían pasar antes por un acercamiento a los usuarios mediante jornadas que les informen y preparen para el cambio, reduciendo la resistencia o la inconformidad, transmitiendo tranquilidad de que serán asistidos siempre que lo necesiten durante la migración y posteriormente tendrán soporte para adaptarse. Hágales saber que aprenderán una nueva tecnología que ampliará sus habilidades profesionales. 


*  **No confronte a los usuarios**: Pueden haber usuarios que se nieguen a priori a migrar a Software Libre, ya sea por un prejuicio o debido a una experiencia anterior negativa. En caso de instituciones públicas, suministre copia de las leyes que ordenan la migración. Evite la confrontación y la imposición, aunque sea obligatorio y ya esté decidido realizar el cambio. Una dinámica útil es pedirles que escriban una lista de mejoras que quisieran en las herramientas informáticas que usan a diario para facilitar o para optimizar su trabajo y luego hágales saber cuáles de esas mejoras ya están incluidas cuando tenga su nuevo escritorio de trabajo. 


*  **Mantenga la Continuidad Operativa**: por último, pero no menos importante, es necesario asegurar en todo momento la fluidez del trabajo y de los procesos informáticos de la organización, para esto se recomienda probar suficientemente cada cambio programado y haber previsto previamente la incidencia que tiene cada nuevo componente en el sistema.

## ANEXO 1: Cómo usar en GNU/Linux aplicaciones que sólo funcionan en Windows

Cuando se comienzan a elaborar planes y estrategias para migrar el Sistema Operativo de todos los escritorios de trabajo a Software Libre, es común encontrar una gran dificultad para resolver el caso de aquellos programas los cuales no tienen ejecutables para GNU/Linux, no es posible correrlos con WINE y no se encuentran alternativas libre que puedan reemplazarlos, que cuenten con las mismas funcionalidades requeridas y que puedan leer sus formatos privativos.

Una propuesta común en la elaboración de estas estrategias consiste en usar un sistema virtualizado (ej. VirtualBox) resultando en la presencia de dos escritorios simultáneos para el usuario y requiriendo una cantidad considerable de recursos en el hardware de las estaciones de trabajo, casi siempre ofuscando y ralentizando el funcionamiento de todas las operaciones comunes.

Tenemos entonces una variedad de programas privativos de los cuales se desconoce una receta para hacerlos correr en GNU/Linux y de lograrlo (vía WINE) es posible que algunas de sus funcionalidades fallen. Muchos de estos programas son aquellos hechos por las mismas organizaciones en lenguajes privativos, con poca o ninguna documentación de su código y duramente vinculados (“cableados”, en la jerga común) con otros sistemas similares que también requieren Windows para operar y si son una piedra de tranca en una migración es por ser indispensables para la continuidad operativa o el funcionamiento de importantes procesos de la organización. 

Esta situación ha sido por siempre causa de desilusiones e intentos fallidos al emprender un plan o proceso de sustituir por GNU/Linux el Sistema Operativo de los escritorios y a continuación se describe una alternativa, usando una sesión de usuario desde un “escritorio central” el cual provee (mediante un protocolo de red) las “ventanas” de las aplicaciones que necesitan los clientes quienes las visualizan como una aplicación más, inlcuso disponible como una entrada mas en su menú de inicio o como otro icono de acceso del escritorio.

**El protocolo RDP**

El protocolo RDP, desarrollado por Microsoft, permite la transmisión por red de la vista de un escritorio completo (al estilo VNC) pero su mas interesante característica es que permite también enviar sólo la ventana de cualquier programa. Es decir: una máquina (física o virtual) con Microsoft Windows puede “servir” cualquier aplicación instalada, digamos notepad, iexprorer o cualquier otro programa local instalado y entonces un cliente GNU/Linux puede mostrar en su escritorio esa ventana, de manera similar como muestra cualquier otra (LibreOffice, GIMP, Gedit, etc). Esto es posible lograrlo gracias a que existe una implementación libre del cliente RDP llamado FreeRDP.

Esta tecnología permite incluso enviar recursos a esas ventanas foráneas, entre los cuales destacan:

*  Sistemas de archivos locales (carpetas existentes en el cliente)
*  Unidades compartidas en red (carpetas montadas en red)
*  Unidades de CD/DVD
*  Unidades de almacenamiento (USB Drive)
*  Puertos físicos (serie, paralelo, USB)
*  Dispositivos de sonido (micrófono y salida de audio)
*  Dispositivos de red
*  Otros (es software libre y permite desarrollarle módulos adicionales)

### Instalación de un Escritorio Central

El servicio RDP se puede instalar en varias versiones de Windows (no en todas) y su funcionamiento ha sido probado satisfactoriamente con todas las funciones necesarias en la versión "Windows 7 Ultimate" en donde se requieren los siguientes pasos:


*  **Reconfigurar el Cortafuegos**: El Cortafuegos y cualquier otra herramienta que controle las reglas de los puertos IP (antivirus o similares) deben permitir peticiones y acceso a servicios por TCP/3389. En el ambiente de desarrollo se puede deshabilitar totalmente el cortafuegos, en producción será necesario realizar este ajuste de seguridad.

*  **Habilitar las peticiones de Escritorio Remoto**: habilitar la opción “Permitir conexiones de asistencia remota a este equipo” (en inglés la opción es “Allow remote connections to this computer”) dentro de la pestaña “Escritorio Remoto” en la sección “Sistema” del panel de control.

{{ :octaviotron:articulos:migracion:remote.png?300 |}}


*  **Instalar .NET Framework**: se requiere específicamente la [versión 4.0](https///download.microsoft.com/download/9/5/A/95A9616B-7A37-4AF6-BC36-D6EA96C8DAAE/dotNetFx40_Full_x86_x64.exe) de este componente. No está probado que funcione con versiones más nuevas o distintas a esta.

*  **Instalar y Configurar RemoteApp Tool**: Después de instalarse [RemoteApp Tool](http://www.kimknight.net/remoteapptool/remoteapptool5300.zip) debe habilitarse en este programa la opción para proveer aplicaciones vía RDP. Se pueden habilitar todas las aplicaciones para todos los usuarios o también es posible proveer una lista de aplicaciones con los usuarios permitidos para su acceso remoto.

{{:octaviotron:articulos:migracion:remoteapptool01.png?400|}} 
{{:octaviotron:articulos:migracion:remoteapptool02.png?400|}}
 

*  **Habilitar sesiones concurrentes**: Para proveer el servicio a varios usuarios simultáneamente, es necesario correr la aplicación [Concurrent RDP](https///raymondcc.r.worldssl.net/Concurrent%20RDP%20Patcher_2-22-2011.zip), la cual modifica las entradas del registro que permiten esta función.

#### Cliente RDP

Sólo es necesario tener instalada la versión 2.0 o superior de [FreeRDP](https///github.com/FreeRDP/FreeRDP/wiki/PreBuilds) con lo cual es posible crear un icono de acceso directo en el escritorio o una entrada en el menu principal que invoque la aplicación requerida, mediante un comando similar al siguiente:

    
    xfreerdp /u:usuario /p: /d:dominio /v:servidor /app:calc
    

{{ :octaviotron:articulos:migracion:calc.png?600 |}}

Esto invocará la aplicación "calc" (la calculadora de Windows) y la mostrará en el escritorio del usuario cliente.

Para invocar otra aplicación, será necesario incluir la ruta al binario ejecutable correspondiente, ejemplo:

    xfreerdp /u:usuario /p: /d:dominio /v:servidor /app:"c:\ruta\al\ejecutable.exe"

Quizás sea necesario añadir la opción /cert-ignore para abrir sesiones sin certificado, en especial para el ambiente de desarrollo. Más información en el man de xfreerdp, también visible ejecutando “xfreerdp /help” o bien disponible en la página de [documentación](https///github.com/FreeRDP/FreeRDP/wiki/CommandLineInterface) del desarrollo.



