---
title: '#90DaysOfDevOps - The Go Workspace - Day 10'
published: false
description: 90DaysOfDevOps - The Go Workspace
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048701
italian_version: maxiviani
vesrsion_date: 2023-07-29
---

## Il Workspace di Go

Nel **Giorno 8** abbiamo brevemente coperto il workspace di Go per far partire Go e per la demo di `Hello #90DaysOfDevOps`. Ma dovremmo spiegare un po' di più riguardo al workspace di Go.

Ricorda che abbiamo scelto le impostazioni predefinite e abbiamo quindi creato la nostra cartella Go nel GOPATH, che è già stato definito, ma in realtà questo GOPATH può essere cambiato ovunque tu voglia.

Se esegui il comando:

```bash
echo $GOPATH
```


L'output dovrebbe essere simile al mio (con un diverso nome utente potrebbe essere):

```bash
/home/michael/projects/go
```


Poi qui, abbiamo creato 3 directory: **src**, **pkg** e **bin**.

![Immagine](Images/Day10_Go1.png)

**src** è dove vengono memorizzati tutti i tuoi programmi e progetti Go. Gestisce la gestione dei nomi dei pacchetti per tutti i tuoi repository Go. È qui che vedrai nella tua postazione di lavoro la nostra cartella Hello per il progetto Hello #90DaysOfDevOps.

![Immagine](Images/Day10_Go2.png)

**pkg** è dove vengono archiviati i file dei pacchetti installati nei programmi. Questo aiuta a velocizzare il processo di compilazione in base a se i pacchetti utilizzati sono stati modificati.

![Immagine](Images/Day10_Go3.png)

**bin** è dove vengono memorizzati tutti i tuoi eseguibili compilati.

![Immagine](Images/Day10_Go4.png)

Il nostro Hello #90DaysOfDevOps non è un programma complesso, quindi ecco un esempio di un programma Go più complesso tratto da un'altra ottima risorsa da considerare [GoChronicles](https://gochronicles.com/).

![Immagine](Images/Day10_Go5.png)

Questa pagina va anche in dettaglio su perché e come sia organizzata in questo modo e approfondisce anche altre cartelle di cui non abbiamo parlato [GoChronicles](https://gochronicles.com/project-structure/).

### Compilazione ed esecuzione del codice

Nel **Giorno 9** abbiamo anche affrontato una breve introduzione alla compilazione del codice, ma possiamo approfondire un po' di più qui.

Per eseguire il nostro codice, prima dobbiamo **compilarlo**. Ci sono tre modi per farlo con Go.

- `go build`: Per compilare pacchetti e dipendenze, compila il pacchetto nella directory corrente. Se il progetto Go contiene un pacchetto `main`, creerà e posizionerà l'eseguibile nella directory corrente, altrimenti lo metterà nella cartella `pkg`, e questo può essere importato e utilizzato da altri programmi Go. `go build` ti permette anche di creare un file eseguibile per qualsiasi piattaforma OS supportata da Go.

- `go install`: Uguale a `go build`, ma posiziona l'eseguibile nella cartella `bin`.

- `go run`: Questo comando compila ed esegue il pacchetto principale composto dai file .go specificati sulla riga di comando. Il comando viene compilato in una cartella temporanea.

Spero che, se stai seguendo, stai guardando una delle playlist o video qui sotto. Sto prendendo pezzi di tutti questi e li sto traducendo nei miei appunti in modo da poter comprendere le conoscenze fondamentali del linguaggio Golang. Le risorse qui sotto ti daranno probabilmente una comprensione molto migliore di molte delle aree necessarie nel complesso, ma sto cercando di documentare il viaggio di 7 giorni o 7 ore con cose interessanti che ho trovato.

## Risorse

- [StackOverflow 2021 Developer Survey](https://insights.stackoverflow.com/survey/2021)
- [Perché stiamo scegliendo di imparare Golang](https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- [Jake Wright - Impara Go in 12 minuti](https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- [Techworld con Nana - Corso completo di Golang - 3 ore e 24 minuti](https://www.youtube.com/watch?v=yyUHQIec83I)
- [**NON GRATUITO** Nigel Poulton Pluralsight - Fondamenti di Go - 3 ore e 26 minuti](https://www.pluralsight.com/courses/go-fundamentals)
- [FreeCodeCamp - Impara la programmazione Go - Tutorial di Golang per principianti](https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- [Hitesh Choudhary - Playlist completa](https://www.youtube.com/playlist?list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N)

Ci vediamo nel **Giorno 11**.
