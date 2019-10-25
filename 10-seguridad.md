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

