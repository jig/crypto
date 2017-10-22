# Introducción a la criptografía

Transparencias en [jig.github.io/crypto/es](https://jig.github.io/crypto/es), pero puedes acceder directamente a cada capítulo seleccionando los enlaces en el apartado "Contenido".

## Contenido

  - [Índice](https://jig.github.io/crypto/es) `8`
  - [Objetivos](https://jig.github.io/crypto/es/objectives.html) `25`
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
  - [Amenazas](http://jig.github.io/crypto/threats.html) `15` (&Sigma; → `118`)
  - [HSM](https://jig.github.io/crypto/es/hsm.html) `41` 
  - [Conexiones (TLS)](http://jig.github.io/crypto/tls.html) `11`
  - [Infraestructura de Clave Pública (PKI)](http://jig.github.io/crypto/pki.html) `59` (&Sigma; → `111`)

Nota: el número a la derecha de cada entrada indic el número (aproximado) de transparencias.  

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
