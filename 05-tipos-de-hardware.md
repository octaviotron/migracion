# El Hardware

Es importante identificar y conocer cada dispositivo de hardware que conforma la red o al menos aquellos los cuales depende el funcionamiento de los procesos informáticos en la organización, con el objetivo de determinar la funcionalidad de cada equipo con Software Libre.

## Levantamiento de Información

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

Es posible usar un sistema en Software Libre como [OSC Inventory](https///www.ocsinventory-ng.org/en/) para acopiar de manera rápida y ordenada la mayor parte de esta información.

## Clasificación 

Una vez obtenidos estos datos, se recomienda añadir la categoría "compatibilidad" a cada componente encontrado, determinando luego de probar el comportamiento de cada uno en un Sistema con Kernel Linux:

*  **Hardware Compatible**: Funciona con [Linux-Libre](https///www.fsfla.org/ikiwiki/selibre/linux-libre/), es decir, no requiere ningún módulo privativo o "blob" oculto. Ejemplo: cualquier teclado o mouse genérico.

*  **Hardware Privativo**:
    * **Tipo A**: Hardware en el cual algunas funcionalidades sólo se acceden mediante el uso de componentes privativos y sin ellos el funcionamiento es parcial. Ej: tarjetas de Video que sólo aceleran con el driver privativo o algunas NIC cuya velocidad es 10/100/1000 con driver privativo y 10/100 sin él. 
    * **Tipo B**: Hardware que funciona sólo en versiones del Kernel con Blobs o mediante módulos o Firmware privativo. Ejemplo: algunas tarjetas WiFi o algunos escáneres.
    * **Tipo C**: Hardware que funciona de forma inestable o muy limitadamente en un kernel Linux aún usando componentes privativos, ejemplo: algunas Tarjetas de TV.

*  **Hardware Incompatible**: No está documentado ni comprobado su funcionamiento en un Kernel Linux. Ejemplo: dispositivos USB muy específicos.
