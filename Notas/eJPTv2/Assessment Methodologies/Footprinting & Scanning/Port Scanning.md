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