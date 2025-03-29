# IoT for Smart Ventilation - Proyecto de Ventilación Inteligente para Cultivo de Rosas en Colombia

## Descripción del Proyecto
Este proyecto busca implementar un sistema de ventilación inteligente para la industria de la floricultura en Colombia, específicamente para el cultivo de rosas. Aprovechando el Internet de las Cosas (IoT) y la inteligencia artificial (IA), se planea optimizar el control del clima, específicamente la ventilación, mediante el uso de datos provenientes de sensores ambientales (temperatura, humedad y consumo de energía). Este sistema permitirá la automatización del control del aire, reduciendo el consumo de energía y mejorando la eficiencia operativa en condiciones rurales con conectividad limitada.

## Objetivos

**Objetivo General:** Diseñar y desarrollar un piloto de infraestructura IoT que integre datos de sensores, automatización mediante IA y monitoreo remoto en tiempo real para mejorar la eficiencia energética en la ventilación de cultivos de rosas en Colombia.

**Objetivos Específicos:**
1. Desarrollar un Producto Mínimo Viable (MVP) que integre adquisición de sensores, procesamiento local con IA y conectividad a la nube para reducir el consumo de energía comparado con los sistemas tradicionales de ventilación.
2. Implementar una plataforma de monitoreo remoto para asegurar una disponibilidad teórica del 99% de los datos en tiempo real a través de una aplicación web/móvil.
3. Recoger retroalimentación de los stakeholders durante la fase final del proyecto para asegurar la satisfacción en términos de eficiencia energética y usabilidad.

## Uso de MQTT en el Proyecto

**¿Qué es MQTT?**

MQTT (Message Queuing Telemetry Transport) es un protocolo de mensajería liviano y eficiente, ideal para aplicaciones IoT debido a su bajo consumo de ancho de banda y su capacidad para funcionar en redes con baja conectividad. Gracias a su arquitectura basada en la publicación y suscripción, es ampliamente utilizado para la transmisión de datos entre dispositivos conectados de manera confiable y segura, incluso en entornos de red inestables.

**¿Para qué se usó MQTT?**

En este proyecto, MQTT se utilizó para la transmisión de datos entre los sensores de monitoreo ambiental (temperatura, humedad, voltaje, corriente) y el sistema de control centralizado. Los sensores recogen los datos del entorno y los envían a través de un cliente MQTT al gateway central, que los retransmite hacia los servidores finales para su almacenamiento y análisis.

**¿Por qué se usó MQTT?**

La eficiencia de MQTT lo hace una opción ideal para redes con capacidad limitada, como las de zonas rurales de Colombia. Su bajo consumo de energía lo convierte en la solución perfecta para dispositivos IoT alimentados por baterías. Además, permite la transmisión de datos en tiempo real, lo cual es esencial para el control de la ventilación, que debe adaptarse rápidamente a las condiciones cambiantes del ambiente. Su modelo de publicación/suscripción garantiza una comunicación confiable y eficiente, además de ser fácilmente escalable, lo que facilita la integración de más sensores y dispositivos a medida que el sistema crece.

## Infraestructura del Proyecto

> ![Infraestrutura en Cisco Packet Tracer](https://github.com/Edwinguty2/cisco/blob/main/infra.png)

La red fue diseñada usando Cisco Packet Tracer, simulando una infraestructura completa para la transmisión de datos entre sensores y servidores a través de MQTT.

### Tipo de red y topología:
La red es híbrida, combinando elementos de red de área local (LAN) y red de área amplia (WAN). Los sensores IoT están conectados a un dispositivo central (SBC) que transmite los datos a través de un gateway hacia la red local. Esta red local se conecta a internet mediante un módem de cable, permitiendo que los dispositivos remotos, como smartphones, accedan a los datos a través de Wi-Fi o redes móviles (torre celular). Los routers y servidores gestionan la transmisión y almacenamiento de datos, permitiendo tanto el monitoreo local como el acceso remoto. El tipo de red es híbrida, y como se puede ver en la imagen, la topología también lo es, ya que en un extremo es tipo estrella y se conecta a otras ramas generadas después de que sale a internet. que integra comunicaciones locales y remotas para la visualización y control en tiempo real de los sensores.

### Detalles de la Infraestructura de Comunicación
A continuación, se describen los componentes clave en el recorrido:
- **Sensores:** Capturan datos de temperatura, humedad y consumo de energía. Estos sensores envían la información a través de MQTT hacia el gateway central.
- **Single Board Computer (SBC):** Actúa como el intermediario entre los sensores y el MQTT Client, simulando una Raspberry Pi en la red y procesando los datos de los sensores para dar partida a la trasmisión.
- **MQTT Client:** Este cliente es responsable de publicar los datos de los sensores en el servidor MQTT suscrito. El modelo de publicación/suscripción asegura que solo los dispositivos necesarios reciban los datos, permitiendo un control remoto y local eficiente.
- **Gateway:** Además de transmitir los datos hacia el router, el gateway permite la conexión directa con los dispositivos locales (monitores de temperatura y humedad, y dispositivos móviles), para visualizar y controlar los datos.
- **Servidor:** El servidor recibe los datos transmitidos por MQTT y los almacenan para su análisis, esto utiliza el MQTT Broker. Los usuarios pueden monitorear y controlar el sistema en tiempo casi real a través de este, con acceso remoto a la información y control sobre el sistema de ventilación. Además, se pueden controlar todos los clientes desde aquí, demostrando seguridad en el control de los dispositivos que deben tener dicha información.

## Validación del Sistema

La validación del sistema se realizó mediante una demostración práctica en video. En el video, se muestra que los dispositivos conectados al MQTT Client reciben los datos en tiempo real. Se demuestra que en diferentes dispositivos (como monitores y dispositivos móviles), el cliente MQTT suscrito está correctamente configurado y puede recibir los datos enviados por los sensores. Además, se valida el funcionamiento del servidor al mostrar cómo este reconoce los dispositivos conectados y confirma la llegada de los datos.  
También se realizó una prueba de conexión en la que se mostró cómo un monitor, al introducir la contraseña del gateway, se conecta correctamente y comienza a recibir los datos de manera instantánea. Esta demostración asegura que la infraestructura funciona correctamente, validando tanto la transmisión de datos como la capacidad de control remoto y local.

## Referencias:
["IOT", HexHub. Disponible en: https://www.youtube.com/playlist?list=PLmolNWplRhQS1r5PdbInurvoX0MdQ7U2F. [Accedido: 27-Mar-2025].)



## Contributors
- **Edwin Alejandro Gutierrez Rodriguez**  
- **Nicolas Stiven Ortiz Cortes**  
- **Juan Díego Lemus Rey**  
- **Universidad de La Sabana**
