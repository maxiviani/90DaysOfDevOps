---
title: '#90DaysOfDevOps - Responsibilities of a DevOps Engineer - Day 2'
published: false
description: 90DaysOfDevOps - Responsibilities of a DevOps Engineer
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048699
date: '2022-04-17T21:15:34Z'
italian_version: maxiviani
translate_date: 2023-07-26
---

## Responsabilità di un DevOps Engineer

Spero tu stia iniziando questa sezione dopo aver esaminato le risorse e il post su [Giorno 1 di #90DaysOfDevOps](day01.md).

Nel primo post è stato accennato brevemente, ma ora dobbiamo approfondire questo concetto e capire che ci sono due parti principali nella creazione di un'applicazione. Abbiamo la parte di **Sviluppo** in cui gli sviluppatori di software programmano l'applicazione e la testano. Poi abbiamo la parte delle **Operazioni** in cui l'applicazione viene distribuita e mantenuta su un server.

## DevOps è il collegamento tra le due

Per comprendere il lavoro di DevOps o le attività che un DevOps engineer svolge, è necessario comprendere gli strumenti o i processi e avere una panoramica di come si uniscono.

Tutto inizia con l'applicazione! Vedrai molto spesso che, quando si parla di DevOps, si parla principalmente dell'applicazione.

Gli sviluppatori creeranno un'applicazione, che può essere realizzata con diverse tecnologie e lasciamo che per ora sia solo frutto della nostra immaginazione, perché affronteremo questo argomento in seguito. Questo può anche coinvolgere molteplici linguaggi di programmazione, strumenti di compilazione, repository di codice, ecc.

Come DevOps engineer, non programmerai l'applicazione, ma comprendere i concetti di come lavora uno sviluppatore, i sistemi, gli strumenti e i processi che utilizzano è fondamentale per il successo.

A un livello molto generale, dovrai sapere come l'applicazione è configurata per comunicare con tutti i suoi servizi o i servizi di dati necessari e come questi aspetti possono o dovrebbero essere testati.

L'applicazione dovrà essere distribuita in qualche luogo, rimaniamo generici e diciamo che sarà su un server, non importa dove, ma su un server. Questo server sarà quindi utilizzato dal cliente o dall'utente finale, a seconda del tipo di applicazione creata.

Questo server deve essere eseguito da qualche parte, può essere in locale, in un cloud pubblico, o anche senza server (ok, ho esagerato, non copriremo il caso senza server, ma è un'opzione e sempre più aziende si stanno dirigendo in questa direzione). Qualcuno deve creare e configurare questi server e renderli pronti per l'esecuzione dell'applicazione. Questo potrebbe essere il compito del DevOps engineer: distribuire e configurare questi server.

Questi server eseguono un sistema operativo, e in generale si tratterà di Linux, ma dedicheremo una sezione o una settimana per coprire alcune delle conoscenze di base che dovresti acquisire in questo campo.

È anche probabile che sia necessaria la comunicazione con altri servizi nella rete o nell'ambiente, quindi è necessario avere anche una conoscenza della rete e della configurazione di quest'ultima, e anche questo potrebbe in parte ricadere sotto la responsabilità del DevOps engineer. Anche qui tratteremo questi aspetti in modo dettagliato, dedicando una sezione a tutti gli argomenti riguardanti DNS, DHCP, bilanciamento del carico, ecc.

## Esperto di tutto, ma maestro di niente

A questo punto, vorrei sottolineare che non è necessario essere uno specialista di rete o di infrastruttura, ma è importante avere una conoscenza di base su come avviare e far interagire gli elementi, allo stesso modo in cui si ha una conoscenza di base di un linguaggio di programmazione ma non è necessario essere uno sviluppatore. Tuttavia, è possibile che tu entri in questo campo come specialista in un'area, e questo è un buon punto di partenza per adattarsi ad altre aree.

È probabile che tu non ti occupi giornalmente della gestione di questi server o dell'applicazione.

Abbiamo parlato di server, ma è probabile che la tua applicazione venga sviluppata per essere eseguita in containers, che comunque funzionano su un server nella maggior parte dei casi, ma avrai anche bisogno di una comprensione non solo della virtualizzazione e dell'Infrastructure as a Service (IaaS) basata su cloud, ma anche della containerizzazione. Il focus in questi 90 giorni sarà maggiormente orientato verso i containers.

## Panoramica ad alto livello

Da una parte abbiamo i nostri sviluppatori che creano nuove caratteristiche e funzionalità (oltre alle correzioni dei bug) per l'applicazione.

Dall'altra parte, abbiamo un tipo di ambiente, infrastruttura o server configurato e gestito per eseguire questa applicazione e comunicare con tutti i suoi servizi necessari.

La grande domanda è: come facciamo ad aggiungere queste nuove funzionalità e correzioni di bug ai nostri prodotti e renderli disponibili agli utenti finali?

Come rilasciamo la nuova versione dell'applicazione? Questo è uno dei compiti principali di un DevOps engineer, e l'importante qui non è solo capire come farlo una volta, ma dobbiamo farlo in modo continuo, automatico ed efficiente, e ciò deve includere anche i test!

Qui concludiamo questa giornata di apprendimento, spero che sia stato utile. Nei prossimi giorni approfondiremo alcune aree di DevOps e poi tratteremo in modo più dettagliato gli strumenti, i processi e i vantaggi di questi.

## Risorse

Sono sempre disponibile a aggiungere ulteriori risorse a questi file readme poiché è uno strumento di apprendimento.

Il mio consiglio è di guardare tutti i video elencati di seguito e spero che tu abbia colto qualcosa anche dal testo e dalle spiegazioni sopra.

- [What is DevOps? - TechWorld with Nana](https://www.youtube.com/watch?v=0yWAtQ6wYNM)
- [What is DevOps? - GitHub YouTube](https://www.youtube.com/watch?v=kBV8gPVZNEE)
- [What is DevOps? - IBM YouTube](https://www.youtube.com/watch?v=UbtB4sMaaNM)
- [What is DevOps? - AWS](https://aws.amazon.com/devops/what-is-devops/)
- [What is DevOps? - Microsoft](https://docs.microsoft.com/en-us/devops/what-is-devops)

Se sei arrivato fin qui, allora saprai se questo è ciò che vuoi o no. Ci vediamo al [Giorno 3](day03.md).
