## Port Scanning con NMAP

El siguiente comando realiza lo siguiente:

```bash
nmap 10.4.24.205
```

- Verifica si el host está **activo** (vivo).
- Escanea los **puertos TCP más comunes** (los primeros 1,000).
- Indica qué **puertos están abiertos**, cerrados o filtrados.
- Muestra el **nombre del servicio** asociado a cada puerto (como `ssh`, `http`, etc.).

```bash
nmap -Pn 10.4.24.205
```

#### ¿Qué significa `-Pn`?

- Le dice a Nmap que **no intente detectar si el host está activo** (es decir, **omite el ping**).
- Asume que el host **está encendido** y pasa directo al escaneo de puertos.
#### ¿Cuándo se usa?

- Cuando el objetivo **bloquea los pings (ICMP)** o no responde.
- Útil en redes con **firewalls o filtros** que ocultan hosts inactivos.
- También se usa en **auditorías de seguridad**, para asegurarte de que escaneas el host sí o sí.

```bash
nmap -Pn -F 10.4.24.205
```

`-F` (Fast scan):  Hace un escaneo **rápido**, solo revisa **los 100 puertos más comunes** (según el archivo `nmap-services`).

```bash
nmap -Pn -p80 10.4.24.205
```

`-p 80`:   Escanea **solo el puerto 80** (HTTP).

```bash
nmap -Pn -p80,445,3389 10.4.24.205
```
  
`-p 80,445,3389`:   Escanea los puertos indicados.

```bash
nmap -Pn -p1-100 10.4.24.205
```

`-p1-100`:  Escanea los **puertos del 1 al 100** (especificás un rango).

```bash
nmap -T4 -Pn -p- 10.4.24.205
```

- `-T4`:  Aumenta la **velocidad del escaneo** (modo rápido/agresivo, sin ser riesgoso).  (Va de `-T0` a `-T5`, donde `T4` es buena para escaneos rápidos sin levantar demasiadas alertas).
- `-Pn`:  **No hace ping**, asume que el host está activo.
- `-p-`:   Escanea **todos los 65,535 puertos TCP** (¡no solo los comunes!).