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