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

|**Capa**|**Descripción**|**Ejemplo**|
|---|---|---|
|**Capa 7: Aplicación**|Proporciona servicios de red a las aplicaciones del usuario (por ejemplo, navegadores web).|HTTP (navegar por la web), FTP (transferencia de archivos)|
|**Capa 6: Presentación**|Se encarga de la representación de datos (formato, cifrado, compresión).|Cifrado SSL/TLS, formato JPEG, compresión ZIP|
|**Capa 5: Sesión**|Establece, mantiene y finaliza las sesiones de comunicación entre aplicaciones.|Protocolo SMB (para compartir archivos), RPC (llamadas a procedimientos remotos)|
|**Capa 4: Transporte**|Asegura la transferencia fiable de datos entre sistemas, controlando el flujo y la corrección de errores.|TCP (transporte fiable de datos), UDP (transporte sin conexión)|
|**Capa 3: Red**|Se encarga del enrutamiento y direccionamiento de datos a través de diferentes redes.|Protocolo IP, Routers|
|**Capa 2: Enlace de Datos**|Proporciona la comunicación de datos entre dispositivos en la misma red, y controla los errores de transmisión.|Ethernet, Wi-Fi, MAC (dirección de hardware)|
|**Capa 1: Física**|Transmite los bits a través del medio físico de transmisión (cables, ondas, etc.).|Cable de red (Ethernet), ondas de radio (Wi-Fi), fibra óptica
