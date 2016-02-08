# Pràctica 8 de febrer de 2016

Cal fer servir la imatge MacOS X amb [Docker Toolbox](https://www.docker.com/products/docker-toolbox).
Docker Toolbox instal·la els clients de Docker, el gestor de màquines virtuals d'Oracle VirtualBox, i 
la imatge de màquina virtual Boot2Docker.

Les imatges del laboratori de MacOS X ja tenen la instal·lació feta.

## Màquina virtual Boot2Docker

Per engegar la màquina virtual (Boot2Docker) feu:

```
$ docker-machine start default
```

al cap d'una estona podeu mirar el seu estat amb:

```
$ docker-machine ls
```

Per a fer servir Docker cal configurar vàries variables d'entorn (IP del Boot2Docker, etc.):

```
$ eval $(docker-machine env default)
```

(nota: si no et funciona aquesta instrucció, és (possiblement) que el shell que tens és `tcshell`. Fes servir `bash`)

## Descàrrega de contenidors

Primer mirem si tot funciona:

```
$ docker images
$ docker ps
```

La primera línia ens mostrarà les imatges Docker disponibles i la segona els contenidors creats a partir d'elles.
Probablement no n'hi hagi cap. Per a engegar un Ubuntu podem provar:

```
$ docker run -ti ubuntu bash
...
root@3f9f56657414:/# _ 
```

Si surt alguna cosa similar a això és que l'entorn funciona. Per baixar altres imatges sense engegarles cal fer servir `pull`:

```
$ docker pull ubuntu
```

Nosaltres farem servir les imatges del projecte [github.com/jig/docker-openssl](https://github.com/jig/docker-openssl). 
Podem baixar la base amb:
 
```
$ docker pull jordi/openssl-with-dhparams
```

Aquesta imatge està derivada d'Ubuntu (latest) i té el paquet openssl i té generat un generador Diffie-Hellman 
de 4096 bit. Aquest valor es pot compartir públicament (actualment es considera suficient 2048 bit).

### Canvis, on són?

Si feu canvis al contenidor, quan sortiu aparentment els predre (per sortir feu `^D` o `exit`) ja que si 
el torneu a engegar amb `docker run -ti ubuntu bash` en realitat n'esteu creant un de nou.

Per rearrancar un contenidor antic, el millor es posar-li nom:

```
$ docker run --name important -ti ubuntu bash
root@3f9f56657414:/# exit
$ docker start important
$ docker attach important
root@3f9f56657414:/# _
```

i hi trobareu tot com ho vàreu deixar.

Per saber quins contenidors teniu creats (i aturats) podeu fer servir:

```
$ docker ps -a
```

# Pràctica PKI

Crearem una CA, configurarem un `nginx` amb HTTPS i farem que només s'hi pugui entrar amb certificat 
de client (TLS amb autenticació mútua)

Aquesta pràctica està basada en el [Tutorial de PKI d'OpenSSL](https://pki-tutorial.readthedocs.org)
de l'Stefan H. Holek. En particular la [Simple PKI](https://pki-tutorial.readthedocs.org/en/latest/simple/).

La configuració TLS de l'nginx l'he fet a partir de [Strong SSL Security on nginx](https://raymii.org/s/tutorials/Strong_SSL_Security_On_nginx.html)
del Remy van Elst.

Com a eina de validació de TLS en servidors públics és molt útil l'[SSL Test](https://www.ssllabs.com/ssltest/) de Qualys SSL LABS; per a servidors TLS en LANs privades es pot fer servir per exemple el [CipherScan](https://github.com/jvehent/cipherscan) del Julien Vehent. N'he preparat una image Docker que podeu descarregar (`jordi/cipherscan`).

Passem al material de la pràctica.

Les imatges que farem servir són:
 
```
$ docker pull jordi/openssl-ca
$ docker pull jordi/nginx
$ docker pull jordi/openssl-broswser
```

Si hi ha temps farem servir un contenidor creat amb [`cipherscan`](https://github.com/jvehent/cipherscan):

```
$ docker pull jordi/cipherscan
```

Per accedir a cadascuna de les imatges cal fer `docker run` com s'ha explicat anteriorment.
Però en el cas de `jordi/nginx` cal obrir un port (Docker crea una LAN virtual que cal accedir via NAT; 
a més a més tenim el servidor Docker dins una màquina virtual que habitualment està a l'adreça 
IP `192.168.99.100`). Per a poder accedir-hi hem d'engegar el contenidor així:

```
$ docker run -p 443:443 -ti jordi/nginx bash
root@3f9f56657414:/# nginx -g "daemon off;"
...
```

Això engegarà l'`nginx` i deixarà accedir al port `443` (que estarà redirigit internament al port 
`443` del contenidor. El port `443` és el port `https` per defecte).

Per a accedir al contenidor amb un navegador podem fer servir el Safari o el Chrome 
(i probablement d'altres) accedint a la URL: `https://192.168.99.100`

# Solució de la pràctica

A [github.com/jig/docker-openssl/.../Dockerfile](https://github.com/jig/docker-openssl/blob/master/Dockerfile) podeu seguir la pràctica sencera
(està en notació `Dockerfile` però és fàcil de seguir). L'execució amb totes les claus i certificats generats (el resultat de la pràctica) el podeu trobar a:

```
$ docker run -ti jordi/openssl-pki-sample bash
```

Alerta! no facis servir les claus generades en aquest contenidor ja que són públiques (...)

Però pots regenerar-ho tot localment baixant-te el `Dockerfile` i regenerant el contenidor localment. Només cal que facis:

```
$ git clone https://github.com/jig/docker-openssl.git
$ cd docker-openssl
$ docker build -t openssl-pki-sample .
$ docker run --name TOT -p 443:443 -ti openssl-pki-sample bash
...
root@3f9f56657414:/# nginx -g "daemon off;"
```
