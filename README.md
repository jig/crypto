# Introducció a la criptografia

Transparències a [jig.github.io/crypto](https://jig.github.io/crypto)

## Contingut

  - [Índex](https://jig.github.io/crypto) `7`
  - [Introducció, història](https://jig.github.io/crypto/intro.html) `38`
  - [Criptografia simètrica](https://jig.github.io/crypto/symmetric.html) `81`
  - [MAC](https://jig.github.io/crypto/mac.html) `11`
  - [Hash, HMAC, xifrat autenticat](https://jig.github.io/crypto/hash.html) `13` → `150`
  - [Teoria de nombres](https://jig.github.io/crypto/number-theory.html) `33`
  - [Acord de claus Diffie-Hellman](https://jig.github.io/crypto/dh.html) `9`
  - [RSA](https://jig.github.io/crypto/rsa.html) `23`
  - [DSA](https://jig.github.io/crypto/dsa.html) `15`
  - [Criptografia de corba el·líptica](https://jig.github.io/crypto/ecc.html) `18`  
  - [Complexitat algorísmica](http://jig.github.io/crypto/complexity.html) `5`
  - [Amenaces](http://jig.github.io/crypto/threats.html) `15`
  - [HSM](https://jig.github.io/crypto/hsm.html) `41` → `159`
  - [Connexions (TLS)](http://jig.github.io/crypto/tls.html) `11`
  - [Infraestructura de Clau Pública (PKI)](http://jig.github.io/crypto/pki.html) `59`
  - [Advanced Electronic Signatures (AdES)](http://jig.github.io/crypto/ades.html) `17` → `87`
  
## Resum
  
  - [Resum](http://jig.github.io/crypto/abstract.html) dels objectius de les funcions criptogràfiques i de les responsabilitats de les autoritats PKI `8`
  
## Exercicis realitzats l'penúltim dia (26 de gener de 2016)

  - `ssh` i `sshd`: gestió de claus, protecció i confiança
  - certificació amb [Let's Encrypt CA](https://letsencrypt.org)) per a servidors HTTPS públics
  - certificació amb la CA [Simple PKI tutorial](https://pki-tutorial.readthedocs.org/en/latest/simple/index.html) (variant) per servidors corporatius/privats
    - CA, TLS Server preconfigurats a:
    
        ```
        $ docker run --name ROOT -ti jordi/openssl-ca
        $ docker run --name SERVER -p 443:443 -ti jordi/openssl-tlsserver
        ```
        
    - Codi font de les imatges d'aquests contenidors al projecte [github.com/jig/docker-openssl](https://github.com/jig/docker-openssl)

## Exercici realitzat l'últim dia (8 de febrer de 2016)

Aquí: [PRACTICA.md](./PRACTICA.md)

## Exercicis opcionals
  - Criptografia simètrica:
    - bloc d'un sol ús amb [Gimp](https://www.gimp.org) (_one-time-pad_)
    - criptografia simètrica amb OpenSSL:
        - xifrat (amb `openssl enc`)
        - hash (amb `openssl dgst`)
        - mac (amb `openssl dgst -hmac`)
  
  - Criptografia asimètrica:
    - generar claus RSA (amb `openssl genrsa`) i ECDSA (amb `openssl ecparam` i `openssl ec`)
        - parsejar, convertir (amb `openssl rsa`, amb `openssl ec`)
    - signar i validar RSA (amb `openssl rsautil`)
    - xifrar i desxifrar (amb `openssl rsautil`)
        
  - PKI      
    - decodificació DER a [lapo.it](https://lapo.it/asn1js/)
    - decodificació X.509 a [Cert Logik](https://certlogik.com/decoder/)
    - decodificació X.509 amb OpenSSL Tools
    - criptografia amb PKCS #7 amb OpenSSL:
    
  - PKI TLS
      - connexions ssh (amb `ssh/d`; contraexemple no-PKI) 
      - validar tls/https (amb [`cipherscan`](https://github.com/jig/docker-cipherscan))
      - validar tls/https (amb [SSL labs](https://www.ssllabs.com/ssltest/))
      - connexions tls/https (chrome → google)
      - connexions tls/https (chrome → servidor propi certificat amb OpenSSL CA)
        - servidor (amb `openssl s_server`)
        - client (amb `openssl s_client`)
      - connexions tls/https (chrome → servidor propi certificat amb [Let's Encrypt CA](https://letsencrypt.org))

## Calendari, gener 2016

 18        | 19               | 21
---------- | ---------------- | -------
 intro     | MAC              | RSA
           | HMAC             | Elgamal
           |                  | DSA
           |                  | 
           |                  | ECC
 symmetric | Teoria de Nombres| Complexitat
           | DH               | Amenaces


 25        | 26               
---------- | ---------------- 
 Amenaces  |
 HSM       | PKI
 TLS       | AdES
           |
 PKI       | (exercici → servidor HTTPS)
 
## Calendari, febrer 2016
 8                  |                
------------------- | ----- 
  [pràctica HTTPS](./PRACTICA.md)  |
  

# Programari utilitzat

  - [Reveal.js](https://github.com/hakimel/reveal.js): per a realitzar les transparències
  - [MathJax](https://www.mathjax.org) ([LaTeX](http://latex-project.org)): per a presentar les equacions
  - [SVG-edit](https://github.com/SVG-Edit/svgedit): per a dibuixar gràfics vectorials
  
## Impressió de les transparències
  
Si vols imprimir les transparències no facis `Ctrl+P` directament. Cal fer servir un template específic
per a impressió afegint `?print-pdf` a la URL abans d'imprimir. Per a més informació consulta les 
[instruccions d'exportació a PDF de Revealjs](https://github.com/hakimel/reveal.js/#pdf-export)

## Descàrrega local

Encara que el més recomenable és accedir a la versió en línia per a veure'n sempre una versió actualitzada, 
si vols pots descarregar les transparències per a visualitzar-les fora de línia. 
Simplement apreta el botó `Download ZIP` de dalt o pica 
[aquí](https://codeload.github.com/jig/crypto/archive/master.zip). 

O si tens compte a GitHub pots fer simplement un `fork` (botó a dalt de tot a la dreta).

O també, pots fer un `clon` local al teu disc dur (et cal un client `git`):

```
$ git clone git@github.com:jig/crypto.git
```

d'aquesta maneres tens còpia local que pots actualitzar amb:

```
$ git pull
```

# Llicència

Aquesta obra està subjecta a una llicència de [Reconeixement 4.0 Internacional de Creative Commons](http://creativecommons.org/licenses/by/4.0/)

[![Llicència de Creative Commons](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

Copyright © 2016 [Jordi Íñigo Griera](https://github.com/jig)
