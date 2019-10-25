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

