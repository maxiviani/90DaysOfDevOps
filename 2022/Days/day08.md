---
title: '#90DaysOfDevOps - Setting up your DevOps environment for Go & Hello World - Day 8'
published: false
description: 90DaysOfDevOps - Setting up your DevOps environment for Go & Hello World
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048857
italian_version: maxiviani
vesrsion_date: 2023-07-29
---

## Preparare l'ambiente DevOps per Go & Hello World

Prima di entrare nei fondamenti di Go, dovremmo installare Go sulla nostra postazione di lavoro e fare ciò che ogni "learning programming 101" module insegna, ovvero creare l'applicazione Hello World. Poiché questa guida spiegherà i passaggi per installare Go sulla tua postazione di lavoro, cercheremo di documentare il processo in immagini per facilitare il seguito.

Innanzitutto, dirigiamoci su [go.dev/dl](https://go.dev/dl/) dove troveremo alcune opzioni disponibili per il download.

![Immagine](Images/Day8_Go1.png)

Se siamo arrivati fin qui, probabilmente sappiamo quale sistema operativo è presente sulla nostra postazione di lavoro, quindi selezioniamo il download appropriato e procediamo con l'installazione. In questa guida useremo Windows, quindi possiamo lasciare tutte le impostazioni predefinite per ora. _(Nota: al momento della scrittura, questa era l'ultima versione e gli screenshot potrebbero essere obsoleti)_

![Immagine](Images/Day8_Go2.png)

Inoltre, se hai una versione più vecchia di Go installata, dovrai rimuoverla prima di procedere. Windows gestisce questo processo all'interno dell'installer, quindi la rimozione e l'installazione avverranno contemporaneamente.

Una volta completata l'installazione, apriamo un prompt dei comandi/terminale e verifichiamo se Go è stato installato correttamente digitando il comando `go version`. Se l'output non corrisponde a quello mostrato di seguito, Go non è stato installato correttamente e dovrai ripercorrere i passi.

![Immagine](Images/Day8_Go3.png)

Successivamente, verifichiamo l'ambiente per Go. È sempre una buona pratica controllare che le directory di lavoro siano configurate correttamente. Come puoi vedere nell'immagine sottostante, dovresti avere la seguente directory sul tuo sistema.

![Immagine](Images/Day8_Go4.png)

Hai controllato? Sei riuscito a seguire finora? Se provi a navigare nella directory indicata sopra, probabilmente otterrai un risultato come quello mostrato nell'immagine di seguito.

![Immagine](Images/Day8_Go5.png)

Va bene, ora creiamo quella directory. Useremo il comando `mkdir` nel nostro terminale PowerShell. Inoltre, dovremo creare altre 3 cartelle all'interno della cartella Go, come mostrato di seguito.

![Immagine](Images/Day8_Go6.png)

Ora che abbiamo installato Go e abbiamo la nostra directory di lavoro pronta per l'azione, dobbiamo ottenere un ambiente di sviluppo integrato (IDE). Ci sono molte opzioni disponibili, ma il più comune e quello che useremo è Visual Studio Code o Code. Puoi saperne di più sugli IDE [qui](https://www.youtube.com/watch?v=vUn5akOlFXQ).

Se non hai ancora scaricato e installato VSCode sulla tua postazione di lavoro, puoi farlo dirigendoti [qui](https://code.visualstudio.com/download). Come puoi vedere nell'immagine sottostante, ci sono opzioni per diversi sistemi operativi.

![Immagine](Images/Day8_Go7.png)

Come con l'installazione di Go, scarichiamo e installiamo VSCode mantenendo le impostazioni predefinite. Una volta completata l'installazione, apriamo VSCode e selezioniamo "Apri file", quindi naviga nella directory Go che abbiamo creato in precedenza.

![Immagine](Images/Day8_Go8.png)

Potresti ricevere un popup relativo alla sicurezza. Puoi leggerlo, se lo desideri, e quindi fare clic su "Sì, fidati degli autori" (ricorda che non sono responsabile se successivamente apri qualcosa in cui non ti fidi!)

Ora dovresti vedere le tre cartelle create in precedenza e ora, facendo clic destro sulla cartella "src", creiamo una nuova cartella chiamata `Hello`.

![Immagine](Images/Day8_Go9.png)

Abbiamo svolto un buon lavoro finora, non è vero? Adesso creiamo il nostro primo programma Go senza conoscere nulla dei concetti coinvolti.

Successivamente, crea un file chiamato `main.go` nella cartella `Hello`. Appena premi il tasto "Invio" dopo aver digitato "main.go", ti verrà chiesto se desideri installare l'estensione di Go e i pacchetti. Puoi anche controllare il file `pkg` vuoto creato qualche passaggio fa, e notare che dovrebbero esserci alcuni nuovi pacchetti ora.

![Immagine](Images/Day8_Go10.png)

Bene, è arrivato il momento di far partire il nostro Hello World. Copia il seguente codice nel nuovo file `main.go` e salvalo.

\```go
package main

import "fmt"

func main() {
    fmt.Println("Hello #90DaysOfDevOps")
}
\```

Ammetto che il codice sopra potrebbe non avere senso al momento, ma in futuro parleremo di funzioni, pacchetti e altro. Per ora, eseguiamo la nostra app. Torna al terminale e nella cartella `Hello`, verifica che tutto funzioni con il seguente comando:

\```bash
go run main.go
\```

![Immagine](Images/Day8_Go11.png)

Ma non finisce qui, cosa succede se vogliamo eseguire il nostro programma su altre macchine Windows? Possiamo farlo creando un eseguibile binario con il seguente comando:

\```bash
go build main.go
\```

![Immagine](Images/Day8_Go12.png)

Se eseguiamo il file risultante, otterremo lo stesso output:

\```bash
$ ./main.exe
Hello #90DaysOfDevOps
\```

## Risorse

- [Indagine sui sviluppatori di StackOverflow 2021](https://insights.stackoverflow.com/survey/2021)
- [Perché scegliamo Golang per imparare](https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- [Jake Wright - Impara Go in 12 minuti](https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- [Techworld with Nana - Corso completo su Golang - 3 ore e 24 minuti](https://www.youtube.com/watch?v=yyUHQIec83I)
- [**NON GRATIS** Nigel Poulton Pluralsight - Go Fundamentals - 3 ore e 26 minuti](https://www.pluralsight.com/courses/go-fundamentals)
- [FreeCodeCamp - Impara la programmazione Go - Tutorial per principianti](https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- [Hitesh Choudhary - Playlist completa](https://www.youtube.com/playlist?list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N)

Ci vediamo al [Giorno 9](day09.md)!

![Immagine](Images/Day8_Go13.png)
