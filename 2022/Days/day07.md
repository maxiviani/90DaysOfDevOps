---
title: '#90DaysOfDevOps - The Big Picture: Learning a Programming Language - Day 7'
published: false
description: 90DaysOfDevOps - The Big Picture DevOps & Learning a Programming Language
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048856
italian_version: maxiviani
vesrsion_date: 2023-07-29
---

## Il Quadro Generale: DevOps e l'apprendimento di un Linguaggio di Programmazione

Credo sia giusto dire che per avere successo nel lungo termine come ingegnere DevOps, devi conoscere almeno un linguaggio di programmazione a un livello fondamentale. Voglio dedicare questa prima sessione di questa sezione a esplorare perché questa abilità sia così cruciale e spero che alla fine di questa settimana o sezione avrai una migliore comprensione del perché, come e cosa fare per progredire nel tuo percorso di apprendimento.

Credo che se chiedessi in giro sui social se sia necessario avere competenze di programmazione per ruoli correlati a DevOps, la risposta sarebbe molto probabilmente un chiaro "sì". Fammi sapere se pensi diversamente. Ok, ma poi una domanda più ampia e qui non otterrai una risposta così chiara: quale linguaggio di programmazione? La risposta più comune che ho visto qui è stata Python o, sempre più spesso, Go, dovrebbe essere il linguaggio che dovresti imparare.

Per avere successo in DevOps, è necessario avere una buona conoscenza delle competenze di programmazione, almeno questo è ciò che ho capito. Ma dobbiamo capire il perché per fare la scelta giusta.

## Capire perché devi imparare un linguaggio di programmazione.

La ragione per cui Python e Go vengono raccomandati così spesso per gli ingegneri DevOps è che molte delle strumentazioni DevOps sono scritte in Python o Go, il che ha senso se stai costruendo strumenti DevOps. Ora, questo è importante perché determinerà davvero ciò che dovresti imparare e ciò sarebbe probabilmente più vantaggioso. Se stai per costruire strumenti DevOps o ti unirai a un team che lo fa, avrebbe senso imparare lo stesso linguaggio; se sarai fortemente coinvolto in Kubernetes o nei container, è probabile che tu voglia scegliere Go come linguaggio di programmazione. Per me, l'azienda per cui lavoro (Kasten by Veeam) fa parte dell'ecosistema Cloud-Native focalizzato sulla gestione dei dati per Kubernetes e tutto è scritto in Go.

Ma potresti non avere una ragione così chiara per fare una scelta; potresti essere uno studente o in fase di transizione di carriera senza una decisione definita. Penso che in questa situazione dovresti scegliere quello che sembra essere più in linea con le applicazioni con cui desideri lavorare.

Ricorda che non sto cercando di diventare uno sviluppatore di software qui, voglio solo capire un po' di più sul linguaggio di programmazione in modo da poter leggere e capire cosa fanno quegli strumenti e questo potrebbe portare a possibili miglioramenti.

È importante anche sapere come interagire con quegli strumenti DevOps, che potrebbero essere Kasten K10 o potrebbero essere Terraform e HCL. Questi sono ciò che chiameremo file di configurazione ed è così che interagisci con quegli strumenti DevOps per far accadere le cose, comunemente saranno in formato YAML. (Potremmo usare l'ultimo giorno di questa sezione per approfondire YAML)

## Mi sono appena sconsigliato di imparare un linguaggio di programmazione?

La maggior parte delle volte o a seconda del ruolo, aiuterai i team di sviluppo a implementare DevOps nel loro flusso di lavoro, molto spesso testando l'applicazione e assicurandoti che il flusso di lavoro costruito si allinei ai principi di DevOps che abbiamo menzionato nei primi giorni. Ma in realtà, gran parte del tempo sarà dedicato alla risoluzione dei problemi di prestazioni dell'applicazione o qualcosa di simile. Questo riporta al mio punto originale e alla mia motivazione: il linguaggio di programmazione che devo conoscere è quello in cui è scritto il codice? Se l'applicazione è scritta in NodeJS, non aiuterebbe molto avere una conoscenza di Go o Python.

## Perché Go

Go è diventato un linguaggio di programmazione molto popolare negli ultimi anni. Secondo l'indagine di StackOverflow per il 2021, Go è arrivato al quarto posto per i linguaggi di programmazione, scripting e markup più desiderati, con Python al primo posto, ma ascoltami. [Indagine sui sviluppatori di StackOverflow 2021 - Link più desiderati](https://insights.stackoverflow.com/survey/2021#section-most-loved-dreaded-and-wanted-programming-scripting-and-markup-languages)

Come ho anche menzionato, alcuni degli strumenti e delle piattaforme DevOps più noti sono scritti in Go, come Kubernetes, Docker, Grafana e Prometheus.

Quali sono alcune delle caratteristiche di Go che lo rendono ideale per DevOps?

## Compilazione e distribuzione di programmi Go

Un vantaggio nell'utilizzare un linguaggio come Python, interpretato in un ruolo DevOps, è che non è necessario compilare un programma Python prima di eseguirlo. Specialmente per compiti di automazione più piccoli, non vuoi essere rallentato da un processo di compilazione, anche se Go è un linguaggio di programmazione compilato, **Go viene compilato direttamente in codice macchina**. Go è noto anche per i tempi di compilazione rapidi.

## Go vs Python per DevOps

I programmi Go sono collegati staticamente, il che significa che quando compili un programma Go, tutto è incluso in un singolo eseguibile binario e non sarà necessario alcun componente esterno da installare sulla macchina remota. Questo semplifica la distribuzione dei programmi Go rispetto a un programma Python che utilizza librerie esterne, in cui è necessario assicurarsi che tutte quelle librerie siano installate sulla macchina remota su cui si desidera eseguirle.

Go è un linguaggio indipendente dalla piattaforma, il che significa che puoi produrre eseguibili binari per \* tutti i sistemi operativi, Linux, Windows, macOS, ecc., ed è molto facile farlo. Con Python, non è così semplice creare questi eseguibili binari per sistemi operativi specifici.

Go è un linguaggio molto performante, ha tempi di compilazione e di esecuzione veloci, con un utilizzo ridotto delle risorse come CPU e memoria, soprattutto rispetto a Python. Numerose ottimizzazioni sono state implementate nel linguaggio Go che lo rendono così performante. (Risorse sottostanti)

A differenza di Python, che spesso richiede l'uso di librerie di terze parti per implementare un particolare programma Python, Go include una libreria standard che contiene la maggior parte delle funzionalità di cui avresti bisogno per DevOps direttamente incorporata. Questo include funzionalità di elaborazione file, servizi web HTTP, elaborazione JSON, supporto nativo per la concorrenza e il parallelismo, nonché test integrati.

Questo non vuol dire che sto denigrando Python, sto solo dando le mie ragioni per scegliere Go, ma non riguardano Go vs Python. In generale, ha senso perché l'azienda per cui lavoro sviluppa software in Go.

Posso dire che una volta che impari il tuo primo linguaggio di programmazione, diventa più facile affrontare altri linguaggi. Probabilmente non avrai mai un lavoro in cui non dovrai gestire, progettare, orchestrare e debug applicazioni JavaScript e Node.js.

## Risorse

- [Indagine sui sviluppatori di StackOverflow 2021](https://insights.stackoverflow.com/survey/2021)
- [Perché scegliamo Golang per imparare](https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- [Jake Wright - Impara Go in 12 minuti](https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- [Techworld with Nana - Corso completo su Go - 3 ore e 24 minuti](https://www.youtube.com/watch?v=yyUHQIec83I)
- [**NON GRATUITO** Nigel Poulton Pluralsight - Fondamenti di Go - 3 ore e 26 minuti](https://www.pluralsight.com/courses/go-fundamentals)
- [FreeCodeCamp - Impara la programmazione Go - Tutorial di Golang per principianti](https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- [Hitesh Choudhary - Playlist completa](https://www.youtube.com/playlist?list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N)

Ora, per i prossimi 6 giorni di questo argomento, intendo seguire alcune delle risorse elencate sopra e documentare i miei appunti per ogni giorno. Noterai che generalmente durano circa 3 ore come un corso completo, volevo condividere l'intera lista in modo che, se hai il tempo, puoi continuare e seguirli tutti, se il tempo lo permette, io seguirò la mia ora di apprendimento ogni giorno.

Ci vediamo al [Giorno 8](day08.md).
