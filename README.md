# Introducció a la criptografia

Transparències a [jig.github.io/crypto](https://jig.github.io/crypto)

  - [Índex](https://jig.github.io/crypto) (7)
  - [Introducció, història](https://jig.github.io/crypto/intro.html) (39)
  - [Criptografia simètrica](https://jig.github.io/crypto/symmetric.html) (80)
  - [MAC](https://jig.github.io/crypto/mac.html) (11)
  - [Hash, HMAC, xifrat autenticat](https://jig.github.io/crypto/hash.html) (13) -> (150)
  - [Teoria de nombres](https://jig.github.io/crypto/number-theory.html) (33)
  - [Acord de claus Diffie-Hellman](https://jig.github.io/crypto/dh.html) (9)
  - [RSA](https://jig.github.io/crypto/rsa.html) (18)
  - [DSA](https://jig.github.io/crypto/dsa.html) (15)
  - [Criptografia de corba el·líptica](https://jig.github.io/crypto/ecc.html) (12*)  -> (97)
  - [HSM](https://jig.github.io/crypto/hsm.html) (41)
  - [Connexions (TLS...)](http://jig.github.io/crypto/tls.html) (11)
  - [Infraestructura de Clau Pública (PKI)](http://jig.github.io/crypto/pki.html) (59)
  - [Advanced Electronic Signatures (AdES)](http://jig.github.io/crypto/ades.html) (17)  -> (128)

Exercicis:

  - bloc d'un sol ús amb [Gimp](https://www.gimp.org) (_one-time-pad_)
  - criptografia simètrica amb OpenSSL:
    - xifrat (amb `openssl enc`)
    - hash (amb `openssl dgst`)
    - mac (amb `openssl dgst -hmac`)
  - criptografia asimètrica amb OpenSSL:
    - generar claus RSA (amb `openssl genrsa`) i ECDSA (amb `openssl ecparam` i `openssl ec`)
      - parsejar, convertir (amb `openssl rsa`, amb `openssl ec`)
    - signar i validar RSA (amb `openssl rsautil`)
    - xifrar i desxifrar (amb `openssl rsautil`)
  - decodificació DER a [lapo.it](https://lapo.it/asn1js/)
  - decodificació X.509 a [Cert Logik](https://certlogik.com/decoder/)
  - decodificació X.509 amb OpenSSL Tools
  - connexions ssh (amb `ssh/d`)
  - validar tls/https (amb [`cipherscan`](https://github.com/jig/docker-cipherscan))
  - validar tls/https (amb [SSL labs](https://www.ssllabs.com/ssltest/))
  - connexions tls/https (chrome -> google)
  - connexions tls/https (chrome -> servidor propi certificat amb OpenSSL CA)
  - connexions tls/https (chrome -> servidor propi certificat amb [Let's Encrypt CA](https://letsencrypt.org))

# Programari utilitzat

[reveal.js](https://github.com/hakimel/reveal.js): per a realitzar les transparències
[MathJax](https://www.mathjax.org) ([LaTeX](http://latex-project.org)): per a presentar les equacions
[SVG-edit](https://github.com/SVG-Edit/svgedit): per a dibuixar gràfics vectorials

# Llicència

Aquesta obra està subjecta a una llicència de [Reconeixement 4.0 Internacional de Creative Commons](http://creativecommons.org/licenses/by/4.0/)

[![Llicència de Creative Commons](https://i.creativecommons.org/l/by/4.0/88x31.png)](http://creativecommons.org/licenses/by/4.0/)

Copyright © 2016 [Jordi Íñigo Griera](https://github.com/jig)
