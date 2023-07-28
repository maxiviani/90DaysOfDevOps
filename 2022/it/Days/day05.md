---
title: '#90DaysOfDevOps - Plan > Code > Build > Testing > Release > Deploy > Operate > Monitor > - Day 5'
published: false
description: 90DaysOfDevOps - Plan > Code > Build > Testing > Release > Deploy > Operate > Monitor >
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048830
italian_version: maxiviani
version_date: 2023-07-28
---

## Pianificazione > Codice > Build > Testing > Release > Deploy > Operativo > Monitoraggio >

Oggi ci concentreremo sugli step individuali dall'inizio alla fine e sul ciclo continuo di un'applicazione nel mondo del DevOps.

![DevOps](Images/Day5_DevOps8.png)

### Pianificazione

Tutto ha inizio con il processo di pianificazione, dove il team di sviluppo si riunisce e stabilisce quali funzionalità e correzioni di bug implementeranno nella prossima sprint. Questa è un'opportunità per te, in qualità di Ingegnere DevOps, per essere coinvolto e capire quali compiti ti riguarderanno e anche influenzare le loro decisioni o il loro percorso e aiutarli a lavorare con l'infrastruttura che hai costruito o indirizzarli verso qualcosa che funzionerà meglio nel caso in cui non siano sulla giusta strada. Un punto chiave da sottolineare è che i membri del team di sviluppo o dell'ingegneria del software sono i tuoi clienti in quanto Ingegnere DevOps, quindi questa è la tua opportunità per collaborare con loro prima che intraprendano una cattiva strada.

### Codice

Una volta conclusa la sessione di pianificazione, inizieranno a scrivere il codice. Potresti essere coinvolto o meno in questa fase, ma uno dei luoghi in cui potresti esserlo è quando scrivono il codice. Puoi aiutarli a comprendere meglio l'infrastruttura, in modo che sappiano quali servizi sono disponibili e come interagire al meglio con tali servizi. Una volta terminato, uniranno il codice al repository.

### Build

Qui avvieremo il primo dei nostri processi di automazione, poiché prenderemo il loro codice e lo compileremo a seconda del linguaggio utilizzato. Potrebbe essere trascritto o compilato, oppure potrebbe essere creato un'immagine Docker da quel codice. In ogni caso, attraverseremo questo processo utilizzando la nostra pipeline CI/CD.

## Testing

Una volta costruito, eseguiremo alcuni test. Di solito, il team di sviluppo scrive i test, ma potresti avere qualche input su quali test vengano scritti. Dobbiamo eseguire questi test perché è un modo per cercare di ridurre al minimo l'introduzione di problemi in produzione. Non garantisce che non ci saranno problemi, ma vogliamo avvicinarci il più possibile a una garanzia che non stiamo introducendo nuovi bug e che non stiamo rompendo ciò che funzionava in precedenza.

## Release

Una volta superati questi test, passeremo al processo di rilascio. A seconda del tipo di applicazione su cui stai lavorando, potrebbe essere una fase opzionale. Il codice potrebbe semplicemente risiedere nel repository GitHub o nel repository Git o in qualsiasi altro posto, ma potrebbe essere il processo di prendere il codice compilato o l'immagine Docker creata e inserirla in un registro o un repository accessibile dai tuoi server di produzione per il processo di distribuzione.

## Deploy

Questa è la fase successiva, poiché il deployment è come il culmine di tutto questo processo. Il deployment avviene quando mettiamo il codice in produzione e solo allora il nostro business realizza il valore di tutto il tempo, lo sforzo e il duro lavoro che tu e il team di ingegneria del software avete dedicato a questo prodotto fino a questo punto.

## Operativo

Una volta che è stato distribuito, ci occuperemo delle operazioni. Questo potrebbe includere, ad esempio, ricevere chiamate dai clienti che si lamentano perché il sito è lento o perché l'applicazione sta funzionando lentamente. Quindi, dovrai capire il motivo di ciò e, eventualmente, costruire la scalabilità automatica per gestire un aumento del numero di server disponibili durante i periodi di picco e ridurre il numero di server durante i periodi di basso carico. In ogni caso, tutto ciò riguarda le metriche operative. Un'altra cosa operativa che farai è includere un feedback loop dalla produzione al tuo team di operazioni, per segnalarti gli eventi chiave avvenuti in produzione, come ad esempio un deployment. Riguardo alla fase di deployment, potrebbe essere automatizzata o meno a seconda del tuo ambiente. L'obiettivo è automatizzarla sempre quando possibile, ma ci potrebbero essere alcuni ambienti in cui è necessario eseguire alcune fasi prima di essere pronti per farlo. Tuttavia, l'ideale è effettuare il deployment automaticamente come parte del tuo processo di automazione, ma se lo fai, potrebbe essere una buona idea includere nelle tue fasi operative qualche tipo di notifica in modo che il tuo team di operazioni sappia che un deployment è avvenuto.

## Monitoraggio

Tutti i passaggi precedenti portano al passo finale, che è il monitoraggio. Soprattutto per le problematiche operative, il monitoraggio è essenziale. La scalabilità automatica, la risoluzione dei problemi, tutto ciò non sarebbe possibile senza un sistema di monitoraggio in grado di avvisarti in caso di problemi. Quindi, alcune delle cose per cui potresti costruire il monitoraggio riguardano l'utilizzo della memoria, l'utilizzo della CPU, lo spazio su disco, il tempo di risposta dell'endpoint API, la velocità con cui l'endpoint risponde. Inoltre, una parte importante di ciò riguarda i log. I log danno agli sviluppatori la possibilità di vedere cosa sta accadendo senza dover accedere direttamente ai sistemi di produzione.

## Ripeti

Una volta che tutto è in atto, torni al punto di partenza, alla fase di pianificazione, e ripeti tutto il processo.

## Continuo

Molti strumenti ci aiutano a raggiungere il processo continuo sopra descritto, tutto questo codice e l'obiettivo finale di essere completamente automatizzati, l'infrastruttura cloud o qualsiasi altro ambiente viene spesso descritto come Continuous Integration/Continuous Delivery/Continuous Deployment o "CI/CD" in breve. Dedicheremo un'intera settimana a CI/CD più avanti nei 90 giorni, con alcuni esempi e spiegazioni per comprendere i concetti fondamentali.

### Continuous Delivery

Continuous Delivery = Pianificazione > Codice > Build > Testing

### Continuous Integration

Questa è essenzialmente l'esito delle fasi di Continuous Delivery sopra descritte, oltre all'esito della fase di Release. Questo vale sia per il fallimento che per il successo, ma ciò viene restituito alla Continuous Delivery o spostato nella Continuous Deployment.

Continuous Integration = Pianificazione > Codice > Build > Testing > Release

### Continuous Deployment

Se hai un rilascio di successo dalla tua Continuous Integration, passa alla Continuous Deployment, che comporta le seguenti fasi

CI Release ha avuto successo = Continuous Deployment = Deploy > Operativo > Monitoraggio

Puoi vedere queste tre fasi continue sopra come una semplice collezione delle fasi del ciclo di vita del DevOps.

Questo ultimo pezzo è stato un breve riassunto per me del Giorno 3, ma penso che mi abbia chiarito le idee.

### Risorse

- [DevOps per Sviluppatori – Software o Ingegnere DevOps?](https://www.youtube.com/watch?v=a0-uE3rOyeU)
- [Techworld con Nana - Mappa stradale del DevOps 2022 - Come diventare un Ingegnere DevOps? Che cos'è il DevOps?](https://www.youtube.com/watch?v=9pZ2xmsSDdo&t=125s)
- [Come diventare un Ingegnere DevOps nel 2021 - Mappa stradale del DevOps](https://www.youtube.com/watch?v=5pxbp6FyTfk)

Se sei arrivato fin qui, saprai se è quello che vuoi fare o meno.

Ci vediamo al [Giorno 6](day06.md).
