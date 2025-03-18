## Protocolos de red

- En las redes informáticas, los hosts se comunican unos con otros usando los protocolos de red.
- Los protocolos de red aseguran que los diferentes sistemas informáticos se comuniquen aunque tengan diferente hardware y software.
- Hay un gran número de protocoles de red utilizados por diferentes servicios para objetivos y funcionalidades diferentes.
- La comunicación entre diferentes host vía protocolos es facilitada mediante el uso paquetes.

## Paquetes

- El objetivo principal de una red es el intercambio de información entre los equipos que la conforman; esta información es transferida mediante paquetes.
- Los paquetes son un flujo de bits "corriendo", como una señal eléctrica en un medio físico como puede ser (Ethernet, WIFI etc).
- Esas señales eléctricas son interpretadas como bits, (ceros y unos), y componen la información.

Cada paquete en cada protocolo tiene la siguiente estructura:
- Cabecera: La cabecera tiene una estructura especifica del protocolo: esto asegura que el host que lo recibe puede interpretar el payload.
- Payload: Es la información actual que esta siendo enviada. Puede ser algo como por ejemplo una parte de un email o el contenido de un archivo mientras se esta descargando.

## OSI MODEL

- El modelo OSI (Open System Interconnection), es un marco conceptual que estandariza las funciones de una telecomunicación o un sistema informático compuesto por 7 capas.
- Este fue desarrollado por la Organización Internacional de Normalización (ISO), para facilitar la comunicación entre los diferentes sistemas y dispositivos, asegurando la operabilidad y comprensión en una amplia gama de tecnologías de red.
- El modelo OSI esta dividido en 7 capas, cada una representa una funcionalidad especifica en el proceso de la comunicación de red.

| **Capa**                    | **Descripción**                                                                                                 | **Ejemplo**                                                                      |
| --------------------------- | --------------------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------- |
| **Capa 7: Aplicación**      | Proporciona servicios de red a las aplicaciones del usuario (por ejemplo, navegadores web).                     | HTTP (navegar por la web), FTP (transferencia de archivos)                       |
| **Capa 6: Presentación**    | Se encarga de la representación de datos (formato, cifrado, compresión).                                        | Cifrado SSL/TLS, formato JPEG, compresión ZIP                                    |
| **Capa 5: Sesión**          | Establece, mantiene y finaliza las sesiones de comunicación entre aplicaciones.                                 | Protocolo SMB (para compartir archivos), RPC (llamadas a procedimientos remotos) |
| **Capa 4: Transporte**      | Asegura la transferencia fiable de datos entre sistemas, controlando el flujo y la corrección de errores.       | TCP (transporte fiable de datos), UDP (transporte sin conexión)                  |
| **Capa 3: Red**             | Se encarga del enrutamiento y direccionamiento de datos a través de diferentes redes.                           | Protocolo IP, Routers                                                            |
| **Capa 2: Enlace de Datos** | Proporciona la comunicación de datos entre dispositivos en la misma red, y controla los errores de transmisión. | Ethernet, Wi-Fi, MAC (dirección de hardware)                                     |
| **Capa 1: Física**          | Transmite los bits a través del medio físico de transmisión (cables, ondas, etc.).                              | Cable de red (Ethernet), ondas de radio (Wi-Fi), fibra óptica                    |
## NETWORK LAYER

- La [capa de red](https://www.azion.com/es/learning/network-layer/que-es-la-capa-de-red/#:~:text=La%20capa%20de%20red%2C%20tambi%C3%A9n,y%20el%20reenv%C3%ADo%20de%20paquetes.) (capa 3): se encarga de permitir la conexión entre dispositivos que están ubicados en redes diferentes.
- Su principal función es determinar el camino más optimo de los datos desde donde se envían hasta el receptor, incluso si los dispositivos se encuentran en diferentes redes.
- La capa de red abstrae la red física subyacente, lo que permite la creación de una interconexión de redes cohesiva.

##### **Protocolos de la capa de red:**

- [Protocolo de internet](https://es.wikipedia.org/wiki/Protocolo_de_internet#:~:text=El%20protocolo%20de%20internet%20(en,seg%C3%BAn%20el%20modelo%20internacional%20OSI.&text=env%C3%ADo%20de%20paquetes%20de%20datos,como%20a%20trav%C3%A9s%20de%20redes.) (IP):La IP es el protocolo principal en la capa de red, responsable del direccionamiento lógico y el enrutamiento. Define la estructura de las direcciones IP y cómo se asignan a los dispositivos. La IP también especifica el formato de los paquetes de datos, incluyendo los campos de encabezado que contienen información como las direcciones de origen y destino, la longitud del paquete y las banderas de fragmentación.
- 
	- IPv4: Usa 32 bits
	- IPv6: Creado para las limitaciones del ipv4 usa 128
	
- [Internet Control Message Protocol](https://es.wikipedia.org/wiki/Protocolo_de_control_de_mensajes_de_Internet) (ICMP): El ICMP (Internet Control Message Protocol) es un protocolo de apoyo utilizado para reportar errores y propósitos de diagnóstico. Define varios tipos de mensajes, como solicitud/respuesta de eco (utilizado por ping), destino inalcanzable, tiempo excedido y mensajes de redirección. El ICMP ayuda a los administradores de red a solucionar problemas de conectividad e identificar problemas de red.
- [Cabecera IP:](https://es.wikipedia.org/wiki/Cabecera_IP)

## TRANSPORT LAYER

La [capa de transporte](https://es.wikipedia.org/wiki/Capa_de_red) en el modelo OSI (Open Systems Interconnection) es la cuarta capa y su principal función es proporcionar la comunicación de datos de extremo a extremo entre sistemas o dispositivos. Se encarga de asegurar que los datos enviados desde la capa de aplicación lleguen correctamente a la aplicación de destino.

### Funciones clave de la capa de transporte:

1. **Segmentación y Reensamblaje**: La capa de transporte divide los datos en segmentos más pequeños para enviarlos a través de la red, y luego reensambla esos segmentos en el destino.

2. **Control de flujo**: Regula la cantidad de datos que se pueden enviar para evitar la saturación del receptor.

3. **Control de errores**: Proporciona mecanismos para detectar y corregir errores en la transmisión, asegurando que los datos lleguen correctamente al destino.

4. **Establecimiento, mantenimiento y terminación de la conexión**: Establece una comunicación confiable, gestionando el inicio y la finalización de las conexiones entre los dispositivos.

5. **Multiplexación**: Permite que múltiples aplicaciones o procesos se comuniquen de forma simultánea utilizando la misma conexión de red, identificando cada flujo de datos mediante puertos.

### Protocolos comunes:

- **TCP (Transmission Control Protocol)**: Ofrece una comunicación confiable, controlando la entrega de los datos de manera ordenada y asegurando que no se pierdan ni lleguen duplicados.

	1. **Orientado a la conexión**: TCP establece una conexión antes de la transferencia de datos (handshake). Esto asegura que ambos extremos de la comunicación estén listos antes de que los datos se envíen.

	2. **Confiabilidad**: Garantiza que los datos lleguen correctamente, realizando la verificación de errores, retransmisión de paquetes perdidos y asegurando el orden correcto de los paquetes.

	3. **Control de flujo**: Regula la cantidad de datos que se pueden enviar para evitar que el receptor se sobrecargue.
 
	4. **Control de congestión**: Ajusta la velocidad de transmisión para evitar la sobrecarga de la red.

	5. **Retransmisión en caso de pérdida de datos**: Si un paquete se pierde durante la transmisión, TCP lo detecta y lo vuelve a enviar.

	6. **Orientado a la fiabilidad**: Es ideal para aplicaciones donde la pérdida de datos no es aceptable, como la navegación web (HTTP/HTTPS), correo electrónico (SMTP), transferencia de archivos (FTP), etc.

El **TCP 3-way handshake** (o **apretón de manos de 3 vías** en español) es el proceso utilizado por el protocolo TCP (Transmission Control Protocol) para establecer una conexión confiable entre dos dispositivos antes de que se transmita cualquier dato. Este proceso garantiza que ambas partes estén listas para la comunicación y establece los parámetros de la conexión.

El 3-way handshake se compone de tres pasos:

1. SYN (Synchronize):

- El dispositivo que inicia la conexión (cliente) envía un segmento TCP con el **SYN flag** activado a la máquina destino (servidor). Este segmento indica que el cliente desea establecer una conexión.
- Este paso también incluye un número de secuencia inicial que se usará en la transmisión de datos.

2. SYN-ACK (Synchronize-Acknowledge):

- El servidor recibe el segmento SYN del cliente y responde con un segmento que tiene activados los flags **SYN** y **ACK** (Acknowledgment).
- El **SYN** indica que el servidor está dispuesto a establecer una conexión, y el **ACK** es una confirmación de que ha recibido el SYN del cliente.
- El servidor también envía su propio número de secuencia inicial para la conexión.

3. ACK (Acknowledge):

- Finalmente, el cliente responde con un segmento **ACK** (Acknowledgment) al servidor, confirmando que ha recibido el SYN-ACK del servidor. Este mensaje no lleva el flag SYN, solo el flag ACK.
- Después de este paso, la conexión se establece y ambos dispositivos pueden comenzar a intercambiar datos de forma confiable.

Resumen del proceso:

1. **Cliente → Servidor**: Envia un **SYN** (solicitud de conexión).
2. **Servidor → Cliente**: Responde con **SYN-ACK** (confirmación de conexión).
3. **Cliente → Servidor**: Responde con un **ACK** (confirmación final de conexión).

Este proceso garantiza que ambos dispositivos estén listos para la comunicación antes de que e envíen los datos, lo que permite que se maneje correctamente cualquier error de conexión o pérdida de paquetes.

- **UDP (User Datagram Protocol)**: Un protocolo sin conexión y sin garantía de entrega, pero más rápido que TCP, adecuado para aplicaciones que no requieren fiabilidad como transmisión de video o voz.

	1. **Sin conexión**: UDP no establece una conexión antes de enviar datos, lo que lo hace más rápido pero menos confiable.

	2. **Sin garantía de entrega**: No asegura que los datos lleguen al destino, ni garantiza el orden o la integridad de los paquetes.

	3. **Sin control de flujo ni control de congestión**: No hay mecanismos para regular la velocidad de envío ni evitar la sobrecarga de la red.

	4. **Más rápido y eficiente**: Al no requerir la configuración de conexión y no realizar comprobaciones adicionales de errores o control de flujo, UDP es más rápido y tiene menos sobrecarga que TCP.

	5. **Adecuado para aplicaciones en tiempo real**: Ideal para aplicaciones donde la velocidad es crucial y se puede tolerar cierta pérdida de datos, como en transmisión de video, voz sobre IP (VoIP), juegos en línea y servicios de transmisión en vivo.


| Característica            | **TCP**                                                       | **UDP**                                      |
| ------------------------- | ------------------------------------------------------------- | -------------------------------------------- |
| **Conexión**              | Orientado a la conexión                                       | Sin conexión                                 |
| **Fiabilidad**            | Alta, con verificación y retransmisión                        | Baja, sin garantía de entrega                |
| **Orden de los paquetes** | Asegurado                                                     | No asegurado                                 |
| **Control de flujo**      | Sí                                                            | No                                           |
| **Control de congestión** | Sí                                                            | No                                           |
| **Velocidad**             | Más lento debido a la verificación                            | Más rápido debido a la falta de verificación |
| **Usos comunes**          | Navegación web, correo electrónico, transferencia de archivos | Streaming, VoIP, juegos en línea             |

En resumen, la capa de transporte es crucial para asegurar una comunicación efectiva y confiable entre aplicaciones de sistemas diferentes, gestionando la fiabilidad y el control de los datos. 