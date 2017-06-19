# Introducción a la criptografía

Transparencias en [jig.github.io/crypto/es](https://jig.github.io/crypto/es)

_Transparències en català a [jig.github.io/crypto](https://jig.github.io/crypto)_

## Contenido

  - [Índice](https://jig.github.io/crypto/es) `8`
  - [Introducción, historia](https://jig.github.io/crypto/es/intro.html) `40`
  - [Criptografía simétrica](https://jig.github.io/crypto/es/symmetric.html) `91`
  - [MAC](https://jig.github.io/crypto/es/mac.html) `11`
  - [Hash, HMAC, cifrado autenticado](https://jig.github.io/crypto/es/hash.html) `13` (&Sigma; → `150`)
  - [Teoría de números](https://jig.github.io/crypto/es/number-theory.html) `33`
  - [Acuerdo de claves Diffie-Hellman](https://jig.github.io/crypto/es/dh.html) `9`
  - [RSA](https://jig.github.io/crypto/es/rsa.html) `23`
  - [DSA](https://jig.github.io/crypto/es/dsa.html) `15`
  - [Criptografía de curva elíptica](https://jig.github.io/crypto/es/ecc.html) `18`  
  - [Complejidad algorítmica](http://jig.github.io/crypto/complexity.html) `5`
  - [Amenazas](http://jig.github.io/crypto/threats.html) `15`
  - [HSM](https://jig.github.io/crypto/es/hsm.html) `41` (&Sigma; → `159`)
  - [Conexiones (TLS)](http://jig.github.io/crypto/tls.html) `11`
  - [Infraestructura de Clave Pública (PKI)](http://jig.github.io/crypto/pki.html) `59`
  - [Advanced Electronic Signatures (AdES)](http://jig.github.io/crypto/ades.html) `17` (&Sigma; → `87`)

### Resumen
  
  - [Resumen](http://jig.github.io/crypto/es/abstract.html) de los objetivos de las funciones criptográficas y de las responsabilidades de las autoridades PKI `8`
  
## Calendario, Enero 2017

 24           | 26                |
--------------|-------------------|
 Objetivos    | ~~MAC~~           | 
 Introducción | HMAC              |
 Simétrica    | Teoría de Números |
         

 30        | 2-febrero |
-----------|-----------|  
DH         |ECC        | 
RSA        |Complejidad|  
Elgamal    |Amenazas   |  
DSA        |HSM        |

 6         | 9
---------- | ---------------- 
 HSM       | (ejercicios → PKI/servidor-https/cliente-https)
 TLS       | 
 PKI       | 
 ~~AdES~~  |

## Ejercicios (a realizar en clase en función del tiempo)
  - Criptografía simétrica:
      - bloques de un sólo uso [Gimp](https://www.gimp.org) (_one-time-pad_ para uso pedagógico exclusivamente)
      - criptografía simétrica con OpenSSL:
          - xifrat (amb `openssl enc`)
          - hash (amb `openssl dgst`)
          - mac (amb `openssl dgst -hmac`)
    
  - Criptografía asimétrica:
    - generar claves RSA (con `openssl genrsa`) y ECDSA (con `openssl ecparam` y `openssl ec`)
        - parsear, convertir (con `openssl rsa`, con `openssl ec`)
    - firmar y validar RSA (con `openssl rsautil`)
    - cifrar y descifrar (con `openssl rsautil`)
        
  - PKI      
    - decodificación DER en [lapo.it](https://lapo.it/asn1js/)
    - decodificación X.509 en [Cert Logik](https://certlogik.com/decoder/)
    - decodificación X.509 con OpenSSL Tools
    - criptografía formateada en PKCS #7 con OpenSSL:
    
  - PKI TLS
      - conexiones ssh (con `ssh`/`sshd`; contraejemplo no-PKI) 
        - gestión de claves, protección y confianza
      - validar tls/https (con [`cipherscan`](https://github.com/jig/docker-cipherscan))
      - validar tls/https (con [SSL labs](https://www.ssllabs.com/ssltest/))
      - conexiones tls/https (chrome → google.com)
      - conexiones tls/https (chrome → servidor propio certificado con [Let's Encrypt CA](https://letsencrypt.org))
        - certificación con [Let's Encrypt CA](https://letsencrypt.org) para servidores HTTPS públicos
      - conexiones tls/https (chrome → servidor propio)
        - servidor (con `nginx`)
        - cliente (con `openssl s_client` y/o Chrome)
          - certificación con la CA [PKI tutorial](https://pki-tutorial.readthedocs.io/en/latest/) (variante) para servidores corporativos/privados
          - CA, TLS Server preconfigurados a:

```
$ docker run --name CAROOT -ti jordi/caroot
$ docker run --name CASUBOR -p 443:443 -ti jordi/casubor
$ docker run --name NGINX -p 443:443 -ti jordi/nginx
$ docker run --name CLIENT -p 443:443 -ti jordi/client
```

Código fuente de las imágenes de estos contenedores en el proyecto [github.com/jig/docker-openssl](https://github.com/jig/docker-openssl)

# Software utilizado para realizar las transparencias

  - [Reveal.js](https://github.com/hakimel/reveal.js): formateo, paginación
  - [MathJax](https://www.mathjax.org) ([LaTeX](http://latex-project.org)): para presentar las ecuaciones
  - [SVG-edit](https://github.com/SVG-Edit/svgedit): para mostrar gráficos vectoriales
  
## Impresión
  
Si quieres imprimir las transparencias no hagas `Ctrl+P` directamente. Mejor utilizada un "template" específico para impresión añadiendo `?print-pdf` a la URL antes de imprimir. para más información consulta las 
[instrucciones de exportación a PDF de Revealjs](https://github.com/hakimel/reveal.js/#pdf-export)

Piensa en el medio ambiente.

## Descarga local

Aunque lo más recomendable es acceder a la versión en línea para ver siempre la versión actualizada, si quieres puedes descargarte las transparencias para visualizarlas fuera de línea.
Simplemente aprieta el botón `Download ZIP` de arriba o bien clica 
[aquí](https://codeload.github.com/jig/crypto/archive/master.zip). 

O si tienes cuenta en GitHub puedes simplemente un `fork` (botón de arriba a la derecha), aunque no las voy a borrar a medio plazo, con lo que si simplemente marcas con una estrella tendrás un recordatorio en tu cuenta de donde residen para cuando las necesites.

O también, puedes clonar el proyecto en tu disco duro local (necesitas un cliente `git`):

```
$ git clone git@github.com:jig/crypto.git
```

de esta manera tienes una copia local que siempre puedes mantener al día con:

```
$ git pull
```

# Licencia

Esta obra esta sujeta a una licencia de [Atribución 4.0 Internacional de Creative Commons](http://creativecommons.org/licenses/by/4.0/)

[![Licencia de Creative Commons](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

Copyright © 2016-2017 [Jordi Íñigo Griera](https://github.com/jig)
