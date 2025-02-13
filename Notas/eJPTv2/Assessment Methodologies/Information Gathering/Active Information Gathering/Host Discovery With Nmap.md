Podemos usar NMAP, para intentar descubrir todos los hosts/equipos conectados a una red.

Para esto usaremos un escaneo de ping con NMAP

-sn: Sin escaneo de puertos

```shell
sudo nmap -sn 192.168.18.0/24
```