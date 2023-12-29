---
title: '#90DaysOfDevOps - Plan > Code > Build > Testing > Release > Deploy > Operate > Monitor > - Day 5'
published: false
description: 90DaysOfDevOps - Plan > Code > Build > Testing > Release > Deploy > Operate > Monitor >
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048830
italian_version: maxiviani
translate_date: 2023-07-28
---

## Plan > Code > Build > Testing > Release > Deploy > Operate > Monitor > (Pianificazione > Sviluppo > Build > Test > Rilascio > Distribuzione > Operatività > Monitoraggio)

Oggi ci concentreremo sugli step individuali dall'inizio alla fine e sul ciclo continuo di un'applicazione nel mondo del DevOps.

![DevOps](Images/Day5_DevOps8.png)

### Plan (Pianificazione)

Tutto ha inizio con il processo di pianificazione, dove il team di sviluppo si riunisce e stabilisce quali funzionalità e correzioni di bug implementeranno nella prossima sprint (ndt: in ambito Agile "strint" è un termine di tempo breve, da 1 a 4 settimane). Questa è un'opportunità per te, in qualità di Ingegnere DevOps, per essere coinvolto e capire quali compiti ti riguarderanno e anche influenzare le loro decisioni o il loro percorso e aiutarli a lavorare con l'infrastruttura che hai costruito o indirizzarli verso qualcosa che funzionerà meglio nel caso in cui non siano sulla giusta strada. Un punto chiave da sottolineare è che i membri del team di sviluppo sono i tuoi clienti in quanto Ingegnere DevOps, quindi questa è la tua opportunità per collaborare con loro prima che intraprendano una cattiva strada.

### Code (Sviluppo)

Una volta conclusa la sessione di pianificazione, inizieranno a scrivere il codice. Potresti essere coinvolto o meno in questa fase, ma ogni volta che scrivono il codice potresti aiutarli a comprendere meglio l'infrastruttura, in modo che sappiano quali servizi sono disponibili e come interagire al meglio con tali servizi. Una volta terminato, uniranno il codice al repository.

### Build

Qui avvieremo il primo dei nostri processi di automazione, poiché prenderemo il loro codice e lo compileremo a seconda del linguaggio utilizzato. Potrebbe essere trascritto o compilato, oppure potrebbe essere creata un'immagine Docker da quel codice. In ogni caso, attraverseremo questo processo utilizzando la nostra pipeline CI/CD (ndt: Continuous Integration/Continuous Delivery).

## Testing

Una volta che l'abbiamo costruito, eseguiremo alcuni test su di esso. Di solito, il team di sviluppo si occupa di scrivere i test, ma potresti avere un ruolo nell'indicare quali test devono essere scritti. Dopo di ciò, dobbiamo eseguire questi test: il testing è un modo per cercare di ridurre al minimo l'introduzione di problemi quando il software viene messo in produzione. Non possiamo garantire al 100% che non ci saranno bug nuovi, ma ci sforziamo di avvicinarci il più possibile a una situazione in cui non ne introduciamo di nuovi e non rompiamo ciò che funzionava in precedenza..

## Release (Rilascio)

Una volta che i test sono stati superati con successo, procederemo con il processo di rilascio. A seconda del tipo di applicazione su cui stai lavorando, questo potrebbe essere un passaggio opzionale. Il codice potrebbe semplicemente trovarsi in un repository GitHub o in un repository Git, o ovunque sia ospitato. Potrebbe essere necessario prendere il codice compilato o l'immagine Docker che hai creato e inserirlo in un registro o un repository, in modo che sia accessibile ai server di produzione per il processo di distribuzione.

## Deploy (Distribuzione)

Dopo il processo di rilascio, il passo successivo è effettuare la distribuzione. La distribuzione è come il gioco finale di tutto questo processo, perché è quando mettiamo il codice in produzione. È solo in quel momento che la nostra azienda può trarre vantaggio da tutto il tempo, lo sforzo e il duro lavoro che tu e il team di ingegneria del software avete dedicato a questo prodotto fino a questo punto. La distribuzione è il momento in cui il software diventa disponibile agli utenti finali o clienti, ed è quando possiamo vedere concretamente i benefici del nostro lavoro. È il momento in cui il prodotto entra nel suo ambiente operativo e inizia a fornire valore reale per il business.

## Operate (Operatività)

Una volta che il software è stato distribuito, entreremo nella fase operativa. Potrebbero verificarsi situazioni in cui ricevi chiamate dai clienti che si lamentano perché il sito o l'applicazione è lenta. A questo punto, dovrai capire la causa di questo problema e potresti dover implementare l'**auto-scaling**, cioè aumentare il numero di server disponibili durante i periodi di picco di utilizzo e ridurli durante i periodi di inattività. Questi sono tutti aspetti operativi del processo.

Un altro compito è creare un ciclo di feedback dal sistema in produzione al team operativo. Questo ciclo ti avvisa degli eventi chiave che si verificano in produzione, come un nuovo rilascio del software. Riguardo al rilascio, alcune fasi potrebbero essere automatizzate a seconda dell'ambiente, ma l'obiettivo è sempre automatizzare il più possibile. Potrebbero esserci alcuni ambienti in cui è necessario eseguire alcune fasi manuali prima di automatizzare completamente il processo di rilascio. Tuttavia, l'ideale è automatizzare il rilascio come parte del processo di automazione. Se hai un rilascio automatico, potrebbe essere una buona idea includere notifiche nel processo operativo per informare il team operativo che il rilascio è avvenuto.

## Monitor (Monitoraggio)

Tutti i passaggi precedenti portano all'ultimo step cruciale: la necessità di implementare il monitoraggio, soprattutto per affrontare eventuali problematiche operative, auto-scaling e risoluzione dei problemi. Senza il monitoraggio, non saremo a conoscenza dei problemi e delle anomalie che possono insorgere nel sistema. Pertanto, alcuni degli aspetti per cui dovremmo costruire il monitoraggio includono: utilizzo della memoria;utilizzo della CPU; spazio su disco; tempi di risposta degli endpoint delle API velocità di risposta di tali endpoint.

Inoltre, un aspetto fondamentale del monitoraggio è rappresentato dai logs. I logs consentono agli sviluppatori di vedere cosa sta accadendo nel sistema senza dover accedere direttamente ai sistemi di produzione. Questo è particolarmente importante perché i logs possono fornire informazioni cruciali per individuare e risolvere problemi senza dover interrompere il funzionamento dell'applicazione.

## Repete (Ripeti)

Una volta che tutto ciò è pronto, torniamo indietro alla fase iniziale di pianificazione e ripetiamo l'intero processo da capo.

## Continuous (Continuo)

Molti strumenti ci aiutano a raggiungere il processo continuo sopra descritto, con l'obiettivo finale di ottenere un'automazione completa. L'infrastruttura cloud o qualsiasi altro ambiente viene spesso descritta come Continuous Integration/Continuous Delivery/Continuous Deployment, abbreviato in "CI/CD". Dedicheremo un'intera settimana al CI/CD più avanti nei 90 giorni, con alcuni esempi e spiegazioni dettagliate per comprendere i fondamenti.

### Continuous Delivery (Distriibuzione Continua)

Continuous Delivery = Pianificazione > Codice > Build > Testing

### Continuous Integration (Integrazinoe Continua)

Questo è sostanzialmente il risultato delle fasi di Continuous Delivery descritte in precedenza, unito al risultato della fase di Rilascio. Questo vale sia per i casi di successo che per quelli di fallimento, ma questi risultati vengono reinseriti nel processo di Continuous Delivery o spostati verso Continuous Deployment.

Continuous Integration = Plan > Code > Build > Testing > Release

### Continuous Deployment (Distribuzione Continua)

Se hai un rilascio di successo dalla tua integrazione continua, allora passi al Continuous Deployment, che comprende le seguenti fasi:

Rilascio CI con successo = Continuous Deployment = Deploy > Operate > Monitor

Puoi vedere queste tre nozioni di Continuous come una semplice collezione di fasi del ciclo di vita di DevOps.

Quest'ultima parte è stata un breve riepilogo per me al Giorno 3, ma penso che mi abbia chiarito le idee.

### Risorse

- [DevOps for Developers – Software or DevOps Engineer?](https://www.youtube.com/watch?v=a0-uE3rOyeU)
- [Techworld with Nana -DevOps Roadmap 2022 - How to become a DevOps Engineer? What is DevOps?](https://www.youtube.com/watch?v=9pZ2xmsSDdo&t=125s)
- [How to become a DevOps Engineer in 2021 - DevOps Roadmap](https://www.youtube.com/watch?v=5pxbp6FyTfk)

Se sei arrivato fin qui, saprai se è quello che vuoi fare o meno.

Ci vediamo al [Giorno 6](day06.md).
