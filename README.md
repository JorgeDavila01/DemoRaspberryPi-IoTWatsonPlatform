# DemoRaspberryPi-IoTWatsonPlatform

## Introducción 

El siguiente repositorio contiene toda la información, el paso a paso, los elementos necesarios y la carpeta con los archivos necesarios para realizar una guía con un sensor de temperatura, Raspberry Pi y el enlazamiento por medio de node-red con Watson IoT platform de IBM.

## Índice

* Elementos necesarios para la realización de la guía.
* Montaje físico. 
* Implementación de la aplicación en Node-red.
* Explicación de la aplicación.
* Referencias.

### Elementos necesarios para la realización de la guía.

A continuación, vera la lista de elementos necesarios para el desarrollo de la guía.

* Raspberry Pi.
* Protoboard.
* Resistencia de 4,7 KΩ.
* Sensor temperatura DS18B20.
* Cables de conexión rápida conectores Hembra-Macho.

### Montaje físico. 

Para realizar el montaje primero se debe tener el orden correspondiente de los pines del sensor DS18B20, el cual puede ver a continuación:

<img width="350" alt="1" src="https://user-images.githubusercontent.com/50923637/70634902-0143ff80-1c01-11ea-87fe-2421cfbd253c.png">

Imagen tomada de:

* https://saber.patagoniatec.com/2014/06/ds18b20-sensor-temperatura-ds18b20-sumergible-agua-liquido-arduino-argentina-ptec/

Antes de realizar la implementación tenga en cuenta las características técnicas del dispositivo que vaya a implementar. 

| Especificación | Valor |
| ------------- | ------------- |
| Fuente de alimentación  | Desde 3V hasta 5,5V  |
| Consumo de corriente | 1mA  |
| Rango de temperatura  | Desde -55°C hasta 125°C  |
| Exactitud o tolerancia  | ± 0.5°C  |
| Resolución  | 9 a 12 bits (seleccionables)  |
| Tiempo de converisón  | Mayor a 750mS  |

A continuación, podrá ver el diagrama de conexión necesario para realizar la guía. 

<img width="350" alt="2" src="https://user-images.githubusercontent.com/50923637/70640326-ca261c00-1c09-11ea-8155-2521c9af4608.png">
