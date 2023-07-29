---
title: '#90DaysOfDevOps - Getting user input with Pointers and a finished program - Day 12'
published: false
description: 90DaysOfDevOps - Getting user input with Pointers and a finished program
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048864
italian_version: maxiviani
vesrsion_date: 2023-07-29
---

## Ottenere l'input dell'utente con Pointers e un programma completato

Ieri ([Giorno 11](day11.md)), abbiamo creato il nostro primo programma Go che era autocontenuto e le parti per le quali volevamo ottenere l'input dell'utente sono state create come variabili all'interno del nostro codice e gli sono stati assegnati dei valori, adesso vogliamo chiedere all'utente il suo input per assegnare il valore alla variabile per il messaggio finale.

## Ottenere l'input dell'utente

Prima di farlo, diamo un'occhiata di nuovo alla nostra applicazione e vediamo le variabili che vogliamo come test prima di ottenere quell'input dell'utente.

Ieri abbiamo concluso con il nostro codice che appariva così [day11_example4.go](Go/day11_example4.go), abbiamo definito manualmente nel codice le nostre `challenge`, `daystotal` e `dayscomplete` come variabili e costanti.

Adesso aggiungeremo una nuova variabile chiamata `TwitterName`. Puoi trovare questo nuovo codice a [day12_example1.go](Go/day12_example1.go) e se eseguiamo questo codice, ecco il nostro output.

![](Images/Day12_Go1.png)

Siamo al giorno 12 e dovremmo cambiare il valore di `dayscomplete` ogni giorno e compilare il nostro codice ogni giorno se fosse codificato rigidamente, il che non sembra così fantastico.

Per ottenere l'input dell'utente, vogliamo ottenere il valore di un nome e il numero di giorni completati. Per fare ciò, possiamo utilizzare un'altra funzione all'interno del pacchetto `fmt`.

Recap sul pacchetto `fmt`, diverse funzioni per input e output formattati (I/O)

- Stampare messaggi
- Raccogliere l'input dell'utente
- Scrivere su un file

Questo invece di assegnare il valore di una variabile, vogliamo chiedere all'utente il suo input.

```
fmt.Scan(&TwitterName)
```

Nota che usiamo anche `&` prima della variabile. Questo è noto come puntatore, di cui parleremo nella prossima sezione.

Nel nostro codice [day12_example2.go](Go/day12_example2.go), puoi vedere che chiediamo all'utente di inserire due variabili, `TwitterName` e `DaysCompleted`.

Ora eseguiamo il nostro programma e vedrai che abbiamo l'input per entrambe le variabili sopra.

![](Images/Day12_Go2.png)

Ottimo, abbiamo ottenuto l'input dall'utente e abbiamo stampato un messaggio, ma come possiamo far sì che il nostro programma ci dica quanti giorni ci restano nella nostra sfida.

Per fare ciò, abbiamo creato una variabile chiamata `remainingDays` e l'abbiamo valorizzata nel nostro codice con `90`. Dobbiamo quindi modificare il valore di questa variabile per stampare i giorni rimanenti quando otteniamo l'input dell'utente per `DaysCompleted`. Possiamo farlo con questa semplice modifica della variabile.

```
remainingDays = remainingDays - DaysCompleted
```

Puoi vedere come appare il nostro programma finito qui [day12_example2.go](Go/day12_example3.go).

Se ora eseguiamo questo programma, puoi vedere che viene effettuato un calcolo semplice in base all'input dell'utente e al valore di `remainingDays`.

![](Images/Day12_Go3.png)

## Cosa è un puntatore? (Variabili speciali)

Un puntatore è una (speciale) variabile che punta all'indirizzo di memoria di un'altra variabile.

Una spiegazione dettagliata di questo concetto può essere trovata qui [geeksforgeeks](https://www.geeksforgeeks.org/pointers-in-golang/).

Semplifichiamo ora il nostro codice e mostriamo con e senza `&` davanti a uno dei nostri comandi di stampa, questo ci fornisce l'indirizzo di memoria del puntatore. Ho aggiunto questo esempio di codice qui [day12_example4.go](Go/day12_example4.go).

Di seguito viene eseguito questo codice.

![](Images/Day12_Go4.png)

## Risorse

- [Sondaggio StackOverflow 2021 sugli sviluppatori](https://insights.stackoverflow.com/survey/2021)
- [Perché scegliamo Go per imparare](https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- [Jake Wright - Impara Go in 12 minuti](https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- [Techworld con Nana - Corso completo di Go - 3 ore e 24 minuti](https://www.youtube.com/watch?v=yyUHQIec83I)
- [**NON GRATUITO** Nigel Poulton Pluralsight - Fondamenti di Go - 3 ore e 26 minuti](https://www.pluralsight.com/courses/go-fundamentals)
- [FreeCodeCamp - Impara la programmazione Go - Golang Tutorial per principianti](https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- [Hitesh Choudhary - Playlist completa](https://www.youtube.com/playlist?list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N)

Ci vediamo al [Giorno 13](day13.md).
