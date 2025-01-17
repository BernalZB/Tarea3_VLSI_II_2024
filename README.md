
![Logo](/Imagenes/Firma_TEC.png)
# Tarea 3
Integrantes del grupo:

* Francisco Coto Alcázar
* Bernal Zamora Barrantes 
* Andres Rojas Barboza 

## Introducción

n esta tarea, se procederá a la instanciación y caracterización de un flip flop estático Amo-Esclavo de 1 bit utilizando la herramienta Custom Compiler. Se empleará la celda DFFHDLLX0 de la librería D_CELLS_HDLL para el diseño, la cual carece de reset y cuenta únicamente con las entradas D y CN, generando salidas Q y QN. Se implementará un reloj utilizando inversores para controlar la señal de reloj del flip flop, permitiendo así simular de manera realista la pendiente de la señal de reloj. Posteriormente, se llevará a cabo una simulación en Hspice a nivel de trazado para determinar y comparar los parámetros de tiempo de setup (tsetup) y tiempo de retardo (thold) con los valores provistos por Liberty Displayer, mediante la técnica de variación de tcd y la medición de tpcq, siguiendo la metodología descrita en el documento de caracterización de celdas.

## Datos Relevantes

* Uso de la tecnología XH018
* El calculo de los valores de la parte 1 pueden observasrse en el archivo Tarea_1.pdf
* Simulador: HSpice
* Herramienta de diseño: custom compiler
* λ = 90µm.
* SUPPLY = 1.8V

## Resultados

Para la optención de los resultados se instanció tanto el esquematico como el layout del flip flop DFFHDLLX0 junto con 2 inversores de 1x y 4x los cuales acondicionan la señal para tener una señal de clock realista. Este se encuentra presente en la biblioteca del curso. A continuacion se muestra una imagen tanto del layout como del esquemático. 

![setupgrafico](./Imagenes/layout.jpg)

Posteriormente, se procedio a la optención de set up time y hold time característicos del flip flip menciondo. Para esto se uitlizó, lo visto en [2], y mediante simulación en Hspice a nivel de trazado (LPE) se comprobó los parámetros de tsetup, thold, usando la técnica de variación de tcd y midiendo tpcq. Para esto se utilizó un metodo de barrido de la fuente y se medio la señal de clock, las entradas de los datos y la salida. A continuación se puede ver ejemplo de las simulaciones. 

![setupgrafico](./Imagenes/simulacion1.jpg)
![setupgrafico](./Imagenes/simulacion2.jpg)
Para el set up time se obtuvo la respuesta mostrada en la siguiente figura. 

![setupgrafico](./Imagenes/SetUp.png)

Para el hold time se obtuvo la respuesta mostrada en la siguiente figura.

![holdafico](./Imagenes/hold.png)

Por lo que la caracterización del sistema corresponde al mostrado en la siguiente figura.

![sethol](./Imagenes/sethold.png)

Según lo mencionado en [1] de las graficas se puede extraar el setup time y hold time. asi mism, comprando el set up time y el hold time encontrado con las características en el Liberty Displayer se obtuvo. 

| Time | Medido | Liberty Displayer [PS] | % de eror |
|-----------|-----------|-----------|-----------|
| Set Up   | 250 | 273  |  8.42 |
| Hold    | 775  | 762  | 1.67  |

 
## Análisis 

Los resultados obtenidos muestran un bajo porcentaje de error, lo que indica una alta precisión en la medición del tiempo de setup y hold del flip-flop.

En el tiempo de Set Up aunque el error es ligeramente mayor que el del tiempo de hold, sigue siendo un valor aceptable en la mayoría de las aplicaciones prácticas. La diferencia puede ser atribuida a variaciones en las condiciones de prueba que pueden deberse a los modelos de simulación o la cantidad de datos extraidos que permiten un mayor análisis estadístico del mismo.

Por otra parte, el tiempo de Hold es muy bajo, indicando una excelente correlación entre las mediciones realizadas y los valores proporcionados por el Liberty Displayer. Las razones para este bajo porcentaje de error pueden otra vez variaciones en las condiciones.

Por lo que, los resultados obtenidos para los tiempos de setup y hold del flip-flop son altamente aceptables debido a los bajos porcentajes de error. Los factores que pueden contribuir a estas pequeñas discrepancias incluyen diferencias entre los modelos de simulación y las condiciones reales de operación del dispositivo.


## Conclusiones

En resumen, el análisis demuestra que los tiempos de setup y hold medidos son confiables y se alinean estrechamente con los valores esperados. Esto asegura que el flip-flop funcionará correctamente dentro de los márgenes de tiempo especificados, garantizando un diseño robusto y fiable en aplicaciones prácticas.

## Referencias
[1] N. Weste and D. Harris, CMOS VLSI Design: A Circuits and Systems Perspective, 4 edition. Boston: Addison-Wesley, 2010.

[2] Process and Device Specification XH018 - 0.18 μm Modular Mixed Signal HV CMOS, PDS-018-13. Release 7.0.1. XFAB Semiconductor Foundries, Nov. 2017.

[3] J. Rabaey, A. Chandrakasan y B. Nikolic. Digital Integrated Circuits: A Design Perspective.

