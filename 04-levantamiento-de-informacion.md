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
