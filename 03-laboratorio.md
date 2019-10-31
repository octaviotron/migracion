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

*  **Repositorio** actualizado diariamente de todas las distribuciones involucradas.
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

