---
title: '#90DaysOfDevOps - Getting user input with Pointers and a finished program - Day 12'
published: false
description: 90DaysOfDevOps - Getting user input with Pointers and a finished program
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048864
italian_version: maxiviani
versin_date: 2023-07-28
---

## Ottenere l'input dell'utente con i puntatori e un programma completo

Ieri ([Giorno 11](day11.md)), abbiamo creato il nostro primo programma Go ma e le parti per cui desideravamo ottenere l'input dell'utente sono state create come variabili e hanno ricevuto i loro valori all'interno del nostro codice. Adesso vogliamo chiedere all'utente di fornire il proprio input per assegnare un valore alla variabile per il messaggio finale.

## Ottenere l'input dall'utente

Prima di farlo, diamo un'occhiata nuovamente alla nostra applicazione e esaminiamo le variabili che vogliamo testare prima di ottenere l'input dell'utente.

Ieri abbiamo terminato con il nostro codice che appariva così [day11_example4.go](Go/day11_example4.go). Abbiamo definito manualmente nel codice le nostre variabili e costanti `challenge, daystotal, dayscomplete`.

Aggiungiamo ora una nuova variabile chiamata `TwitterName`, puoi trovare questo nuovo codice in [day12_example1.go](Go/day12_example1.go) e se eseguiamo questo codice, ecco il nostro output.

![](Images/Day12_Go1.png)

Siamo al giorno 12 e dovremmo modificare quel valore di `dayscomplete` e compilare il nostro codice ogni giorno se fosse codificato in modo rigido, il che non sembra così fantastico.

Per input dell'utente, vogliamo ottenere il valore di un nome e del numero di giorni completati. Per fare ciò, possiamo utilizzare un'altra funzione all'interno del pacchetto `fmt`.

Riepilogo sul package `fmt`, diverse funzioni per input e output formattato (I/O):

- Messaggi di stampa
- Raccogli l'input dell'utente
- Scrivi in un file

Con questo codice, invece di assegnare il valore ad una variabile, chiediamo all'utente il proprio input.

```golang
fmt.Scan(&TwitterName)
```

Nota che utilizziamo anche `&` prima della variabile. Questo è conosciuto come puntatore, di cui parleremo nella prossima sezione.

Nel nostro codice [day12_example2.go](Go/day12_example2.go), puoi vedere che chiediamo all'utente di inserire due variabili, `TwitterName` e `DaysCompleted`

Eseguiamo ora il nostro programma e vedrai che abbiamo l'input per entrambe le variabili.

![](Images/Day12_Go2.png)

Bene, ottimo, abbiamo ottenuto un input dall'utente e abbiamo stampato un messaggio, ma come facciamo a ottenere dal nostro programma quanti giorni ci sono rimasti per terminare nostra sfida?

Per farlo, abbiamo creato una variabile chiamata `remainingDays` e l'abbiamo valorizzata nel nostro codice con `90`, quindi dobbiamo cambiare il valore di questa variabile per stampare i giorni rimanenti quando otteniamo l'input dall'utente di `DaysCompleted`. Possiamo farlo con questa semplice modifica di variabile.

```golang
remainingDays = remainingDays - DaysCompleted
```

Puoi vedere come appare il nostro programma completo qui [day12_example3.go](Go/day12_example3.go).

Se eseguiamo ora questo programma, puoi vedere che viene effettuato un semplice calcolo basato sull'input dell'utente e il valore di `remainingDays`.

![](Images/Day12_Go3.png)

## Cosa è un puntatore? (Variabili Speciali)

Un puntatore è una variabile (speciale) che punta all'indirizzo di memoria di un'altra variabile.

Una spiegazione dettagliata può essere trovata qui su [geeksforgeeks](https://www.geeksforgeeks.org/pointers-in-golang/)

Ora semplifichiamo il nostro codice e mostriamo con e senza il `&` di fronte a uno dei nostri comandi di stampa, questo ci restituisce l'indirizzo di memoria del puntatore. Ho aggiunto questo esempio di codice qui [day12_example4.go](Go/day12_example4.go)

Di seguito è riportato l'esecuzione di questo codice.

![](Images/Day12_Go4.png)

## Risorse

- [StackOverflow 2021 Developer Survey](https://insights.stackoverflow.com/survey/2021)
- [Why we are choosing Golang to learn](https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- [Jake Wright - Learn Go in 12 minutes](https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- [Techworld with Nana - Golang full course - 3 hours 24 mins](https://www.youtube.com/watch?v=yyUHQIec83I)
- [**NOT FREE** Nigel Poulton Pluralsight - Go Fundamentals - 3 hours 26 mins](https://www.pluralsight.com/courses/go-fundamentals)
- [FreeCodeCamp - Learn Go Programming - Golang Tutorial for Beginners](https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- [Hitesh Choudhary - Complete playlist](https://www.youtube.com/playlist?list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N)

Ci vediamo al [Giorno 13](day13.md).
