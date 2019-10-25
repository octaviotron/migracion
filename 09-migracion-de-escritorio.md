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

**Resultado**

En la evaluación se escogió Cinnamon debido a ser el único que supero el mínimo aceptable para superar la prueba el 80% de la escala de valoración (5,60 de 7,00)

