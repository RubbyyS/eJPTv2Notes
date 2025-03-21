[**Google hacking**](https://es.wikipedia.org/wiki/Google_Hacking), también llamado **Google dorking**, es una técnica en informática que utiliza operadores para filtrar información en el buscador de Google

Si queremos ampliar y conseguir más dorks podemos acceder a esta web: https://www.exploit-db.com/google-hacking-database, que nos permitirá ver más dorks que nos pueden venir bien al enumerar a nuestro objetivo.
### Operadores básicos de Google Dorking:

1. **`site:`**  
    Limita los resultados a un dominio o sitio web específico.  
    Ejemplo:
    
    - `site:example.com` → Busca solo dentro de example.com.
    - `site:*.example.com` → Busca subdominios de example.com.
    - `site:.gov` → Busca en sitios web con dominio `.gov`.
1. **`intitle:`**  
    Busca una palabra o frase dentro del título de una página.  
    Ejemplo:
    
    - `intitle:login` → Encuentra páginas que tienen "login" en el título.
3. **`allintitle:`**  
    Busca múltiples palabras dentro del título de una página.  
    Ejemplo:
    
    - `allintitle:admin login` → Encuentra páginas que tienen "admin" y "login" en el título.
4. **`inurl:`**  
    Busca una palabra o frase dentro de la URL de una página.  
    Ejemplo:
    
    - `inurl:admin` → Encuentra páginas con "admin" en la URL.
5. **`allinurl:`**  
    Busca múltiples palabras dentro de la URL de una página.  
    Ejemplo:
    
    - `allinurl:login.php` → Encuentra páginas con "login" y "php" en la URL.
6. **`filetype:`**  
    Limita la búsqueda a archivos de un tipo específico (PDF, DOC, XLS, etc.).  
    Ejemplo:
    
    - `filetype:pdf "seguridad informática"` → Encuentra documentos PDF sobre seguridad informática.
7. **`ext:`**  
    Similar a `filetype:`, busca archivos con una extensión particular.  
    Ejemplo:
    
    - `ext:xls budget` → Encuentra archivos de Excel con la palabra "budget".
8. **`intext:`**  
    Busca palabras o frases específicas en el cuerpo del texto de una página.  
    Ejemplo:
    
    - `intext:"contraseña predeterminada"` → Busca páginas que contengan "contraseña predeterminada" en el texto.
9. **`allintext:`**  
    Busca varias palabras dentro del cuerpo del texto.  
    Ejemplo:
    
    - `allintext:usuario contraseña` → Encuentra páginas que contengan ambas palabras en el texto.
10. **`cache:`**  
    Muestra la versión en caché de una página web guardada por Google.  
    Ejemplo:
    
    - `cache:example.com` → Muestra la versión en caché de example.com.

### Operadores de búsqueda avanzada:

1. **`related:`**  
    Encuentra sitios web relacionados con un dominio específico.  
    Ejemplo:
    
    - `related:example.com` → Encuentra sitios relacionados con example.com.
2. **`link:`**  
    Muestra las páginas que enlazan a una URL específica.  
    Ejemplo:
    
    - `link:example.com` → Encuentra páginas que enlazan a example.com.
3. **`define:`**  
    Busca definiciones de una palabra o término.  
    Ejemplo:
    
    - `define:phishing` → Encuentra la definición de phishing.
4. **`AROUND(X)`**  
    Encuentra palabras o frases que están cercanas entre sí, donde `X` es la distancia máxima de palabras entre ellas.  
    Ejemplo:
    
    - `"seguridad informática" AROUND(5) "contraseñas"` → Encuentra páginas donde "seguridad informática" y "contraseñas" están a una distancia máxima de 5 palabras.
