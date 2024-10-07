---
title: "Cos'è Bitcoin?"
slug : "cos-e-bitcoin"
date: 2024-10-07T00:00:00Z
draft: false
featuredImg: ""
description : "Un'introduzione per i non addetti ai lavori"
tags: 
  - Bitcoin
  - Phylosophy
author : zenone
lnAddress: bc1p4dldd4kuwkt28w8km4y344x7l80w853mpzuhshyq2x4ll5ut86zss9h24y
scrolltotop : true
toc : true
mathjax : false
---

## Che cos è Bitcoin? ##
*B*itcoin (con la B maiuscola) è un protocollo di comunicazione informatico, un software, un programma che può essere installato su di un computer.

Un protocollo rappresenta le “istruzioni di gioco”, un insieme di regole o linee guida che determinano come due o più entità devono comunicare tra loro in un determinato scenario operativo.
Può essere visto come una regola di comportamento tra sistemi o dispositivi.
Ad esempio, il protocollo [HTTP](https://en.wikipedia.org/wiki/HTTP) regola come un browser web, o client (il programma che stai usando per navigare su questa pagina) e un server (un computer remoto, da qualche parte) comunicano per trasferire informazioni (connessione al server, richiesta del contenuto di questa pagina, invio del contenuto al mio PC).

Raramente il mondo mainstream mette in luce questa differenza, ma quando parliamo della criptovaluta stiamo parlando di *b*itcoin (con la b minuscola), ovvero l’unità di misura, l’entità "di valore" che può essere
- scambiata, come quando compriamo sui crypto exchange 
- prodotta, estratta con il famoso processo di “mining”.

Lo scopo di *b*itcoin (b minuscola) è creare un incentivo al mantenimento “volontario” del protocollo *B*itcoin (B maiuscola).

## La rete Bitcoin ##
La rete Bitcoin (perché di rete di computer si tratta) è composta da vari dispositivi informatici interconnessi tramite un'architettura di tipo peer to peer: a differenza dell'esempio precedente, dove molti *client* richiedono un servizio ad un solo *server*, in una rete p2p tutti i dispositivi sono contemporaneamente client e server, di fatto creando una rete di disposiivi equivalenti tra loro (*peer*).
Le informazioni contentute in ciascun *peer* sono uguali a quelle degli altri. Questo permette una immensa ridondanza dei dati e una resilienza a attacchi esterni quali censure o limitazioni di accesso a server centralizzati e di conseguenza oscuramenti di contenuti o di accessi a siti e servizi online.
Se vi chiedete perché serva un incentivo la risposta è semplice: nonostante sia affascinante l’idea di un servizio di questo genere, il servizio offerto da bitcoin richiede parecchia energia elettrica e capacità tecnica per essere mantenuto online e nessuno fa niente per niente.
Cominciamo a scendere di un gradino nella tana del bianconiglio e cambiamo domanda.

Per spiegarlo ci serve introdurre un un concetto fondamentale: la **Blockchain**.

## La blockchain ##
Un termine spesso associato a *B*itcoin è la parola Blockchain, un tipo particolare di struttura di dati. Blockchain è un tipo di “archivio” costituito da una catena (**chain**) di files o blocchi (**block**), in cui i dati vengono inseriti in ciascun file e ciascun file è dipende dal blocco precedente, e diventa un input per determinare il contenuto del file successivo.

La sequenza dei blocchi è temporale e non è possibile (è piu corretto dire che non è conveniente) eliminare, aggiungere o modificare blocchi che siano gia stati confermati come validi. L'unica modifica possibile permessa è nel prossimo blocco che verrà creato.

## Le regole della blockchain ##
La blockchain di bitcoin e in generale le blockchain utilizzate da progetti di criptovalute più noti è una blockchain “pubblica”(ne esistono di private, di federate,di ibride,...), in cui chiunque rispetti le regole può interagire con il protocollo:

1. chiunque può leggere il contenuto di tutti i file excel (blocchi): tutti i peers della rete dispongono di una copia della blockchain

2. chiunque può aggiungere dati al file excel (blocco) se sono rispettate... 

3. le regole di scrittura

Quando uno dei peer o *nodo* vuole scrivere nella blockchain, invia a tutti i nodi della rete le informazioni da modificare.
Se queste informazioni *transazione* è valida, viene accettata e tenuta in memoria da ciascun nodo, essendoci migliaia di nodi attivi che generano transazioni, nella memoria di ciascun nodo ci sono costantemente migliaia di transazioni valide.

Ma attenzione: il nodo non ha il diritto di modificare la blockchain.

## Il mining ##
Tra i nodi della rete, ci sono alcuni nodi speciali, i *miners* che possono prelevare le transazioni dalla memoria per provare a generare un blocco, ovvero un file che rispetta una caratteristica decisa all'unanimità dai nodi.
Creare un blocco consiste nel combinare il maggior numero possibile di transazioni presenti nella mempool, attraverso un algoritmo di hashing, in modo che l'output rispetti alcune caratteristiche.

Come paragone, è come se migliaia di computer cercassero di risolvere un problema complicatissimo, usando molta energia, finchè qualcuno alza la mano e dice "finito!".

Uno solo arriverà per primo, e proporrà il suo blocco alla rete. Se il blocco verrà dichiarato valido, tutti i nodi lo inscriveranno per sempre nella blockchain.

Il miner invece, sarà ripagato con dei bitcoin nuovi di zecca.
Il processo di generazione di nuovi bitcoin rappresenta un incentivo costante all’impegno energetico e computazionale che i minatori decidono di prendersi.

La probabilità di vincita di un miner è misurata in termini di hash power, ovvero quante soluzioni per secondo vengono proposte alla ricerca di quel numero difficilissimo.
Per avere stima di grandezza pensate che a luglio 2024 (picco massimo dell hash power investita per tentare di vincere la lotteria che valida un nuovo blocco e da come ricompensa una quantità di bitcoin nuovi al vincitore) era di 879 EH/s, ovvero ogni secondo venivano proposte 879 quintilioni di possibili soluzioni al secondo (879,000,000,000,000,000,000,000 tentativi al secondo).

## Bitcoin vs moneta "fiat" ##

Quando ci riferiamo a bitcoin come valuta ci riferiamo esattamente all’unità di ricompensa prevista per chi si impegna (a proprie spese e consumando energia) a mantenere operativo un registro pubblico contabile, unità di misura che finisce poi per diventare mezzo di scambio.
Va da sè che per essere conveniente per i miners, la ricompensa in Bitcoin deve avere un valore almeno uguale o superiore al costo dell'energia usata per creare un blocco.

Può sembrare inutilmente complesso ma considerate che il nostro attuale sistema di scambio di valore, il sistema monetario-bancario, ha una complessità molto più elevata e dei costi ampiamente maggiori per garantire che i saldi degli utenti non vengano hackerati, il denaro cartaceo venga stampato e trasportato, i sistemi di pagamento rimangano efficienti e non vengano create valute falsificate o frodi.

Gli attori che garantiscono l’efficacia, l'efficienza e il funzionamento del sistema monetario sono almeno:

1. Banche Centrali
2. Banche Commerciali
3. Autorità di Regolamentazione Finanziaria
4. Organizzazioni Internazionali
5. Sistemi di Pagamento e di Compensazione 6. Istituzioni Finanziarie Non Bancarie
7. Audit e Revisori dei Conti
8. Governi e Legislatori
9. Depositi e Garanzie sui Depositi

Gli attori che garantiscono il funzionamento del protocollo Bitcoin sono:
1. Miners
2. Nodi (Nodes)

ma soprattutto, sono solo macchine incorruttibili che eseguono un software, non umani corruttibili e assetati i potere.

## Ricapitolando, cos’è *b*itcoin e cos’è *B*itcoin? ##
### bitcoin è **unità di valore** ###
bitcoin è l’unità di misura usata per incentivare il mantenimento del protocollo Bitcoin, considerabile valuta nel momento in cui viene accettata e utilizzata per lo scambio di beni o servizi.

Come abbiamo visto non dipende dalle regole del sistema bancario attuale ma è un programma indipendente e a partecipazione volontaria installabile su qualunque dispositivo informatico, e che copre l’intero globo senza barriere di ingresso che non siano un dispositivo informatico e una connessione internet.

### bitcoin è **scarso** ###
È limitato a una quantità di 21 milioni, distribuito secondo le regole del protocollo, ovvero dato come ricompensa ai minatori che garantiscono il corretto funzionamento del protocollo.
Oltre che limitato ha una politica monetaria deflattiva, ovvero la sua emissione si riduce costantemente con il passare del tempo, al contrario dell’emissione di moneta tradizionale che, come abbiamo imparato bene in questi ultimi 15 anni, aumenta costantemente almeno del 2% all’anno.

### bitcoin è **trasferibile** ###
È trasferibile da A a B senza che una terza parte centrale (un autorità simile ad una banca per intenderci) possa arbitrariamente decidere di bloccare quel trasferimento.
È tecnicamente inconfiscabile da qualunque tipo di autorità in quando non fisicamente detenuto presso nessun ente che risponde a regole governative e coercizioni di alcun tipo.
È tracciato su registro distribuito, pubblico e immutabile (la blockchain), al contrario di un conto bancario che è centralizzato, oscurato a chi non ne è proprietario e modificabile arbitrariamente. È oro digitale, scarso e prezioso per le suddette proprietà “fisiche” intrinseche, classificato come commodity dalla [SEC](https://www.sec.gov/) quindi al pari di una materia prima.

### bitcoin è **programmabile** ###
È denaro programmabile: permette il settlement automatico di transazioni all’avverarsi di terminate condizioni contrattuali (concetto di “smart contract”)
Un piccolo indizio per quello di cui parleremo più avanti: bitcoin è una valuta, un applicazione sviluppata dentro il protocollo Bitcoin, così come WorldWideWeb è un'applicazione del protocollo Internet.


Il protocollo Bitcoin è molto più di una semplice valuta.
È un database pubblico e immutabile in cui è possibile registrare qualunque tipo di informazione e di dato. Se non è chiaro ancora l’importanza di questa funzionalità lo diventerà quando introdurremo il concetto di “asset digitale” e di “OP_code”, un tipo di transazione che non prevede per forza lo scambio di btc ma che può contenere al suo interno script contrattuali complessi, microsoftware che vivono in quella che può essere considerata una macchina virtuale del valore distribuita e decentralizzata.
Motivo per cui ad oggi non si parla più solo di bitcoin come criptovaluta ma come ecosistema.
