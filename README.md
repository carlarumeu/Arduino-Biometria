# Proyecto Arduino: Medidor de Gas y Temperatura

Este proyecto implementa un sistema para medir la concentración de ozono (O3) y temperatura utilizando un Arduino. Utiliza varias clases para organizar la lógica, incluyendo la lectura de sensores, la publicación de datos mediante Bluetooth Low Energy (BLE), y la gestión de LEDs.

## Tabla de Contenidos

- [Requisitos](#requisitos)
- [Configuración del Proyecto](#configuración-del-proyecto)
- [Clases](#clases)
  - [LED](#led)
  - [Medidor](#medidor)
  - [Publicador](#publicador)
  - [PuertoSerie](#puerto-serie)
  - [ServicioEnEmisora](#servicio-en-emisora)
- [Uso](#uso)
- [Contribuciones](#contribuciones)

## Requisitos

- *Hardware*:
  - Arduino (cualquier modelo compatible)
  - Sensor de ozono
  - Sensor de temperatura (opcional)
  - Módulo BLE
  - LED (opcional)

- *Software*:
  - Arduino IDE
  - Biblioteca BLE (dependiendo del módulo utilizado)

## Configuración del Proyecto

1. *Conectar los Sensores*: Asegúrate de conectar el sensor de ozono y el sensor de temperatura a los pines adecuados en tu Arduino.
2. *Configurar el Módulo BLE*: Conecta el módulo BLE y verifica que esté correctamente configurado para comunicarse con el Arduino.
3. *Instalar Bibliotecas*: Asegúrate de instalar todas las bibliotecas necesarias para el BLE y cualquier otra que pueda ser requerida por los sensores.

## Clases

### LED
Esta clase gestiona el control de un LED conectado al Arduino. Incluye métodos para encender, apagar, alternar su estado y hacer que brille durante un tiempo específico.

#### Métodos:
- encender(): Enciende el LED.
- apagar(): Apaga el LED.
- alternar(): Cambia el estado del LED.
- brillar(long tiempo): Enciende el LED por un tiempo determinado.

### Medidor
Esta clase se encarga de leer los valores de los sensores de gas y temperatura.

#### Métodos:
- iniciarMedidor(): Configura los pines para los sensores.
- medirGas(): Lee la concentración de ozono y devuelve el valor calibrado en ppm.
- medirTemperatura(): Devuelve una temperatura de ejemplo (a modificar según el sensor utilizado).

### Publicador
Esta clase se encarga de publicar los datos de las mediciones a través del módulo BLE.

#### Métodos:
- encenderEmisora(): Activa la emisora BLE.
- publicarCO2(double valorCO2, uint8_t contador, long tiempoEspera): Publica los datos de CO2.
- publicarTemperatura(int16_t valorTemperatura, uint8_t contador, long tiempoEspera): Publica los datos de temperatura.

### PuertoSerie
Esta clase permite la comunicación a través del puerto serie.

#### Métodos:
- esperarDisponible(): Espera a que el puerto serie esté disponible.
- escribir(T mensaje): Envía un mensaje a través del puerto serie.

### ServicioEnEmisora
Esta clase gestiona el servicio BLE y las características relacionadas.

#### Métodos:
- activarServicio(): Activa el servicio BLE y sus características.
- anyadirCaracteristica(Caracteristica& car): Añade una característica al servicio.

## Uso

1. Carga el código en tu Arduino utilizando el Arduino IDE.
2. Abre el puerto serie para ver las mediciones en tiempo real.
3. Asegúrate de que el módulo BLE esté encendido y funcionando.
4. Observa las lecturas de ozono y temperatura en el monitor serie.

## Contribuciones

Las contribuciones son bienvenidas. Si deseas contribuir, por favor, haz un fork del repositorio y envía un pull request.

## Licencia

Este proyecto está licenciado bajo la MIT License. Para más detalles, consulta el archivo LICENSE.

Hecho con :heart: por Elena Ruiz De La Blanca
