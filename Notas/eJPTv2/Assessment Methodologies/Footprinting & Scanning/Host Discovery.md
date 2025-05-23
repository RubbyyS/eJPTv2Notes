### **Network Mapping:**

### ¿Qué es?

- **Network mapping** en pentesting es el proceso de identificar y mapear dispositivos, servicios y configuraciones de una red con el fin de encontrar vulnerabilidades que puedan ser explotadas durante una prueba de penetración.

---

### Objetivos en Pentesting:

1. **Descubrimiento de dispositivos**: Identificar hosts activos en la red.
2. **Detección de servicios**: Encontrar servicios y puertos abiertos en los dispositivos.
3. **Evaluación de la topología**: Entender la estructura y las conexiones de la red para identificar posibles vectores de ataque.
4. **Reconocimiento**: Recopilar información valiosa sobre la red sin interactuar directamente con los sistemas.

---

### Elementos Clave:

1. **Dispositivos**: Routers, switches, servidores, estaciones de trabajo, firewalls.
2. **Conexiones**: Puertos abiertos, redes internas, VPN, conexiones inalámbricas.
3. **Servicios**: Identificar qué servicios están activos en los dispositivos (HTTP, FTP, SSH, etc.).
4. **Direcciones IP y Subredes**: Localización de dispositivos en la red y segmentación de la infraestructura.

---

### Técnicas Comunes:

1. **Escaneo de Puertos**: Utilizar herramientas como **Nmap**, **Masscan** para identificar puertos abiertos y servicios activos.
2. **Escaneo de Vulnerabilidades**: Herramientas como **Nessus** o **OpenVAS** para buscar fallos de seguridad conocidos en los servicios detectados.
3. **Mapeo de Topología**: Analizar cómo están conectados los dispositivos y cómo se distribuye la red usando **Zenmap** o **Netcat**.
4. **Reconocimiento Pasivo**: Obtener información sin interactuar con los sistemas, utilizando herramientas como **Shodan** o consultando bases de datos públicas.

---

### Herramientas Comunes:

1. **Nmap**: Para escaneo de puertos y descubrimiento de servicios.
2. **Masscan**: Para escaneo de puertos a gran escala.
3. **Wireshark**: Para análisis de tráfico de red y captura de paquetes.
4. **Netcat**: Para crear conexiones de red y explorar servicios de forma manual.
5. **Zenmap**: Interfaz gráfica de Nmap para facilitar el mapeo.

---

### Aplicaciones en Pentesting:

- **Reconocimiento inicial**: Obtener una visión general de la red antes de atacar.
- **Escaneo de puertos**: Identificar servicios vulnerables que puedan ser explotados.
- **Enumeración de servicios**: Buscar versiones de servicios y posibles fallos en la configuración de seguridad.
- **Explotación de vulnerabilidades**: Utilizar la información del mapeo para planificar y realizar ataques dirigidos.

##### **NMAP**

**Nmap** es una herramienta de código abierto utilizada para explorar redes y realizar auditorías de seguridad. Se emplea principalmente para escanear puertos, descubrir dispositivos activos en la red y detectar servicios que están corriendo en esos dispositivos. En el contexto de **pentesting**, Nmap es esencial durante la fase de reconocimiento, ya que permite obtener información clave sobre la infraestructura de red, como puertos abiertos, sistemas operativos y versiones de servicios, lo que ayuda a identificar posibles vulnerabilidades y puntos de ataque.

**Funcionalidades de Nmap:**

1. **Escaneo de puertos**:
    
    - Detecta puertos abiertos en dispositivos de la red, tanto **TCP** como **UDP**.
2. **Descubrimiento de hosts**:
    
    - Identifica dispositivos activos en una red (ping scan).
3. **Detección de servicios**:
    
    - Mapea los servicios que están corriendo en los puertos abiertos, como **HTTP**, **FTP**, **SSH**, etc.
4. **Detección de sistemas operativos**:
    
    - Intenta identificar el sistema operativo y la versión del dispositivo objetivo mediante técnicas de huellas digitales.
5. **Detección de versiones**:
    
    - Obtiene información detallada sobre las versiones de los servicios que están en ejecución.
6. **Escaneo de redes completas**:
    
    - Permite escanear rangos completos de direcciones IP o subredes para descubrir dispositivos y servicios a gran escala.
7. **Análisis de seguridad**:
    
    - Detecta vulnerabilidades conocidas y configuraciones erróneas en los servicios y dispositivos descubiertos.
8. **Escaneo de puertos ocultos**:
    
    - Utiliza técnicas avanzadas para descubrir puertos que están "ocultos" o que no responden con los métodos de escaneo tradicionales.
9. **Escaneo de Firewalls y filtrado de paquetes**:
    
    - Evalúa si hay firewalls u otros dispositivos de seguridad que bloquean ciertos puertos o tráfico.
10. **Scriptable interactions (NSE)**:

    - Nmap tiene un **motor de scripts** (NSE) que permite automatizar pruebas de seguridad, como la detección de vulnerabilidades o la explotación de configuraciones incorrectas en los servicios.

Estas funcionalidades hacen de Nmap una herramienta versátil y poderosa para auditorías de seguridad y pruebas de penetración.


##### **HOST DISCOVERY:**

**Host Discovery** es el proceso de identificar qué dispositivos (hosts) están activos en una red, es decir, determinar qué sistemas están encendidos y respondiendo a las solicitudes de red. Este proceso es crucial en tareas de **reconocimiento** y **auditoría de redes**, ya que permite mapear los dispositivos de la infraestructura antes de realizar pruebas de penetración o análisis de seguridad.

### Técnicas de Host Discovery:

1. **Ping (ICMP Echo Request)**:
    
    - Enviar paquetes **ICMP Echo Request** (comúnmente conocido como "ping") a un rango de direcciones IP. Si el dispositivo está activo, responderá con un **ICMP Echo Reply**.
2. **Escaneo ARP (Address Resolution Protocol)**:
    
    - Utiliza **ARP** para descubrir dispositivos en redes locales. ARP solicita la dirección MAC de un dispositivo a partir de su dirección IP, lo que permite identificar hosts activos incluso si el ping está bloqueado.
3. **Escaneo TCP Connect**:
    
    - Intenta realizar una conexión TCP completa con los puertos más comunes (como el puerto 80, 443, etc.). Si el puerto responde, el host está activo.
4. **Escaneo de Puertos (SYN Scan)**:
    
    - En lugar de enviar un simple ping, se envía un paquete SYN (inicio de conexión) a los puertos y espera una respuesta de **SYN-ACK** si el puerto está abierto, indicando que el dispositivo está activo.
5. **Escaneo de ICMP Timestamp**:
    
    - Envía una solicitud de **ICMP Timestamp** para verificar si el dispositivo responde. Algunos dispositivos responden a estos paquetes con la fecha y hora del sistema, indicando que están activos.
6. **Escaneo de DNS**:
    
    - Realiza consultas **DNS** a un servidor para determinar si ciertos nombres de host están activos y si hay respuestas del servidor DNS, lo que sugiere que los dispositivos asociados están activos.
7. **Escaneo UDP**:
    
    - Envía paquetes **UDP** a puertos específicos y observa si hay respuestas, ya que algunos servicios UDP responden incluso si no se ha establecido una conexión completa.
8. **Escaneo de SMNP (Simple Network Management Protocol)**:
    
    - Utiliza **SNMP** para consultar información de red, como la lista de dispositivos activos, lo que puede ayudar a descubrir hosts.


### Ping Sweeps:

**Ping Sweep** (también conocido como **Ping Sweep Scan**) es una técnica utilizada en el descubrimiento de hosts en una red. Consiste en enviar paquetes **ICMP Echo Request** (pings) a un rango de direcciones IP para determinar cuáles están activas, es decir, qué dispositivos están respondiendo a los pings.
### ¿Cómo funciona el Ping Sweep?

1. Se envía un **ping** a varias direcciones IP dentro de un rango específico.
2. Si un dispositivo está activo y configurado para responder, enviará un **ICMP Echo Reply**.
3. Si no hay respuesta, el dispositivo puede estar apagado o estar bloqueando las respuestas ICMP (por ejemplo, debido a un firewall).

### Usos comunes del Ping Sweep:

- **Reconocimiento en Pentesting**: Se usa para identificar qué dispositivos están activos en una red antes de realizar otras pruebas de penetración.
- **Administración de redes**: Los administradores de redes utilizan esta técnica para verificar qué dispositivos están conectados y funcionando correctamente en su red.

### Limitaciones:

- Algunos dispositivos y redes bloquean o filtran paquetes ICMP para evitar que se detecten, lo que puede hacer que el Ping Sweep no sea 100% efectivo.

**Comando en Nmap para Ping Sweep**:

```bash
nmap -sn <rango de IP>
```

Este comando realizará un **ping sweep** a un rango de direcciones IP, sin realizar un escaneo de puertos, y solo indicará qué dispositivos están activos en la red.

### FPING

`fping` es una herramienta de red que permite hacer ping a múltiples direcciones IP de manera simultánea y más eficiente que el comando `ping`.

**Comando de ejemplo**:

Para hacer ping a varias direcciones IP:

```bash
fping 192.168.1.1 192.168.1.2 192.168.1.3
```

Esto enviará paquetes ICMP a las tres direcciones al mismo tiempo y mostrará los resultados.

Para hacer un "ping" a todos los equipos de una red usando `fping`, puedes usar una dirección de red con un rango de direcciones IP. Por ejemplo, si tu red es `192.168.1.0/24`, puedes hacer ping a todas las direcciones IP de esa red con el siguiente comando:

```bash
fping -g 192.168.1.0/24
```

- `-g`: Indica a `fping` que haga un "ping" a todas las direcciones IP en el rango especificado.

Este comando enviará paquetes ICMP a todas las direcciones IP en el rango `192.168.1.0` a `192.168.1.255` y te mostrará cuáles están activas.

Para hacer que `fping` indique únicamente los sistemas activos, puedes usar la opción `-a`, que muestra solo las direcciones IP que están respondiendo. Aquí tienes el comando:

```bash
fping -a -g 192.168.1.0/24
```

- `-a`: Muestra solo las direcciones IP que están activas (que responden al ping).
- `-g`: Permite hacer ping a todas las direcciones IP del rango especificado (en este caso, `192.168.1.0/24`).

Este comando te dará una lista de las direcciones IP activas en tu red.
### NMAP HOST DISCOVERY

Este comando **`nmap -sn 10.1.0.0/24`** busca qué dispositivos están **activos** en el rango de direcciones **10.1.0.0 a 10.1.0.255**.

El comando **`nmap -sn --send-ip 10.1.0.0/24`** realiza lo mismo que el comando anterior (escaneo de hosts activos en el rango **10.1.0.0 a 10.1.0.255**), pero con una diferencia importante:

- **`--send-ip`**: Esta opción le indica a **nmap** que envíe los paquetes de red directamente usando el protocolo **IP** (en lugar de utilizar otros protocolos de bajo nivel como **ICMP** o **ARP**). Esto puede hacer que el escaneo sea más rápido o eludir ciertas restricciones de firewall que bloquean los pings estándar.

El comando **`nmap -sn -iL ips.txt`** se utiliza para realizar un escaneo de hosts activos (sin escanear puertos) a partir de una lista de direcciones IP contenida en un archivo.

El comando **`nmap -sn -PS`** envía paquetes **SYN** al puerto 80 (por defecto) de los hosts en la red para verificar si están activos. Si el host responde con un **SYN-ACK**, significa que está activo.
Este tipo de escaneo es útil cuando un firewall o dispositivo de red bloquea **pings ICMP**, pero permite tráfico TCP en puertos específicos. El **TCP SYN Ping** puede eludir esos filtros y detectar dispositivos activos.

El comando **`nmap -sn -PS22`** realiza un **escaneo de hosts activos** en una red utilizando un **ping TCP SYN** dirigido al **puerto 22** (que es comúnmente utilizado para **SSH**).
Se puede cambiar el 22 por cualquier puerto.

El comando **`nmap -sn -v -T4 10.1.0.0/24`** realiza un **escaneo rápido** de **hosts activos** en el rango **10.1.0.0 a 10.1.0.255**.

- **`-sn`**: Verifica si los dispositivos están activos (sin escanear puertos).
    
- **`-v`**: Muestra información detallada durante el escaneo.
    
- **`-T4`**: Hace que el escaneo sea más rápido.