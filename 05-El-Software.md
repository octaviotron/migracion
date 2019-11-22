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

