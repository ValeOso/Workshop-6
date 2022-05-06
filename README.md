# Workshop # 6 Automatización

Integrantes:
Brayan David Acosta Gomez y Valentina Osorio Lopez

## [](https://github.com/Dacosta011/Workshop6#identificaci%C3%B3n-del-modelo-basico-iot)Identificación del modelo basico IOT

### [](https://github.com/Dacosta011/Workshop6#sensor)Sensor

El BME280 es un sensor digital combinado de humedad, presión y temperatura basado en pruebas principios sensoriales. El BME280 logra un alto rendimiento en todas las aplicaciones que requieren humedad y presión medición. Estas aplicaciones emergentes de control domótico, navegación interior, fitness como así como el refinamiento del GPS requieren una alta precisión y un TCO bajo al mismo tiempo.  [![enter image description here](https://camo.githubusercontent.com/ace5b50edeedf6946e0094dc6787f77d5f7e8e6e5634ed59e5f9d4c8fa58f6db/68747470733a2f2f7469656e64612e627269636f6765656b2e636f6d2f363732322d746869636b626f785f64656661756c742f73656e736f722d64652d74656d70657261747572612d68756d656461642d792d70726573696f6e2d626d653238302e6a7067)](https://camo.githubusercontent.com/ace5b50edeedf6946e0094dc6787f77d5f7e8e6e5634ed59e5f9d4c8fa58f6db/68747470733a2f2f7469656e64612e627269636f6765656b2e636f6d2f363732322d746869636b626f785f64656661756c742f73656e736f722d64652d74656d70657261747572612d68756d656461642d792d70726573696f6e2d626d653238302e6a7067)

### [](https://github.com/Dacosta011/Workshop6#embedded-system)Embedded System

#### [](https://github.com/Dacosta011/Workshop6#hardware)Hardware

Para el sistema iot básico que se utiliza en la simulación se evidencian ciertos componentes físicos necesarios para el desarrollo del ejercicio de lectura de humedad y presión por parte de un sensor. Dichos elementos constan de:

-   Protoboard
-   Sensor BME 280
-   Diodo Led
-   cables de conexión

#### [](https://github.com/Dacosta011/Workshop6#software)Software

Una vez identificado el hardware que se está utilizando para la simulación, es necesario conocer el software utilizado y necesario para hacer la programación de los dispositivos físicos mencionados anteriormente y más impórtate, como recolectar los datos y enviarlos a un servicio externo para su manipulación. Dicho software es:

-   Lenguaje de programación Nodejs
-   Librería wiring-pi (Manejo de pines Raspberry pi)
-   Librería de conexión a azure IOT
-   Librería para el manejo del protocolo MQTT
-   Libreria bme280 (lectura del sensor)
-   Plataforma cloud Azure

### [](https://github.com/Dacosta011/Workshop6#conectivity)Conectivity 
Para la trasmisión de datos conformamos la conectividad basados en el siguiente modelo de comunicación dividido en 3 capas las cuales son Comunicación Física, Protocolo de comunicación y Protocolo de Aplicación.

<img width="1195" alt="Captura de Pantalla 2022-05-05 a la(s) 10 32 48 p m" src="https://user-images.githubusercontent.com/74270748/167066663-23ee03d8-a7ea-475d-b033-498213ae835f.png"> "The Connectivity' - Tomado de los recursos clase de Automatización.


- Comunicación física:  Tras conectar el sensor de temperatura BME280 a la Raspberry Pi satisfactoriamente se requiere contar con una conexión física vía puerto Ethernet por medio del cable micro USB a la red de internet y por ende a la fuente de poder.
- Protocolo de comunicación: En este caso el protocolo de comunicación correspondiente a la conectividad física es IP (Internet Protocol) necesaria para identificar / poder acceder a la interfaz de la Raspberry y a su vez que esta logre conexión a internet por medio del PC con el fin de poder localizar otros dispositivos de la red.
- Protocolo de Aplicación: Finalmente en la capa de aplicación contamos con el protocolo MQTT que es usado frecuentemente para microconntroladores pequeños con recursos de hardware limitados como en la configuración presentada.  Además que cuenta con la compatibilidad con la plataforma de Raspberry Pi y diferentes proveedores de servicios en la nube como Azure que permiten una comunicación bidireccional permitiendo así al sector de IOT tener una transmisión de datos de parte del dispositivo como de la nube de forma más sencilla y asincrónica entre los clientes (dispositivos como el microcontrolador) y el editor.

### [](https://github.com/Dacosta011/Workshop6#data-analytic)Data analytic
Las tecnologías de IoT proporcionan volúmenes de datos inmensos que son necesarios de procesos con herramientas especializadas para convertidor los datos en información útil; por esta razón el uso de comoponentes como "IoT Hub" pues puede recopilar rápidamente los datos de cada dispositivo y con ayuda de otro de los componentes llamado "Azure Stream Analytics" lograr entrar información de los flujos de datos como por ejemplo patrones o relaciones que previamente podrán ser almacenas en "Azure SQL Database" donde los analistas y usuarios finales pueden ver a través de una interfaz web. 
## [](https://github.com/Dacosta011/Workshop6#simulaci%C3%B3n-del-modelo)Simulación del modelo

Para el proceso de simulación IOT, se hizo uso de la plataforma de simulación de raspberry pi que ofrece la nube de azure. Dicho simulador, está diseñado para capturar información de un sensor, enviarla hacia la plataforma de azue IOT y encender un actuador led dependiendo de las condiciones especificadas en el código.

Para realizar este proceso fueron necesarios una serie de pasos para hacer la conexión y envio de datos entre el simulador y la plataforma de IOT.

1.  Crear un centro de IoT en Azure
2.  Registrar un nuevo dispositivo en el centro de IoT
3.  Ejecutar la aplicación de prueba con el simulador
4.  Lea los mensajes recibidos por el servicio

Una vez realizados los pasos pertinentes se obtuvo el siguiente resultado en el simulado.

[![enter image description here](https://raw.githubusercontent.com/Dacosta011/Workshop6/main/ledOn.png)](https://raw.githubusercontent.com/Dacosta011/Workshop6/main/ledOn.png)

Como se puede observar, el actuador led empezó a encender con respecto al comportamiento que se esperaba respecto a la programación anterior. Además, por medio de la consola se empezó a observar la información que se estaba ejecutando y enviando al servicio de IOT.

[![enter image description here](https://raw.githubusercontent.com/Dacosta011/Workshop6/main/message.png)](https://raw.githubusercontent.com/Dacosta011/Workshop6/main/message.png)

Concluyendo así la simulación de la comunicación entre un dispositivo físico como lo es la raspberry pi y un servicio de gestión y analítica de datos generados por dispositivos IOT como el que ofrece Azure con IOT hub, de manera satisfactoria.
