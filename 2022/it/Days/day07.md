---
title: '#90DaysOfDevOps - The Big Picture: Learning a Programming Language - Day 7'
published: false
description: 90DaysOfDevOps - The Big Picture DevOps & Learning a Programming Language
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048856
italian_version: maxiviani
versin_date: 2023-07-28
---

## Il quadro generale: DevOps e imparare un linguaggio di programmazione

Credo sia giusto dire che, per avere successo a lungo termine come ingegnere DevOps, è necessario conoscere almeno un linguaggio di programmazione a livello di base. Voglio dedicare questa prima sessione di questa sezione per esplorare perché questa è una competenza così fondamentale e spero che alla fine di questa settimana o di questa sezione, avrai una migliore comprensione del perché, del come e di cosa fare per progredire nel tuo percorso di apprendimento.

Se chiedessi sui social media se è necessario avere competenze di programmazione per ruoli legati a DevOps, probabilmente la risposta sarebbe decisamente sì. Fammi sapere se pensi diversamente. Ma poi viene una domanda più ampia e qui non avrai una risposta così chiara: quale linguaggio di programmazione? La risposta più comune che ho visto qui è stata Python o, sempre più spesso, Golang o Go, come il linguaggio da imparare.

Per avere successo in DevOps, devi avere una buona conoscenza delle competenze di programmazione, è quello che ho capito almeno. Ma dobbiamo capire perché ne abbiamo bisogno per scegliere la strada giusta.

## Capire perché è necessario imparare un linguaggio di programmazione

Il motivo per cui Python e Go vengono raccomandati così spesso per gli ingegneri DevOps è che molti degli strumenti DevOps sono scritti in Python o Go, il che ha senso se stai costruendo strumenti DevOps. Questo è importante perché determinerà davvero cosa dovresti imparare e quale sarebbe probabilmente il più vantaggioso. Se prevedi di costruire strumenti DevOps o ti stai unendo a un team che lo fa, avrebbe senso imparare lo stesso linguaggio. Se prevedi di essere fortemente coinvolto in Kubernetes o nei contaners, è molto probabile che tu scelga Go come linguaggio di programmazione. Per esempio, l'azienda per cui lavoro (Kasten by Veeam) si trova nell'ecosistema Cloud-Native con focus sulla gestione dei dati per Kubernetes e tutto è scritto in Go.

Ma potresti non avere le idee così chiare per fare una scelta, potresti essere uno studente o stai cambiando carriera senza aver fatto una scelta precisa. In questa situazione, penso che tu debba scegliere quello che sembra più adatto alle applicazioni con cui desideri lavorare.

Ricorda, non sto cercando di diventare uno sviluppatore di software, voglio solo capire un po' di più sul linguaggio di programmazione in modo da poter leggere e capire cosa fanno questi strumenti e da lì potremmo vedere come possiamo contribuire al miglioramento delle cose.

È anche importante sapere come interagire con questi strumenti DevOps, che potrebbero essere Kasten K10 o potrebbe essere Terraform e HCL. Questi sono ciò che chiameremo file di configurazione e così interagisci con gli strumenti DevOps per realizzare le cose, comunemente si tratta di file YAML. (Potremmo dedicare l'ultimo giorno di questa sezione per approfondire un po' su YAML)

## Mi sono appena convinto a non imparare un linguaggio di programmazione?

Nella maggior parte dei casi, o a seconda del ruolo, aiuterai i team di ingegneria a implementare DevOps nel loro flusso di lavoro, gran parte del tempo sarà dedicata al testing dell'applicazione e all'assicurarsi che il flusso di lavoro costruito sia in linea con i principi di DevOps che abbiamo menzionato nei primi giorni. Ma nella realtà, gran parte del tempo sarà dedicata alla risoluzione di problemi legati alle prestazioni dell'applicazione o a qualcosa del genere. Questo mi riporta al mio punto originale e alla ragione per cui dobbiamo conoscere il linguaggio di programmazione: dobbiamo conoscere il linguaggio in cui è scritto il codice. Se l'applicazione è scritta in NodeJS, non sarà di grande aiuto avere una competenza in Go o Python.

## Perché Go

Perché Golang è il prossimo linguaggio di programmazione per DevOps? Go è diventato un linguaggio di programmazione molto popolare negli ultimi anni. Secondo l'indagine di StackOverflow per il 2021, Go è arrivato al quarto posto per i linguaggi di programmazione, scripting e markup più desiderati, con Python al primo posto, ma ascoltami. [Indagine sviluppatori StackOverflow 2021 - Link sui più desiderati](https://insights.stackoverflow.com/survey/2021#section-most-loved-dreaded-and-wanted-programming-scripting-and-markup-languages)

Come ho già detto, alcuni dei più noti strumenti e piattaforme DevOps sono scritti in Go, come Kubernetes, Docker, Grafana e Prometheus.

Quali sono alcune caratteristiche di Go che lo rendono ottimo per DevOps?

## Compilazione e distribuzione dei programmi Go

Un vantaggio nell'usare un linguaggio come Python, interpretato, in un ruolo DevOps è che non devi compilare un programma prima di eseguirlo. Soprattutto per compiti di automazione più piccoli, non vuoi essere rallentato da un processo che richiede una compilazione, anche se Go è un linguaggio di programmazione compilato, **Go viene compilato direttamente in codice macchina**. Go è noto anche per i tempi di compilazione veloci.

## Go vs Python per DevOps

I programmi Go sono linkati staticamente, il che significa che quando compili un programma Go, tutto è incluso in un singolo file eseguibile binario e non saranno necessarie dipendenze esterne che dovrebbero essere installate sulla macchina remota. Ciò rende il rilascio dei programmi Go semplice, a differenza dei programmi Python che utilizzano librerie esterne, dove devi assicurarti che tutte quelle librerie siano installate sulla macchina remota su cui desideri eseguire il programma.

Go è un linguaggio indipendente dalla piattaforma, il che significa che puoi produrre eseguibili binari per tutti i sistemi operativi, Linux, Windows, macOS, ecc. ed è molto facile farlo. Con Python, per determinati sistemi operativi, non è così semplice creare eseguibili binari.

Go è un linguaggio molto performante, ha tempi di compilazione veloci e un tempo di esecuzione rapido, con un utilizzo ridotto delle risorse come CPU e memoria, soprattutto rispetto a Python. Sono stati implementati numerosi miglioramenti nel linguaggio Go che lo rendono così performante. (Vedi le risorse indicate)

A differenza di Python, che spesso richiede l'uso di librerie di terze parti per implementare un determinato programma, Go include una libreria standard che offre la maggior parte delle funzionalità necessarie per DevOps direttamente integrata. Ciò include funzionalità di elaborazione dei file, servizi web HTTP, elaborazione JSON, supporto nativo per la concorrenza e il parallelismo, nonché test integrati.

Non sto assolutamente criticando Python, sto solo esponendo le mie ragioni per scegliere Go, e non sono quelle del confronto Go vs Python di cui sopra ma è, in generale, perché ha senso dato che l'azienda per cui lavoro sviluppa software in Go. Ecco perché.

Posso dire che, o almeno mi è stato detto poiché non sono moltissime le pagine in questa parte al momento, una volta imparato il tuo primo linguaggio di programmazione sarà più facile affrontare altri linguaggi. Probabilmente non avrai mai un lavoro in un'azienda dove non dovrai occuparti di gestire, progettare, orchestrare e risolvere problemi delle applicazioni JavaScript e Node JS.

## Risorse

- [StackOverflow 2021 Developer Survey](https://insights.stackoverflow.com/survey/2021)
- [Why we are choosing Golang to learn](https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- [Jake Wright - Learn Go in 12 minutes](https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- [Techworld with Nana - Golang full course - 3 hours 24 mins](https://www.youtube.com/watch?v=yyUHQIec83I)
- [**NOT FREE** Nigel Poulton Pluralsight - Go Fundamentals - 3 hours 26 mins](https://www.pluralsight.com/courses/go-fundamentals)
- [FreeCodeCamp - Learn Go Programming - Golang Tutorial for Beginners](https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- [Hitesh Choudhary - Complete playlist](https://www.youtube.com/playlist?list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N)

Per i prossimi 6 giorni su questo argomento, intendo lavorare su alcune delle risorse elencate sopra e documentare le mie note per ogni giorno. Noterai che in genere durano circa 3 ore come corso completo, ho voluto condividere l'elenco completo in modo che, se hai il tempo, dovresti procedere e seguire ognuna di esse. Se il tempo lo consente, mi attengo alla mia ora di apprendimento ogni giorno.

Ci vediamo al [Giorno 8](day08.md).
