# Reloj multipropósito

Este será un reloj multipropósito que usara un MCU como algún ESP32, por su bajo costo y sus características como
bluetooth y wifi.

Quiero que se lo más compacto posible, así que el tamaño de la pantalla y el consumo de esta será una de las limitantes

Buscando en Aliexpress me encontré con las siguientes opciones 

|ID|Tipo de tecnología|Consumo (mAh) - Voltage (V)|Intefaz de comunicación|Tamaño|Precio|Resolución|
|-|-|-|-|-|-|-|
|1|TFT-LCD|95mAh-5v|UART|47,5mm de diámetro x 27,0mm de altura|371 MX|240px|
|2|Pantalla de papel electrónico Monocromo|0.15mAh|1.28in|574.29 MX 2 unidades| 128px|


## Links
1. https://es.aliexpress.com/item/1005005295747021.html
2. https://es.aliexpress.com/item/1005004555311346.html

## Botones
Para el control de las aplicaciones(modos de operación) es necesario contar con algún tipo de entradas,
Como en los relojes comunes, la hora se configura con botones.
Una de las opciones son botones capacitivos o microbotones como con los que cuentan los teléfonos

## Sensor touch capacitivo
Con base a este documento https://ww1.microchip.com/downloads/en/AppNotes/Capacitive-Touch-Sensor-Design-Guide-DS00002934-B.pdf
El tipo de arreglo de sensores que me parece mejor, es conocido como slide sensor, una buena forma de aplicarlo es con "Extend Interpolation"


## Puerto de programación
Para la programación de este reloj es por medio de comunicación UART.
Por lo cual es importante contar con un acceso rápido al puerto de programación
Para lograr un fácil acceso será con el uso de pogo pins o (springs pins)

## Consumo de ESP32 

|Modo|Consumo|
|-|-|
|Recomendado|500(mA)|
|deep sleep|7-8(uA)|
|light sleep|240(uA)|
|wifi|355mA|

Suponiendo que quisiera usarlo con wifi en alguna aplicación por 3 horas en un dia y con la pantalla encendida.
El consumo total sería=ESP32-500(mA)+Pantalla Monocromo(3.6mA)=503.6mAh
**Así que aproximadamente es necesario una batería de 1.5A**
Aunque aún se requiere comprobar los resultados
