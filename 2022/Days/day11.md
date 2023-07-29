---
title: '#90DaysOfDevOps - Variables & Constants in Go - Day 11'
published: false
description: 90DaysOfDevOps - Variables & Constants in Go
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048862
italian_version: maxiviani
vesrsion_date: 2023-07-29
---

Prima di iniziare con gli argomenti di oggi voglio fare un grande elogio a Techworld with Nana (https://www.youtube.com/watch?v=yyUHQIec83I) e a questo fantastico viaggio conciso attraverso i fondamenti di Go.

Il Giorno 8 abbiamo configurato il nostro ambiente, il Giorno 9 abbiamo esaminato il codice Hello #90DaysOfDevOps e il Giorno 10 abbiamo esaminato il nostro spazio di lavoro Go e siamo andati un po' più in profondità sulla compilazione e l'esecuzione del codice.

Oggi daremo uno sguardo alle Variabili, Costanti e Tipi di Dati mentre scriviamo un nuovo programma.

Variabili & Costanti in Go

Iniziamo pianificando la nostra applicazione. Penso che sarebbe una buona idea lavorare su un programma che ci dica quanti giorni ci sono rimasti nella nostra sfida #90DaysOfDevOps.

La prima cosa da considerare è che, mentre costruiamo la nostra app e diamo il benvenuto ai partecipanti e forniamo loro un feedback sul numero di giorni che hanno completato, potremmo utilizzare il termine #90DaysOfDevOps molte volte all'interno del programma. Questo è un ottimo caso d'uso per rendere #90DaysOfDevOps una variabile all'interno del nostro programma.

- Le variabili vengono utilizzate per memorizzare valori.
- Sono come piccole scatole con le nostre informazioni o valori salvati.
- Possiamo poi utilizzare questa variabile in tutto il programma, il che ci consente anche di cambiarne il valore in un unico punto se questa sfida o variabile cambia. Ciò significa che potremmo tradurre questa variabile in altre sfide che abbiamo nella community semplicemente cambiando quel valore in un unico punto.

Per dichiarare questo nella nostra programma Go definiamo un valore utilizzando una keyword per le variabili. Questo sarà inserito all'interno del blocco di codice func main, che vedrai più avanti. Puoi trovare ulteriori informazioni sulle Keywords qui.

Ricordati di utilizzare nomi di variabili descrittivi. Se dichiari una variabile, devi usarla, altrimenti otterrai un errore per evitare possibili codici morti, ovvero codice che non viene mai utilizzato. Questo vale anche per i pacchetti non utilizzati.

var sfida = "#90DaysOfDevOps"

Con il codice sopra definito e utilizzato come vedremo nel prossimo esempio, puoi vedere dall'output qui sotto che abbiamo utilizzato una variabile.

package main

import "fmt"

func main() {
    var sfida = "#90DaysOfDevOps"
    fmt.Println("Benvenuto in", sfida, "")
}

Puoi trovare il codice sopra nell'esempio day11_example1.go

Vedrai quindi dal di sotto che abbiamo compilato il nostro codice con l'esempio sopra e abbiamo ottenuto l'output mostrato di seguito.

![](Images/Day11_Go1.png)

Sappiamo anche che la nostra sfida dura 90 giorni, almeno per questa sfida, ma il prossimo passo potrebbe essere 100, quindi vogliamo definire una variabile che ci aiuti in questo senso. Tuttavia, per il nostro programma, vogliamo definire questo come una costante. Le costanti sono come le variabili, tranne che il loro valore non può essere modificato nel codice (possiamo comunque creare un'applicazione in seguito con questo codice e cambiare questa costante, ma questo 90 non cambierà mentre eseguiamo la nostra applicazione)

Aggiungiamo il const al nostro codice e aggiungiamo un'altra riga di codice per stampare questo.

package main

import "fmt"

func main() {
    var sfida = "#90DaysOfDevOps"
    const giornitotali = 90

    fmt.Println("Benvenuto in", sfida, "")
    fmt.Println("Questa è una sfida di", giornitotali, "giorni")
}

Puoi trovare il codice sopra nell'esempio day11_example2.go

Se eseguiamo nuovamente il processo go build e lo eseguiamo vedrai di seguito il risultato.

![](Images/Day11_Go2.png)

Infine, e questo non sarà la fine del nostro programma, ci torneremo al Giorno 12 per aggiungere ulteriori funzionalità. Ora vogliamo aggiungere un'altra variabile per il numero di giorni che abbiamo completato la sfida.

Di seguito ho aggiunto la variabile giornicompletati con il numero di giorni completati.

package main

import "fmt"

func main() {
    var sfida = "#90DaysOfDevOps"
    const giornitotali = 90
    var giornicompletati = 11

    fmt.Println("Benvenuto in", sfida, "")
    fmt.Println("Questa è una sfida di", giornitotali, "giorni e hai completato", giornicompletati, "giorni")
    fmt.Println("Gran lavoro")
}

Puoi trovare il codice sopra nell'esempio day11_example3.go

Eseguiamo nuovamente il processo go build o puoi semplicemente usare go run

![](Images/Day11_Go3.png)

Di seguito ci sono alcuni altri esempi che ho usato per rendere il codice più facile da leggere e modificare. Fino ad ora abbiamo utilizzato Println, ma possiamo semplificarlo utilizzando Printf usando %v, che ci permette di definire le nostre variabili in ordine alla fine della riga di codice. Utilizziamo anche \n per andare a capo.

Uso %v perché utilizza un valore predefinito, ma ci sono altre opzioni che puoi trovare nella documentazione del pacchetto fmt, puoi trovare il codice esempio day11_example4.go

Le variabili possono anche essere definite in un formato più semplice nel tuo codice. Invece di definire che è una var e il tipo, puoi scrivere come segue per ottenere la stessa funzionalità, ma un aspetto più pulito e semplice per il tuo codice. Questo funzionerà solo per le variabili e non per le costanti.

func main() {
    sfida := "#90DaysOfDevOps"
    const giornitotali = 90

Tipi di Dati

Negli esempi sopra, non abbiamo definito il tipo di variabili, perché possiamo assegnare un valore qui e Go è abbastanza intelligente da sapere di che tipo si tratta o almeno può dedurlo in base al valore che hai memorizzato. Tuttavia, se vogliamo che l'utente inserisca un valore, sarà necessario un tipo specifico.

Abbiamo utilizzato Stringhe e Integers nel nostro codice fino ad ora. Integers per il numero di giorni e le stringhe per il nome della sfida.

È importante notare che ogni tipo di dato può fare cose diverse e si comporta in modo diverso. Ad esempio, gli interi possono essere moltiplicati mentre le stringhe no.

Ci sono quattro categorie:

- Tipo di base: Numeri, stringhe e booleani rientrano in questa categoria.
- Tipo aggregato: Array e strutture rientrano in questa categoria.
- Tipo di riferimento: Puntatori, slice, mappe, funzioni e canali rientrano in questa categoria.
- Tipo di interfaccia

Il tipo di dati è un concetto importante nella programmazione. Il tipo di dati specifica la dimensione e il tipo di valori delle variabili.

Go è un linguaggio a tipizzazione statica, il che significa che una volta definito il tipo di variabile, può memorizzare solo dati di quel tipo.

Go ha tre tipi di dati di base:

- bool: rappresenta un valore booleano e può essere true o false
- Numeric: rappresenta tipi interi, valori in virgola mobile e tipi complessi
- string: rappresenta un valore di stringa

Ho trovato questa risorsa super dettagliata sui tipi di dati Golang by example (https://golangbyexample.com/all-data-types-in-golang-with-examples/)

Ti suggerisco anche di guardare Techworld with Nana (https://www.youtube.com/watch?v=yyUHQIec83I&t=2023s) in questo punto, in cui vengono coperti in dettaglio molti aspetti dei tipi di dati in Go.

Se abbiamo bisogno di definire un tipo nella nostra variabile, possiamo farlo in questo modo:

var TwitterHandle string
var GiorniCompletati uint

Poiché Go implica le variabili quando viene dato un valore, possiamo stampare quei valori con il seguente codice:

fmt.Printf("La sfida è di tipo %T, il totale dei giorni è di tipo %T, i giorni completati sono di tipo %T\n", sfida, giornitotali, giornicompletati)

Ci sono molti tipi diversi di tipi di interi e di numeri floating point, i link sopra li copriranno in dettaglio.

- int = numeri interi
- unint = numeri interi positivi
- floating point types = numeri che contengono una componente decimale

Risorse

- StackOverflow 2021 Developer Survey (https://insights.stackoverflow.com/survey/2021)
- Perché abbiamo scelto Go da imparare (https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- Jake Wright - Impara Go in 12 minuti (https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- Techworld with Nana - Corso completo su Go - 3 ore e 24 minuti (https://www.youtube.com/watch?v=yyUHQIec83I)
- A PAGAMENTO Nigel Poulton Pluralsight - Go Fundamentals - 3 ore e 26 minuti (https://www.pluralsight.com/courses/go-fundamentals)
- FreeCodeCamp - Impara la programmazione Go - Tutorial Go per principianti (https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- Hitesh Choudhary - Playlist completa (https://www.youtube.com/playlist?list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N)

Il prossimo passo sarà aggiungere alcune funzionalità di input utente al nostro programma in modo da poter chiedere quanti giorni sono stati completati.

Ci vediamo al Giorno 12.
