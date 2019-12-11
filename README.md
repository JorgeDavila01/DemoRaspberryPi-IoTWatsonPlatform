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

* [Referencia imagen PINOUT DS18B20](https://saber.patagoniatec.com/2014/06/ds18b20-sensor-temperatura-ds18b20-sumergible-agua-liquido-arduino-argentina-ptec/)

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

### Implementación de la aplicación en Node-red.

**Antes de implementar la aplicación de esta guía debe tener instalado Node-Red en su raspberry Pi.**

* [Instalación Node-red en su Raspberry pi](https://nodered.org/docs/getting-started/raspberrypi)

**También debe tener previamente creado su servicio de Watson IoT platform y haber registrado su dispositivo.**

En el siguiente video podrá ver como se habilita en la raspberry el pin para que tome los datos del sensor de temperatura fijese en el minuto **2:35 hasta el 3:05** [Video configuracion Pin raspberry para DS18B20](https://www.youtube.com/watch?time_continue=20&v=aEnS0-Jy2vE)
