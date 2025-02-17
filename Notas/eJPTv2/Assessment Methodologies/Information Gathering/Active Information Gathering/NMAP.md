**Host Discovery With Nmap**

Podemos usar NMAP, para intentar descubrir todos los hosts/equipos conectados a una red.

Para esto usaremos un escaneo de ping con NMAP

-sn: Sin escaneo de puertos

```shell
sudo nmap -sn 192.168.18.0/24
```

**Port Scanning With Nmap**

Podemos usar NMAP, intentar descubrir que puertos tiene abierto los hosts de una red, asi como servicios ejecuta etc.

- **nmap 127.0.0.1** - Escaneo por defecto, a veces windows bloquea los pings.
- **nmap -Pn 127.0.0.1** - Indicamos que escanea los 1000 puertos mas usados sin revisar que el host tenga conexión o no.
- **nmap -Pn -p- 127.0.0.1** - Indicamos que escanea los 65000 puertos sin revisar que el host tenga conexión o no.
- **nmap -Pn -p 80,443 127.0.0.1** - - Indicamos que escanee los puertos indicados.
- **nmap -Pn -p1-1000 127.0.0.1** - - Indicamos que escanee desde el puerto 1 hasta el 1000.
- **nmap -Pn -F  127.0.0.1** - Con la opción -F escaneará solo los 100 primeros puertos.
- **nmap -Pn -sU  127.0.0.1** - Escanea puertos UDP.
- **nmap -Pn -F  127.0.0.1 -v** - Verbose, muestra las acciones que va realizando.
- **nmap -Pn -F -sV  127.0.0.1** - -sV nos muestra la versión de servicios detectados.
- map -Pn -F -sV -O  127.0.0.1** - -O nos muestra la versión del sistema operativo.
-  map -Pn -F -sV -O -sC 127.0.0.1** - -sC ejecuta una lista de scripts de nmap, para obtener más información acerca de los puertos.