---
title: '#90DaysOfDevOps - The Go Workspace - Day 10'
published: false
description: 90DaysOfDevOps - The Go Workspace
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048701
italian_version: maxiviani
versin_date: 2023-07-28
---

### Lo spazio di lavoro di Go

Nel [Giorno 8](day08.md) abbiamo brevemente esaminato lo spazio di lavoro di Go per far funzionare Go e arrivare alla demo di `Hello #90DaysOfDevOps`. Ma dovremmo spiegare un po' meglio lo spazio di lavoro di Go.

Ricordi che abbiamo scelto le impostazioni predefinite e poi abbiamo creato la nostra cartella Go nel GOPATH che era già definito, ma in realtà, questo GOPATH può essere modificato per essere ovunque tu voglia.

Se esegui il comando

```
echo $GOPATH
```

L'output dovrebbe essere simile al mio (con un nome utente diverso forse), che è:

```
/home/michael/projects/go
```

Quindi qui abbiamo creato 3 directory. **src**, **pkg** e **bin**

![](Images/Day10_Go1.png)

**src** è dove vengono memorizzati tutti i tuoi programmi e progetti Go. Questo gestisce la gestione dei nomi dei pacchetti per tutti i tuoi repository Go. Qui vedrai sulla nostra postazione di lavoro la nostra cartella Hello per il progetto Hello #90DaysOfDevOps.

![](Images/Day10_Go2.png)

**pkg** è dove vengono archiviati i file delle librerie di pacchetti che sono stati o sono stati installati nei programmi. Questo aiuta a velocizzare il processo di compilazione in base a se i pacchetti utilizzati sono stati modificati.

![](Images/Day10_Go3.png)

**bin** è dove vengono memorizzati tutti i file binari compilati.

![](Images/Day10_Go4.png)

Il nostro Hello #90DaysOfDevOps non è un programma complesso, quindi ecco un esempio di un programma Go più complesso preso da un'altra ottima risorsa degna di essere esaminata [GoChronicles](https://gochronicles.com/)

![](Images/Day10_Go5.png)

Questa pagina approfondisce anche alcuni dettagli interessanti su perché e come è strutturata in questo modo, e approfondisce anche altre cartelle che non abbiamo menzionato [GoChronicles](https://gochronicles.com/project-structure/)

### Compilazione ed esecuzione del codice

Nel [Giorno 9](day09.md) abbiamo anche coperto brevemente un'introduzione alla compilazione del codice, ma possiamo approfondire un po' di più qui.

Per eseguire il nostro codice, prima dobbiamo **compilarlo**. Ci sono tre modi per farlo in Go.

- go build
- go install
- go run

Prima di arrivare alla fase di compilazione sopra, dobbiamo dare un'occhiata a cosa otteniamo con l'installazione di Go.

Quando abbiamo installato Go il Giorno 8, abbiamo installato qualcosa chiamato strumenti Go, che consiste in diversi programmi che ci consentono di compilare e elaborare i nostri file sorgente Go. Uno degli strumenti è `Go`

È utile notare che puoi installare strumenti aggiuntivi che non sono inclusi nell'installazione standard di Go.

Se apri il prompt dei comandi e digiti `go`, dovresti vedere qualcosa simile all'immagine qui sotto e quindi vedrai "Additional Help Topics" sotto, ma per ora non ci preoccupiamo di quelli.

![](Images/Day10_Go6.png)

Potresti anche ricordare di aver già usato almeno due di questi strumenti finora il Giorno 8.

![](Images/Day10_Go7.png)

Quelli di cui vogliamo imparare di più sono build, install e run.

![](Images/Day10_Go8.png)

- `go run` - Questo comando compila ed esegue il pacchetto principale composto dai file .go specificati sulla riga di comando. Il comando viene compilato in una cartella temporanea.
- `go build` - Per compilare pacchetti e dipendenze, compila il pacchetto nella directory corrente. Se il progetto Go contiene un pacchetto `main`, creerà e posizionerà l'eseguibile nella directory corrente; se non è così, metterà l'eseguibile nella cartella `pkg`, che può essere importata e utilizzata da altri programmi Go. `go build` ti consente anche di compilare un file eseguibile per qualsiasi piattaforma OS supportata da Go.
- `go install` - Uguale a go build ma posizionerà l'eseguibile nella cartella `bin`.

Abbiamo già eseguito go build e go run, ma sentiti libero di eseguirli nuovamente qui se lo desideri, `go install` come indicato sopra mette l'eseguibile nella nostra cartella bin.

![](Images/Day10_Go9.png)

Spero che, se stai seguendo, tu stia guardando una delle playlist o dei video qui sotto. Sto prendendo spunti da tutti questi e li sto traducendo nelle mie note per poter comprendere le conoscenze fondamentali del linguaggio Golang. Le risorse qui sotto probabilmente ti daranno una comprensione molto migliore di molte delle aree di cui hai bisogno in generale, ma sto cercando di documentare i 7 giorni o le 7 ore del viaggio con cose interessanti che ho trovato.

## Risorse

- [StackOverflow 2021 Developer Survey](https://insights.stackoverflow.com/survey/2021)
- [Why we are choosing Golang to learn](https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- [Jake Wright - Learn Go in 12 minutes](https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- [Techworld with Nana - Golang full course - 3 hours 24 mins](https://www.youtube.com/watch?v=yyUHQIec83I)
- [**NOT FREE** Nigel Poulton Pluralsight - Go Fundamentals - 3 hours 26 mins](https://www.pluralsight.com/courses/go-fundamentals)
- [FreeCodeCamp - Learn Go Programming - Golang Tutorial for Beginners](https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- [Hitesh Choudhary - Complete playlist](https://www.youtube.com/playlist?list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N)

Ci vediamo al [Giorno 11](day11.md).
