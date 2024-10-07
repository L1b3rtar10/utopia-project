---
title: "Esempio pratico"
slug : "un-esempio"
date: 2024-09-30T00:00:00Z
draft: true
featuredImg: ""
description : 'Bitcoin: what is it?'
tags: 
  - Bitcoin
  - Phylosophy
author : zenone
lnAddress: bc1p4dldd4kuwkt28w8km4y344x7l80w853mpzuhshyq2x4ll5ut86zss9h24y
scrolltotop : true
toc : false
mathjax : false
---

## Bitcoin, un esempio pratico ##
Una regola di scrittura può essere intesa come una cella contenente una formula condizionale: Bob puo scrivere in quella cella che sposta 1 btc a Alice a condizione che il saldo di Bob > 1.
(Esempio)
Scenario iniziale.
Saldi aggiornati:
Nakamoto=0
BLOCCO 0
numero di partecipanti alla rete=1 (Satoshi Nakamoto )
transazioni=0;
ricompensa=25btc
Bitcoin spendibili= ([saldi aggiornati])
Vincitore validazione del blocco 0=nakamoto
Saldi aggiornati:
Nakamoto=25
Blocco 1
numero di partecipanti alla rete=2 (Satoshi Nakamoto, Hall Finney ) transazioni=1([Nakamoto->Finney(10btc]);
ricompensa=25btc
Bitcoin spendibili= ([saldi aggiornati])
Vincitore della validazione del blocco= Satoshi Nakamoto
Saldi aggiornati:
Nakamoto=40
Finney=10
Blocco 2
numero di partecipanti alla rete=4 (Satoshi Nakamoto, Hall Finney, Bob, Alice) transazioni=2(Nakamoto invia a bob 10 btc, finney invia a alice 5 bitcoin);
ricompensa=25btc
Vincitore della validazione del blocco= Finney
Bitcoin spendibili= ([saldi aggiornati])
Vincitore Validazione del blocco 2= finney
Saldi aggiornati:
Nakamoto=30
Finney=30
bob=10
alice=5
Osserviamo cosa verifica il minatore del blocco 2 (in questo caso finney) durante la validazione e prima di collegarlo definitivamente al blocco 1, vincendo cosi i bitcoin contenuti nel blocco 2:
Satoshi spende 10 btc a favore di bob. Lo puo fare o sta spendendo soldi che non ha? Risposta: Si perche nel blocco 0 aveva guadagnato 25 btc, nel blocco 1 ne aveva guadagnati altri 25 e ne aveva inviati 10 a finney, per cui il suo totale al blocco 2 è di 40 btc. La prima transazione è valida.
La seconda transazione di cui valutare la validità è “finney invia a alice 5 btc”. Lo può fare? Risposta: si perchè nel blocco 1 finney aveva ricevuto 10 btc da satoshi, quei 10 btc erano stati generati legittimamente da satoshi al blocco 0 e quindi sono spendibili ora (blocco 2) da finney ad alice.

 Saldi aggiornati: Nakamoto=30 Finney=30 bob=10
alice=5
Ipotizziamo ora uno scenario in cui un attore malevolo vuole provare a spendere btc che non ha e vediamo come il protocollo bitcoin risolve la controversia in questo caso:
Blocco 3
numero di partecipanti alla rete=5 (Satoshi Nakamoto, Hall Finney, Bob, Alice, Dart Vader) transazioni=3([bob -> alice (1btc)], [finney->satoshi(5btc), [dart vader-> bob(2btc)]); ricompensa=25btc
Vincitore della validazione del blocco= Bob
Bitcoin spendibili= ([saldi aggiornati])
Quando Bob andrà a controllare le transazioni contenute nel blocco 3 potrà facilmente risalire al saldo attuale di chi sta cercando di fare transazioni in quel blocco. Guardando alle prime due transazioni (bob a favore di alice e finney a favore di satoshi) si puo riuscire a ricostruire la carena di saldi che confermano a bob (il validatore di questo blocco) che quei saldi sono legittimi e possono essere spostati. Quando arriverà alla transazione che Dart Vader sta cercando di inviare a bob noterà però che Dart Vader non ha nessun saldo ricevuto e (non ancora speso verso altre utenti) disponibile. La conseguenza sarà che quella transazione non potrà essere inserita in nessun blocco in quando non valida. Il tentativo di frode da parte di Dart Vader viene bloccato alla fonte, ancor prima di essere eseguito.
Essendo che il saldo detenuto da Bob è scritto in uno dei blocchi precedentemente creati e aggiunti alla catena, chiunque può fare una veloce verifica per decidere se la transazione che Bob vuole fare a Alice è legittima o meno.
esiste un periodo di “latenza” tra quando Bob richiede l’invio di 1 btc a Alice e quando questa transazione viene eseguita, e quel periodo serve proprio a far si che un numero consistente di utenti controllino che Bob può davvero inviare quei bitcoin ad Alice perché li possiede e perche il possesso è giustificato da transazioni (in entrata per bob) registrate nei blocchi precedentemente aggiunti alla catena.
Dunque un altra verifica effettuata in questo periodo di latenza è se effettivamente Bob detiene in modo legittimo quei Bitcoin che vuole spendere.
Immagina di aver viaggiato da Milano a Napoli passando per Pavia, Genova, Roma e Perugia.
Il tuo spostamento si puo schematizzare sottoforma di un “albero di decisioni” intraprese durante il viaggio e che ha la sua radice (il punto di partenza) a Milano e la sua destinazione a Napoli. Tra tutte le diramazioni stradali possibili tu scegli quelle del percorso sopra citato. Alla fine, quando giunto a Napoli ti chiedono come mai ci hai messo due ore in più del previsto, tu mostrerai come giustificativo la mappa dell Italia e il percorso da te effettuato e registrato su google maps. Quella è la prova che non stai mentendo, che il tempo impiegato è giustificato dal tragitto che hai percorso.
Allo stesso modo, ogni singolo bitcoin (ne esisteranno 21 milioni) viene tracciato dal protocollo Bitcoin. il bitcoin che bob vuole spostare ad alice “contiene” una traccia del percorso che quel bitcoin ha fatto per andare dalla radice (Milano nell esempio, il momento in cui quel bitcoin è stato creato nella pratica) a bob. Quella traccia è un piccolo schema che rappresenta il tracciato che quel bitcoin ha seguito per essere dove è ora (a Napoli nell esempio, nel Wallet di Bob nella pratica) : tutti i
 
 partecipanti al foglio excel possono verificare che quel mezzo bitcoin è partito dalla sua origine (Milano), è passato da varie “città” (da Wallet di vari utenti che se lo sono scambiato) ed è finito a Napoli (il Wallet di Bob) ed è quindi ora disponibile per arrivare a Napoli (Alice)
Questa è una blockchain pubblica spiegata nel modo più semplice e affine a noi, generazione dei fogli di calcolo e viaggiatori frenetici di città.
È una “catena“ (Chain) di blocchi (Block) dove ogni blocco è un “”file excel” pieno di richieste di trasferimento di bitcoin da un indirizzo ad un altro.
Un blocco puo contenere migliaia di richieste del tipo “bob vuole spostare 1 btc a alice”.