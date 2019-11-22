# Evaluación de Alternativas

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

Es importante notar que con la excepciòn de Debian, el instalador y el administrador de paquetes de las distribuciones anteriormente listadas, sugieren la inclusión de programas privativos en el sistema operativo. Algunas distribuciones también contienen [blobs](http://manulix.wikidot.com/kernel-blobs) en el kernel y corresponde evaluar los riesgos a la seguridad y privacidad de los datos almacenados en sistemas con estos componentes.

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

