---
title: "Configurazione full node"
slug : "bitcoin-fullnode-setup"
date: 2024-01-30T21:49:37Z
draft: true
featuredImg: ""
description : 'Configurazione di un full node Bitcoin su Raspberry Pi'
tags: 
  - Bitcoin
  - Full Node
  - Privacy
  - Sicurezza
author : smettoquandovoglio
scrolltotop : true
toc : true
mathjax : false
---

{{< admonition warning "Premessa" >}}
>Scopo di questa guida è creare un full node che abbia il minimo indispensabile per operare con Bitcoin. Per mantenere i requisiti di privacy e sicurezza tanto sbandierati dai puristi Bitcoin, è necessario scendere a compromessi.
Trovo ridicolo preoccuparsi della generazione di chiavi private [true random](https://www.2uo.de/myths-about-urandom/), usare hardware wallets o altre soluzioni "commerciali", per poi appestare il full node di applicazioni di dubbia provenienza.
{{< /admonition >}}

È vero, molto è open source, quindi testato, controllato, ecc, ecc...
Poi però nella pratica ci si fida e non si va mai a controllare ogni singolo aggiornamento.

# Scopo della guida

Configurare un full node bitcoin che abbia tutte le funzionalità di un nodo Bitcoin riducendo al minimo i vettori di attacco verso il nodo stesso

## Installazione sistema operativo

### Preparazione scheda SD
- Scaricare e installare l'imager per Raspberry Pi sul proprio PC [Imager](https://www.raspberrypi/com/software/)
- Scaricare e installare l'immagine del sisteam operativo [Raspberry Os Lite](https://www.raspberrypi.com/software/operating-systems/)

{{< admonition danger "Don't trust, Verify!" >}}
>__**Verificare**__ il checksum SHA256 del file immagine. Cosa succederebbe se invece dell'immagine originale, installassimo un sistema operativo che ha incluso un keylogger, per esempio?
{{< /admonition >}}

```javascript
sha256sum imagefile.img
```
Il comando mostrato è valido su OSX. Con un po' di ricerche puoi trovare l'equivalente Windows, non è difficle.
Questo comando non fa altro che eseguire l'hash SHA256 del file immagine.

In sostanza, un algoritmo di hashing prende in pasto una sequenza di bit di lunghezza arbitraria (un file è di fatto una sequenza di bit), la macina in qualche modo, e sputa fuori una sequenza di bit più breve (il **checksum**), che può essere usata per verificare la validita del file stesso.
Nella pagina di download infatti viene fornito l'hash del file che abbiamo scaricato. Qualcosa del tipo:

9ce5e2c8c6c7637cd2227fdaaf0e34633e6ebedf05f1c88e00f833cbb644db4b

Quindi se l'output del nostro comando è identico alla stringa fornita nella pagina web, siamo sicuri che il file è identico.
Certo, potremmo essere su un sito fasullo, che propone un file fasullo ma un checksum corretto. Per questo hanno inventato i certificati HTTPS , ma [questa è un'altra storia](https://medium.com/@prashantramnyc/what-is-https-and-how-does-https-work-183c8b57c6).

### Avvio

### Installazione Rsyslog

```bash
sudo apt-get install rsyslog
```

A questo punto, possiamo rimuovere la scheda MicroSD dal PC e inserirla nello slot SD card del nostro Raspi.

### Installazione Bitcoin Core

 - Eseguiamo il seguente comando per installare le librerie necessarie alla compilazione del codice sorgente di Bitcoin

```bash
sudo apt install git build-essential libtool autotools-dev automake pkg-config libssl-dev libevent-dev bsdmainutils libboost-system-dev libboost-filesystem-dev libboost-chrono-dev libboost-program-options-dev libboost-test-dev libboost-thread-dev libminiupnpc-dev libzmq3-dev libsqlite3-dev
```

 - Eseguiamo il seguente comando per scaricare il codice sorgente direttamente dalla repository.
Sostituire il numero di versione con l'ultima versione stabile, visibile qui [Bitcoin Repository]https://github.com/bitcoin/bitcoin

```bash
git clone -b v26.0
```

 - Eseguiamo il seguente comando per configurare la compilazione. Il comando non fa altro che verificare che le librerie necessarie siano disponibili sul sistema e che i parametri di configurazione passati siano validi.

```bash
./configure --prefix=/mnt/bitcoin/lib/ --exec-prefix=/mnt/bitcoin/bin --disable-tests --disable-gui-tests --with-sqlite=yes --with-gui=no --without-bdb
```

Se tutto è andato per il verso giusto, il comando dovrebbe terminare senza errori.

 - A questo punto possiamo compilare il nostro eseguibile con il comando:

```bash
make -j4
```

 - Una volta terminato (ci vorrà un'ora almeno se siete su Raspberry Pi) possiamo eseguire il comando per l'installazione.

```bash
make install
```