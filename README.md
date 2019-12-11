# DemoRaspberryPi-IoTWatsonPlatform

## Introducción 

El siguiente repositorio contiene toda la información, el paso a paso, los elementos necesarios y la carpeta con los archivos necesarios para realizar una guía con un sensor de temperatura, Raspberry Pi y el enlazamiento por medio de node-red con Watson IoT platform de IBM.

## Índice

* Elementos necesarios para la realización de la guía.
* Montaje físico. 
* Implementación de la aplicación en Node-red.
* Explicación de la aplicación.

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

<img width="500" alt="2" src="https://user-images.githubusercontent.com/50923637/70640326-ca261c00-1c09-11ea-8155-2521c9af4608.png">

### Implementación de la aplicación en Node-red.

**Antes de implementar la aplicación de esta guía debe tener instalado Node-Red en su Raspberry Pi.**

* [Instalación Node-red en su Raspberry pi](https://nodered.org/docs/getting-started/raspberrypi)

**También debe tener previamente creado su servicio de Watson IoT platform y haber registrado su dispositivo en la plataforma.**

En el siguiente video podrá ver como se habilita en la raspberry el pin para que tome los datos del sensor de temperatura fijese en el minuto **2:35 hasta el 3:05** [Video configuracion Pin raspberry para DS18B20](https://www.youtube.com/watch?time_continue=20&v=aEnS0-Jy2vE)

Primero debe acceder a la dirección local que se indica como localhost, esta dirección aparece luego de que usted inicie Node-red o inicie dando clic en el icono que aparece en la sección de programación con la que cuentan las últimas versiones del raspbian.

<img width="300" alt="3" src="https://user-images.githubusercontent.com/50923637/70658297-b4295300-1c2b-11ea-8cc6-a19b2ffc464c.png">

Después de haber abierto la URL de local, usted vera el Node-red, donde en su costado izquierdo vera los nodos por si quiere realizar alguna implementación, en su lado derecho el espacio para la descripción de los nodos.

<img width="600" alt="3" src="https://user-images.githubusercontent.com/50923637/70658537-2bf77d80-1c2c-11ea-8abc-7684c3b0cdea.png">

Luego usted debe instalar los nodos del sensor de temperatura DS18B20 para Node-red, para esto usted da clic en el menú de hamburguesa y luego clic en manage palette.

<img width="600" alt="3" src="https://user-images.githubusercontent.com/50923637/70658712-82fd5280-1c2c-11ea-9548-5964cc959656.png">

Luego de ingresar al manage palette debe dar clic en install, usted en la sección donde esta la lupa escribe DS18B20 y los dos primeros nodos que ve a continuación son los que debe seleccionar e instalar, luego de dar clic en la opción install y dejar que pase un tiempo de 2 a 5 minutos máximo, para que instale el nodo lo vera como se encuentran en la siguiente imagen dentro del recuadro verde.

<img width="600" alt="6" src="https://user-images.githubusercontent.com/50923637/70659066-58f86000-1c2d-11ea-8a89-5505af47e1d6.png">

Luego de haber instalado el nodo usted debe importar el archivo json que esta dentro del repositorio, llamado **Demo_raspberry**, Para importar el archivo usted debe acceder al **menú de hamburguesa**, selccionar la opción **import** y luego seleccionar la opción dentro de import **clipboard**.

<img width="600" alt="7" src="https://user-images.githubusercontent.com/50923637/70661030-6a436b80-1c31-11ea-9457-c5aa6b67cc63.png">

Después de paso anterior vera la siguiente imagen donde usted debe dar clic en **select a file to import**, buscara donde tiene su archivo **json Demo_raspberry** lo selecciona y finalmente da clic en **import**.

<img width="600" alt="8" src="https://user-images.githubusercontent.com/50923637/70661058-78918780-1c31-11ea-9e54-d4f5b597304b.png">

Luego de importar el json, podrá ver la siguiente configuración de nodos, donde ya esta en el nodo naranja de **function** vera la función correspondiente al envió de un 1 o un 0 según corresponda a la condición de temperatura dada dentro del mismo nodo, a su vez en el *nodo azul claro que tiene el símbolo de raspberry* puede seleccionar que pin va a ser el de salida para la activación del diodo led que usted implemento en la salida.

<img width="600" alt="9" src="https://user-images.githubusercontent.com/50923637/70661060-7a5b4b00-1c31-11ea-92eb-b5b63af97340.png">

Luego debe acceder a uno de los nodos de **IoT Watson platform** en este caso se accedió al que está arriba de nodo de función y se configura como **Quickstart** dando clic en la opción, este por defecto asigna un ID.

<img width="600" alt="10" src="https://user-images.githubusercontent.com/50923637/70661065-7cbda500-1c31-11ea-8a86-86ad4e5031c5.png">

luego usted debe acceder al otro nodo, donde usted debe seleccionar la opcion de **Registered**, accede a la modificaciones del nodo y dentro de ellas deberá ingresar los datos de **Device type**, **Device ID**, **Organization** y el **Auth Token**, estos datos los obtiene del dispositivo creado en la plataforma de Watson IoT platform.

<img width="600" alt="11" src="https://user-images.githubusercontent.com/50923637/70661070-7e876880-1c31-11ea-816d-006c10fb46a4.png">

Ahora para ver el resultado del nodo de Quickstart vera que esta resaltado en un recuadro rojo usted da clic en él y automática mente abre una ventana emergente donde vera el siguiente dashboard.

<img width="600" alt="11" src="https://user-images.githubusercontent.com/50923637/70661378-1dac6000-1c32-11ea-9444-df379bf587b2.png">

Si usted ingreso correctamente los datos en el nodo de Watson IoT platform usted vera una imagen como la siguiente dentro de su servicio, donde podrá verificar que este conectado el dispositivo y si accede a la opción de sucesos reciente vera que se está realizando el envío de las medidas de temperatura a su servicio.

<img width="600" alt="19" src="https://user-images.githubusercontent.com/50923637/70664475-754dca00-1c38-11ea-9ff2-87c748b6e7c5.png">

<img width="600" alt="11" src="https://user-images.githubusercontent.com/50923637/70661716-e5595180-1c32-11ea-8e78-e3d3cfd76a82.png">

Luego de realizar la verificación usted debe acceder a la sección de paneles del servicio de Watson IoT platform, donde usted puede crear la visualización de tarjetas a su gusto, en este caso en la sección de tarjetas llamada dash están alojadas dos formas de ver los datos que previamente cree.

<img width="600" alt="13" src="https://user-images.githubusercontent.com/50923637/70661945-51d45080-1c33-11ea-9690-759c3d03f5c1.png">

Finalmente podrá ver los dashboards donde el primero es un grafico en el cual están las medidas de temperatura en un tiempo delimitado y el segundo esta la medida actual de temperatura tomada.

<img width="600" alt="14" src="https://user-images.githubusercontent.com/50923637/70662246-da52f100-1c33-11ea-9032-8bbf2ffe1188.png">

### Explicación de la aplicación.

La aplicación consta de tomar la temperatura ambiente de un lugar por medio del sensor de temperatura DS18B20, luego ese dato por medio de la raspberry Pi enviarlo a Node-red y visualizar los datos de forma local, luego hacer una función en Node-red que dependiendo la temperatura encienda o apague un led según corresponda haciendo la simulación de la activación y desactivación de un sistema correspondiente a la temperatura actual registrada, finalmente se envían los datos a la plataforma de Watson IoT platform y se visualizan los datos en la forma Quickstart que ofrece el servicio y la forma monitoreable y modificable en la propia plataforma seleccionando a opción Registered.

**A continuación, podrá ver la arquitectura básica de la aplicación y los posibles casos de uso que tiene.**

<img width="600" alt="15" src="https://user-images.githubusercontent.com/50923637/70662761-e68b7e00-1c34-11ea-9f1f-affe2827b915.png">

* El proyecto busca darse como una solución ante sistemas de regulación y monitoreo de temperaturas, dando como herramienta de monitoreo, revisión de datos y manejo de los mismo  la plataforma de Watson IoT platform de IBM, en la cual por medio de dashboards o de los sucesos recientes que registra el dispositivo.

<img width="600" alt="16" src="https://user-images.githubusercontent.com/50923637/70662895-2b171980-1c35-11ea-9a7c-f25ece017c0b.png">
