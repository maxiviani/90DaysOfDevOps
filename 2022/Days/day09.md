---
title: '#90DaysOfDevOps - Let''s explain the Hello World code - Day 9'
published: false
description: 90DaysOfDevOps - Let's explain the Hello World code
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1099682
italian_version: maxiviani
vesrsion_date: 2023-07-29
---

## Spieghiamo il codice Hello World

### Come funziona Go

Nel [Giorno 8](day08.md) abbiamo visto come installare Go sulla tua postazione di lavoro e abbiamo creato la nostra prima applicazione Go.

In questa sezione, approfondiremo il codice e capiremo meglio alcuni aspetti del linguaggio Go.

### Cos'è la compilazione?

Prima di analizzare le [6 righe del codice Hello World](Go/hello.go) dobbiamo capire cosa sia la compilazione.

Programming languages that we commonly use such as Python, Java, Go and C++ are high-level languages. Meaning they are human-readable but when a machine is trying to execute a program it needs to be in a form that a machine can understand. We have to translate our human-readable code to machine code which is called compiling.

![Immagine](Images/Day9_Go1.png)

Dall'immagine sopra puoi vedere ciò che abbiamo fatto nel [Giorno 8](day08.md): abbiamo creato un semplice file main.go con un Hello World e abbiamo usato il comando `go build main.go` per compilare il nostro eseguibile.

### Cosa sono i pacchetti?

Un pacchetto è una collezione di file sorgente nella stessa directory che vengono compilati insieme. Possiamo semplificarlo ulteriormente: un pacchetto è un insieme di file .go nella stessa directory. Ricordi la nostra cartella Hello dal Giorno 8? Quando e se ti imbatterai in programmi Go più complessi, potresti trovare cartelle folder1 folder2 e folder3 che contengono diversi file .go che compongono il tuo programma con pacchetti multipli.

Usiamo i pacchetti per riutilizzare il codice di altre persone, così da non dover scrivere tutto da zero. Se desideriamo ad esempio una calcolatrice come parte del nostro programma, potremmo trovare un pacchetto Go esistente che contiene le funzioni matematiche che possiamo importare nel nostro codice, risparmiandoci molto tempo e sforzi a lungo andare.

Go ci incoraggia ad organizzare il nostro codice in pacchetti in modo che sia facile riutilizzarlo e mantenere il codice sorgente.

### Hello #90DaysOfDevOps Riga per Riga

Adesso diamo uno sguardo al nostro file main.go per Hello #90DaysOfDevOps e analizziamolo riga per riga.

![Immagine](Images/Day9_Go2.png)

Nella prima riga, abbiamo `package main`, che significa che questo file appartiene a un pacchetto chiamato main. Tutti i file .go devono appartenere a un pacchetto, e dovrebbero anche avere `package qualcosa` nella riga di apertura.

Un pacchetto può avere qualsiasi nome tu desideri. Dobbiamo chiamarlo `main` perché è il punto di partenza del programma che sarà in questo pacchetto, questa è una regola. (Devo capire di più su questa regola?)

![Immagine](Images/Day9_Go3.png)

Ogni volta che vogliamo compilare ed eseguire il nostro codice, dobbiamo dire alla macchina dove deve iniziare l'esecuzione. Lo facciamo scrivendo una funzione chiamata `main`. La macchina cercherà una funzione chiamata `main` per trovare il punto di ingresso del programma.

Una funzione è un blocco di codice che può eseguire un compito specifico ed essere utilizzato in tutto il programma.

È possibile dichiarare una funzione con qualsiasi nome utilizzando `func`, ma in questo caso, dobbiamo chiamarla `main` perché qui inizia il codice.

![Immagine](Images/Day9_Go4.png)

Successivamente, vediamo la riga 3 del nostro codice, l'importazione. Questo significa che vogliamo includere un altro pacchetto nel nostro programma principale. `fmt` è un pacchetto standard utilizzato qui e fornito da Go, che contiene la funzione `Println()`, e poiché l'abbiamo importato, possiamo usarla nella riga 6. Ci sono diversi pacchetti standard che puoi includere nel tuo programma e utilizzare o riutilizzare nel tuo codice, risparmiandoti il fastidio di dover scrivere tutto da zero. [Libreria standard di Go](https://pkg.go.dev/std)

![Immagine](Images/Day9_Go5.png)

Il `Println()` che abbiamo qui è un modo per scrivere l'output standard sul terminale, ovunque l'eseguibile venga eseguito correttamente. Sentiti libero di cambiare il messaggio tra le parentesi ().

![Immagine](Images/Day9_Go6.png)

### TL;DR (In breve)

- **Riga 1** = Questo file farà parte del pacchetto chiamato `main`, e deve essere chiamato `main` poiché contiene il punto di ingresso del programma.
- **Riga 3** = Per utilizzare `Println()`, dobbiamo importare il pacchetto `fmt` per usarlo nella riga 6.
- **Riga 5** = Punto di inizio effettivo, la funzione `main`.
- **Riga 6** = Ciò ci permetterà di stampare "Hello #90DaysOfDevOps" sul nostro sistema.

## Risorse

- [Indagine sui sviluppatori di StackOverflow 2021](https://insights.stackoverflow.com/survey/2021)
- [Perché scegliamo Golang per imparare](https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- [Jake Wright - Impara Go in 12 minuti](https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- [Techworld with Nana - Corso completo su Golang - 3 ore e 24 minuti](https://www.youtube.com/watch?v=yyUHQIec83I)
- [**NON GRATIS** Nigel Poulton Pluralsight - Go Fundamentals - 3 ore e 26 minuti](https://www.pluralsight.com/courses/go-fundamentals)
- [FreeCodeCamp - Impara la programmazione Go - Tutorial per principianti](https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- [Hitesh Choudhary - Playlist completa](https://www.youtube.com/playlist?list=PLRA
