## Cómo usar en GNU/Linux aplicaciones que sólo funcionan en Windows

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

