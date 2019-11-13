## Cómo usar en GNU/Linux aplicaciones que sólo funcionan en Windows

Cuando se comienzan a elaborar planes y estrategias para migrar el Sistema Operativo de todos los escritorios de trabajo a Software Libre, es común encontrar una gran dificultad para resolver el caso de aquellos programas que no tienen ejecutables para GNU/Linux, no pueden correr en un emulador y no se cuenta con alguna alternativa libre o sus reemplazos similares no ofrecen algunas funcionalidades requeridas o no puedan leer el histórico de los archivos creados por los usuarios.

Una propuesta común en la elaboración de estas estrategias consiste en usar un sistema virtualizado en un hypervisor (VirtualBox, KVM, VMware) lo cual requiere una cantidad considerable adicional de memoria y procesador pues serán dos Sistemas Operativos funcionando simultáneamente en el mismo hardware, ofuscando y ralentizando el funcionamiento de todas las operaciones comunes en el escritorio de trabajo.

Tenemos entonces una variedad de programas privativos de los cuales se desconoce una receta para hacerlos correr en GNU/Linux y de lograrlo (vía WINE, por ejemplo) es posible que algunas de sus funcionalidades fallen. A esto se suman aquellos programas hechos a la medida en lenguajes privativos, con poca o ninguna documentación de su código y duramente vinculados (“cableados”, en la jerga común) con otros sistemas similares que a su vez requieren Sistemas Operativos distintos para operar y que por ser indispensables en los procesos operativos se convierten sin duda en una piedra de tranca para cualquier intento de migración.

A continuación se describe una alternativa para resolver esta situación. En resumen, consiste en colocar un “escritorio central” el cual provee en una red local las “ventanas” de los programas que necesitan los usuarios, quienes en sus escritorios con GNu/Linux las pueden visualizar como una entrada mas en su menú de aplicaciones o como otro icono de acceso del escritorio.

**El protocolo RDP**

El protocolo RDP permite la transmisión por red de la interfaz gráfica de un Sistema Operativo (al estilo VNC). Su mas interesante característica consiste en que puede enviar sólo la ventana de programas específicos y no todo el escritorio de trabajo. De esta manera una máquina (física o virtual) con Microsoft Windows puede “servir” los programas que se le han instalado y accederles desde la interfaz gráfica de los clientes con GNU/Linux como una aplicación mas.

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

El servicio RDP está soportado en algunas versiones de Windows. Para este documento, el proceso se relizó usando "Windows 7 Ultimate" y según la documentación consultada se pueden obtener los mismos resultados en "Windows 7 Enterprise" y "Windows 7 Profesional". Quizás sea posible lograrlo en versiones distintas a estas, pero el la referida se garantiza que funciona apropiadamente. Para esto se requieren los siguientes pasos:

*  **Reconfigurar el Cortafuegos**: El Cortafuegos y cualquier otra herramienta que controle las reglas de los puertos IP (antivirus o similares) deben permitir peticiones y acceso a servicios por TCP/3389. En el ambiente de desarrollo se puede deshabilitar totalmente el cortafuegos, en producción será necesario realizar este ajuste de seguridad.
*  **Habilitar las peticiones de Escritorio Remoto**: Es necesario habilitar la opción “Permitir conexiones de asistencia remota a este equipo” (en inglés la opción es “Allow remote connections to this computer”) dentro de la pestaña “Escritorio Remoto” en la sección “Sistema” del panel de control del sistema.

![ c ](/imgs/remote.png)

*  **Instalar .NET Framework**: se requiere específicamente la [versión 4.0](https://download.microsoft.com/download/9/5/A/95A9616B-7A37-4AF6-BC36-D6EA96C8DAAE/dotNetFx40_Full_x86_x64.exe) de este componente. No está probado que funcione con versiones más nuevas o distintas a esta.
*  **Instalar y Configurar RemoteApp Tool**: Después de instalarse [RemoteApp Tool](http://www.kimknight.net/remoteapptool/remoteapptool5300.zip) debe habilitarse en este programa la opción para proveer aplicaciones vía RDP. Se pueden habilitar todas las aplicaciones para todos los usuarios o también es posible proveer una lista de aplicaciones con los usuarios permitidos para su acceso remoto.

![ c ](/imgs/remoteapptool01.png)
![ c ](/imgs/remoteapptool02.png)


*  **Habilitar sesiones concurrentes**: Para proveer el servicio a varios usuarios simultáneamente, es necesario correr la aplicación [Concurrent RDP](https://raymondcc.r.worldssl.net/Concurrent%20RDP%20Patcher_2-22-2011.zip), la cual modifica las entradas del registro que permiten esta función.

#### Cliente RDP

Sólo es necesario tener instalada la versión 2.0 o superior de [FreeRDP](https://github.com/FreeRDP/FreeRDP/wiki/PreBuilds) con lo cual es posible crear un icono de acceso directo en el escritorio o una entrada en el menu principal que invoque la aplicación requerida, mediante un comando similar al siguiente:

    
    xfreerdp /u:usuario /p: /d:dominio /v:servidor /app:calc
    
![ c ](/imgs/calc.png)

Esto invocará la aplicación "calc" (la calculadora de Windows) y la mostrará en el escritorio del usuario cliente.

Para invocar otra aplicación, será necesario incluir la ruta al binario ejecutable correspondiente, ejemplo:

    xfreerdp /u:usuario /p: /d:dominio /v:servidor /app:"c:\ruta\al\ejecutable.exe"

Quizás sea necesario añadir la opción /cert-ignore para abrir sesiones sin certificado, en especial para el ambiente de desarrollo. Más información en el man de xfreerdp, también visible ejecutando “xfreerdp /help” o bien disponible en la página de [documentación](https://github.com/FreeRDP/FreeRDP/wiki/CommandLineInterface) del desarrollo.

