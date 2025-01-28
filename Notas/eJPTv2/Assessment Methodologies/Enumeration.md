La enumeración es el proceso de reunir información activamente sobre una red objetivo, como sus dispositivos, sistemas y servicios

[WHOIS](https://es.wikipedia.org/wiki/WHOIS): es un protocolo TCP basado en petición/respuesta para efectuar consultas en una base de datos que permite determinar el propietario de un nombre de dominio o una dirección IP en Internet.

[NetCraft](https://www.netcraft.com/?utm_feeditemid=&utm_device=c&utm_term=netcraft&utm_source=google&utm_medium=ppc&utm_campaign=Google+%7C+Search+%7C+Brand+%7C+Exact+%7C+20221014&hsa_cam=18600605269&hsa_grp=150893442948&hsa_mt=p&hsa_src=g&hsa_ad=689927749890&hsa_acc=4527524350&hsa_net=adwords&hsa_kw=netcraft&hsa_tgt=kwd-514047883912&hsa_ver=3&gad_source=1&gclid=CjwKCAiAnKi8BhB0EiwA58DA4cM03ASHqUwuu_Y3_olqaeQb_ENPJbayUCUFhZrpUNpGhM71kUqNRxoCYmQQAvD_BwE): Netcraft es un sitio web que proporciona información sobre otros sitios web, incluidos detalles como la dirección IP, el sistema operativo del servidor web y el servidor DNS.

[DNS Recon](https://byte-mind.net/dns-enumeration-tecnicas-y-herramientas/): es el acto de detectar y enumerar todos los registros DNS posibles.
	[DNSRECON.](https://kali-linux.net/article/dnsrecon/): También es una herramienta ya instalada en KaliLinux, a continuación un ejemplo de uso.

```shell
dnsrecon -d ejemplo.com
```

[DNSDUMPSTER](https://dnsdumpster.com/): Es una herramienta para rastrear y explorar el historial de registros DNS de un dominio especifico, podemos descubrir con ella hosts relacionados con un dominio.

[WAF](https://es.wikipedia.org/wiki/Web_application_firewall): Un WAF es un Firewall de aplicaciones web. [WAFWOOF](https://github.com/EnableSecurity/wafw00f), nos permite poder obtener información acerca de estos mismos.

```shell
wafw00f ejemplo.com
```

[Subdomain Enumeration](https://medium.com/@rajeevranjancom/subdomain-enumeration-2d5c80a14d32): Es el proceso usado para identificar todos los subdominios de un dominio. En este caso usaremos la herramienta [Sublist3r](https://github.com/aboul3la/Sublist3r), indicar que al no estar interactuando activamente con el objetivo, esto no es un ataque de fuerza bruta, la información se recopila de fuentes publicas ([OSINT](https://es.wikipedia.org/wiki/Inteligencia_de_fuentes_abiertas)) Usa buscadores como: Google, Bing, Yahoo etc.., también usa Netcraft, Virustotal, ThreatCrowd, DNSdumpster y  ReverseDNS.

Instalar y usar sublist3r:

```shell
sudo apt-get install sublist3r
```

Ejemplo de uso:

Indicar que por ejemplo Google, limita las solicitudes que se realizan, para que no nos bloquee podemos usar una VPN.
```shell
sublist3r -d hackersploit.org -e google,yahoo
```

[Email Harvesting](https://es.wikipedia.org/wiki/Recopilaci%C3%B3n_de_direcciones_de_correo_electr%C3%B3nico#:~:text=La%20recolecci%C3%B3n%20o%20raspado%20de,correo%20electr%C3%B3nico%20masivo%20o%20spam.): Consiste en obtener la mayor cantidad de correos electrónicos para usarlos en una futura de prueba de pen testing.
Podemos usar herramientas como: [theHarvester](https://github.com/laramies/theHarvester), esta herramienta usa información de fuentes públicas igual que sublist3r.

```shell
theHarvester -d hackersploit.org -b google;linkedin
theHarvester -d HackerSploit -b google;linkedin
```