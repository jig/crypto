# Introducción a la criptografía

Transparencias en [jig.github.io/crypto/es](https://jig.github.io/crypto/es), pero puedes acceder directamente a cada capítulo seleccionando los enlaces en el apartado "Contenido".

## Contenido UPC 2019-1-10,14,15

En el curso 2019-01 _no entrarán_ los paquetes de transparencias marcados como opcionales en este índice de aquí debajo.

  - OPCIONAL [Índice](https://jig.github.io/crypto/es) `8`
  - [Objetivos](https://jig.github.io/crypto/es/objectives.html) `25` 
  - [Introducción, historia](https://jig.github.io/crypto/es/intro.html) `40`
  - OPCIONAL [Criptografía simétrica, AES](https://jig.github.io/crypto/es/symmetric.html) `91` (&Sigma; → `126`) ([AES y modos de operación](https://jig.github.io/crypto/es/symmetric.html#aes), resto OPCIONAL)
  - OPCIONAL [Hash, HMAC, cifrado autenticado](https://jig.github.io/crypto/es/hash.html) `13`  
  - OPCIONAL [MAC](https://jig.github.io/crypto/es/ecbc-mac.html) `11` 
  - [Teoría de números](https://jig.github.io/crypto/es/number-theory.html) `33`
  - [Acuerdo de claves Diffie-Hellman](https://jig.github.io/crypto/es/dh.html) `9`
  - [RSA](https://jig.github.io/crypto/es/rsa.html) `23`
  - OPCIONAL [DSA](https://jig.github.io/crypto/es/dsa.html) `15`
  - OPCIONAL [Criptografía de curva elíptica](https://jig.github.io/crypto/es/ecc.html) `18`  
  - [Complejidad algorítmica](http://jig.github.io/crypto/es/complexity.html) `5` (&Sigma; → `127`)
  - OPCIONAL [Amenazas](http://jig.github.io/crypto/es/threats.html) `15` 
  - OPCIONAL [RND y HSM](https://jig.github.io/crypto/es/hsm.html) `41` 
  - [Conexiones (TLS)](http://jig.github.io/crypto/es/tls.html) `11`
  - [Infraestructura de Clave Pública (PKI)](http://jig.github.io/crypto/es/pki.html) `59` (&Sigma; → `126`)
  - OPCIONAL Certificación de un servidor con Let's Encrypt

**Nota**: el número a la derecha de cada entrada indica el número de transparencias aproximado

### OPCIONAL: práctica OpenSSL

Material para los ejercicios prácticos **opcionales** comentados en la sesión síncrona del martes 7 de Noviembre de 2017: [jig/docker-openssl](https://github.com/jig/docker-openssl)

### Resumen
  
  - [Resumen](http://jig.github.io/crypto/es/abstract.html) de los objetivos de las funciones criptográficas y de las responsabilidades de las autoridades PKI `8`
  
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

# Software utilizado para realizar las transparencias

  - [Reveal.js](https://github.com/hakimel/reveal.js): formateo, paginación
  - [MathJax](https://www.mathjax.org) ([LaTeX](http://latex-project.org)): para presentar las ecuaciones
  - [SVG-edit](https://github.com/SVG-Edit/svgedit): para mostrar gráficos vectoriales
  
## Impresión
  
Si quieres imprimir las transparencias no hagas `Ctrl+P` directamente. Mejor utilizada un "template" específico para impresión añadiendo 

```
?print-pdf 
``` 
a la URL antes de imprimir. 

Para más información consulta las 
[instrucciones de exportación a PDF de Revealjs](https://github.com/hakimel/reveal.js/#pdf-export).

Piensa en el medio ambiente.

# Licencia

Esta obra esta sujeta a una licencia de [Atribución 4.0 Internacional de Creative Commons](http://creativecommons.org/licenses/by/4.0/)

[![Licencia de Creative Commons](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

Copyright © 2016-2017 [Jordi Íñigo Griera](https://github.com/jig)
