### **Network Mapping:**

### ¿### ¿Qué es?

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