---
title: '#90DaysOfDevOps - Tweet your progress with our new App - Day 13'
published: false
description: 90DaysOfDevOps - Tweet your progress with our new App
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048865
italian_version: maxiviani
vesrsion_date: 2023-07-29
---

## Condividi i tuoi progressi con il nostro nuovo Applicativo

Nell'ultimo giorno in cui ci siamo dedicati a questo linguaggio di programmazione, abbiamo solo raschiato la superficie di esso, ma è proprio all'inizio che penso sia necessario interessarsi e entusiasmarsi e voler approfondire ulteriormente.

Durante gli ultimi giorni, abbiamo preso una piccola idea per un'applicazione e abbiamo aggiunto funzionalità ad essa. In questa sessione voglio sfruttare i pacchetti che abbiamo menzionato e creare la funzionalità per la nostra app, in modo che non solo ti mostri gli aggiornamenti sul tuo progresso sullo schermo, ma invii anche un tweet con i dettagli della sfida e il tuo stato.

## Aggiunta della possibilità di condividere il tuo progresso tramite tweet

La prima cosa da fare è configurare l'accesso alla tua API sviluppatore con Twitter perché tutto funzioni.

Vai alla [Twitter Developer Platform](https://developer.twitter.com) e accedi con il tuo account Twitter e i dettagli. Una volta dentro, dovresti vedere qualcosa di simile a quanto segue, senza l'app che ho già creato.

![](Images/Day13_Go1.png)

Da qui potresti anche voler richiedere un accesso elevato, potrebbe richiedere del tempo, ma per me è stato molto veloce.

Successivamente, dovremmo selezionare "Projects & Apps" e creare la nostra App. I limiti dipendono dall'accesso dell'account che hai: con "essential" puoi avere solo un'app e un progetto, con "elevated" puoi avere 3 app.

![](Images/Day13_Go2.png)

Dai un nome alla tua applicazione.

![](Images/Day13_Go3.png)

Ti saranno forniti questi token API, dovresti salvarli in un luogo sicuro. (Ho cancellato questa app successivamente) Ne avremo bisogno più avanti per la nostra App Go.

![](Images/Day13_Go4.png)

Ora che abbiamo creato la nostra app (ho dovuto cambiare il nome dell'app perché quello nello screenshot sopra era già stato preso, questi nomi devono essere unici)

![](Images/Day13_Go5.png)

Le chiavi che abbiamo raccolto prima sono conosciute come le chiavi del consumatore e avremo anche bisogno del nostro token di accesso e dei segreti. Possiamo ottenere queste informazioni utilizzando la scheda "Keys & Tokens".

![](Images/Day13_Go6.png)

Bene, per ora abbiamo finito con il portale sviluppatore di Twitter. Assicurati di tenere al sicuro le tue chiavi perché ne avremo bisogno più tardi.

## Go Twitter Bot

Ricordi il codice con cui stiamo iniziando all'interno della nostra applicazione anche [day13_example1](Go/day13_example1.go) ma prima dobbiamo controllare di avere il codice corretto per inviare un tweet.

Ora dobbiamo pensare al codice per ottenere il nostro output o messaggio su Twitter sotto forma di tweet. Utilizzeremo [go-twitter](https://github.com/dghubble/go-twitter), che è una libreria client Go per l'API di Twitter.

Per testare ciò prima di inserirlo nella nostra applicazione principale, ho creato una nuova directory nella nostra cartella `src` chiamata go-twitter-bot, ho eseguito il comando `go mod init github.com/michaelcade/go-Twitter-bot` nella cartella, che ha creato un file `go.mod`, quindi possiamo iniziare a scrivere il nostro nuovo main.go e testare il tutto.

Ora abbiamo bisogno di quei token, chiavi e segreti che abbiamo raccolto dal portale sviluppatore di Twitter. Li imposteremo nelle nostre variabili di ambiente. Questo dipenderà dal sistema operativo che stai utilizzando:

Ho ricevuto alcune domande riguardanti le variabili di ambiente, ecco un articolo che ne approfondisce i dettagli in modo che tu possa capire cosa sta accadendo: [Come impostare le variabili di ambiente](https://www.twilio.com/blog/2017/01/how-to-set-environment-variables.html)

Windows

```
set CONSUMER_KEY
set CONSUMER_SECRET
set ACCESS_TOKEN
set ACCESS_TOKEN_SECRET
```

Linux / macOS

```
export CONSUMER_KEY
export CONSUMER_SECRET
export ACCESS_TOKEN
export ACCESS_TOKEN_SECRET
```

In questa fase, puoi dare un'occhiata a [day13_example2](Go/day13_example2.go) al codice, ma noterai che stiamo usando una struttura per definire le nostre chiavi, segreti e token.

Abbiamo quindi una funzione `func` per analizzare queste credenziali e stabilire la connessione con l'API di Twitter.

Successivamente, in base al successo, invieremo un tweet.

```
package main

import (
    // altre importazioni
    "fmt"
    "log"
    "os"

    "github.com/dghubble/go-twitter/twitter"
    "github.com/dghubble

/oauth1"
)

// Credentials memorizza tutti i nostri access/consumer tokens
// e chiavi segrete necessarie per l'autenticazione con
// l'API REST di Twitter.
type Credentials struct {
    ConsumerKey       string
    ConsumerSecret    string
    AccessToken       string
    AccessTokenSecret string
}

// getClient è una funzione di supporto che restituirà un client Twitter
// che possiamo successivamente utilizzare per inviare tweet o per trasmettere nuovi tweet
// questa funzione prende un puntatore a una struttura di Credenziali che conterrà
// tutto il necessario per l'autenticazione e restituirà un puntatore a un client Twitter
// o un errore
func getClient(creds *Credentials) (*twitter.Client, error) {
    // Passa la tua consumer key (API Key) e la tua Consumer Secret (API Secret)
    config := oauth1.NewConfig(creds.ConsumerKey, creds.ConsumerSecret)
    // Passa il tuo Access Token e il tuo Access Token Secret
    token := oauth1.NewToken(creds.AccessToken, creds.AccessTokenSecret)

    httpClient := config.Client(oauth1.NoContext, token)
    client := twitter.NewClient(httpClient)

    // Verifica le credenziali
    verifyParams := &twitter.AccountVerifyParams{
        SkipStatus:   twitter.Bool(true),
        IncludeEmail: twitter.Bool(true),
    }

    // possiamo recuperare l'utente e verificare se le credenziali
    // che abbiamo utilizzato ci permettono di accedere correttamente!
    user, _, err := client.Accounts.VerifyCredentials(verifyParams)
    if err != nil {
        return nil, err
    }

    log.Printf("ACCOUNT dell'utente:\n%+v\n", user)
    return client, nil
}
func main() {
    fmt.Println("Go-Twitter Bot v0.01")
    creds := Credentials{
        AccessToken:       os.Getenv("ACCESS_TOKEN"),
        AccessTokenSecret: os.Getenv("ACCESS_TOKEN_SECRET"),
        ConsumerKey:       os.Getenv("CONSUMER_KEY"),
        ConsumerSecret:    os.Getenv("CONSUMER_SECRET"),
    }

    client, err := getClient(&creds)
    if err != nil {
        log.Println("Errore nell'ottenere il client Twitter, questo è previsto se non hai fornito i tuoi token API di Twitter")
        log.Println(err)
    }

    tweet, resp, err := client.Statuses.Update("Un tweet di prova dal futuro, testando un Programma #90DaysOfDevOps che invia un tweet, tweet tweet", nil)
    if err != nil {
        log.Println(err)
    }
    log.Printf("%+v\n", resp)
    log.Printf("%+v\n", tweet)
}

```

Quanto sopra ti restituirà un errore in base a ciò che sta accadendo oppure avrà successo e invierà un tweet con il messaggio delineato nel codice.

## Abbinare i due insieme - Go-Twitter-Bot + La nostra App

Ora dobbiamo unire questi due nel nostro `main.go`. Sono sicuro che qualcuno sta gridando che c'è un modo migliore per fare questo e per favore commenta in merito perché puoi avere più di un file `.go` in un progetto e potrebbe avere senso, ma questo funziona.

Puoi vedere il codice base unito in [day13_example3](Go/day13_example3.go) ma lo mostrerò anche qui di seguito.

```
package main

import (
    // altre importazioni
    "fmt"
    "log"
    "os"

    "github.com/dghubble/go-twitter/twitter"
    "github.com/dghubble/oauth1"
)

// Credentials memorizza tutti i nostri access/consumer tokens
// e chiavi segrete necessarie per l'autenticazione con
// l'API REST di Twitter.
type Credentials struct {
    ConsumerKey       string
    ConsumerSecret    string
    AccessToken       string
    AccessTokenSecret string
}

// getClient è una funzione di supporto che restituirà un client Twitter
// che possiamo successivamente utilizzare per inviare tweet o per trasmettere nuovi tweet
// questa funzione prende un puntatore a una struttura di Credenziali che conterrà
// tutto il necessario per l'autenticazione e restituirà un puntatore a un client Twitter
// o un errore
func getClient(creds *Credentials) (*twitter.Client, error) {
    // Passa la tua consumer key (API Key) e la tua Consumer Secret (API Secret)
    config := oauth1.NewConfig(creds.ConsumerKey, creds.ConsumerSecret)
    // Passa il tuo Access Token e il tuo Access Token Secret
    token := oauth1.NewToken(creds.AccessToken, creds.AccessTokenSecret)

    httpClient := config.Client(oauth1.NoContext, token)
    client := twitter.NewClient(httpClient)

    // Verifica le credenziali
    verifyParams := &twitter.AccountVerifyParams{
        SkipStatus:   twitter.Bool(true),
        IncludeEmail: twitter.Bool(true),
    }

    // possiamo recuperare l'utente e verificare se le credenziali
    // che abbiamo utilizzato ci permettono di accedere correttamente!
    user, _, err := client.Accounts.VerifyCredentials(verifyParams)
    if err != nil {
        return nil, err
    }

    log.Printf("ACCOUNT dell'utente:\n%+v\n", user)
    return client, nil
}
func main() {
    creds := Credentials{
        AccessToken:       os.Getenv("ACCESS_TOKEN"),
        AccessTokenSecret: os.Getenv("ACCESS_TOKEN_SECRET"),
        ConsumerKey:       os.Getenv("CONSUMER_KEY"),
        ConsumerSecret:    os.Getenv("CONSUMER_SECRET"),
    }
    {
        const DaysTotal int = 90
        var remainingDays uint = 90
        challenge := "#90DaysOfDevOps"

        fmt.Printf("Benvenuto alla sfida %v.\nQuesta sfida consiste di

 %v giorni\n", challenge, DaysTotal)

        var TwitterName string
        var DaysCompleted uint

        // richiesta di input all'utente
        fmt.Println("Inserisci il tuo nome utente Twitter: ")
        fmt.Scanln(&TwitterName)

        fmt.Println("Quanti giorni hai completato?: ")
        fmt.Scanln(&DaysCompleted)

        // calcola i giorni rimanenti
        remainingDays = remainingDays - DaysCompleted

        //fmt.Printf("Grazie %v per aver partecipato e completato %v giorni.\n", TwitterName, DaysCompleted)
        //fmt.Printf("Ti restano %v giorni per la sfida %v\n", remainingDays, challenge)
        // fmt.Println("Buona fortuna")

        client, err := getClient(&creds)
        if err != nil {
            log.Println("Errore nell'ottenere il client Twitter, questo è previsto se non hai fornito i tuoi token API di Twitter")
            log.Println(err)
        }

        message := fmt.Sprintf("Ehi, sono %v. Ho partecipato a %v per %v giorni e mi restano %v giorni", TwitterName, challenge, DaysCompleted, remainingDays)
        tweet, resp, err := client.Statuses.Update(message, nil)
        if err != nil {
            log.Println(err)
        }
        log.Printf("%+v\n", resp)
        log.Printf("%+v\n", tweet)
    }

}
```

Il risultato di questo dovrebbe essere un tweet, ma se non hai fornito le variabili di ambiente, dovresti ricevere un errore come quello mostrato di seguito.

![](Images/Day13_Go7.png)

Una volta risolto il problema o se decidi di non autenticarti con Twitter, puoi usare il codice con cui abbiamo finito ieri. L'output sul terminale in caso di successo sarà simile a questo:

![](Images/Day13_Go8.png)

Il tweet risultante dovrebbe apparire più o meno così:

![](Images/Day13_Go9.png)

## Come compilare per più sistemi operativi

Ora vorrei coprire la domanda: "Come si compila per più sistemi operativi?" La cosa fantastica di Go è che può essere facilmente compilato per molti sistemi operativi diversi. Puoi ottenere un elenco completo eseguendo il comando seguente:

```
go tool dist list
```

Fino ad ora, l'utilizzo dei nostri comandi `go build` è ottimo e utilizzerà le variabili d'ambiente `GOOS` e `GOARCH` per determinare la macchina host e per quale sistema verrà creato il build. Ma possiamo anche creare altre versioni eseguibili utilizzando il codice seguente come esempio.

```
GOARCH=amd64 GOOS=darwin go build -o ${BINARY_NAME}_0.1_darwin main.go
GOARCH=amd64 GOOS=linux go build -o ${BINARY_NAME}_0.1_linux main.go
GOARCH=amd64 GOOS=windows go build -o ${BINARY_NAME}_0.1_windows main.go
GOARCH=arm64 GOOS=linux go build -o ${BINARY_NAME}_0.1_linux_arm64 main.go
GOARCH=arm64 GOOS=darwin go build -o ${BINARY_NAME}_0.1_darwin_arm64 main.go
```

Questo ti fornirà quindi eseguibili nella tua directory per tutte le piattaforme elencate sopra. Puoi quindi prendere questo e creare un makefile per creare questi eseguibili ogni volta che aggiungi nuove funzionalità al tuo codice. Ho incluso il [makefile](Go/makefile)

Questo è quello che ho usato per creare le release che puoi vedere ora nel [repository](https://github.com/MichaelCade/90DaysOfDevOps/releases)

## Risorse

- [StackOverflow 2021 Developer Survey](https://insights.stackoverflow.com/survey/2021)
- [Perché abbiamo scelto Go come linguaggio da imparare](https://www.youtube.com/watch?v=7pLqIIAqZD4&t=9s)
- [Jake Wright - Impara Go in 12 minuti](https://www.youtube.com/watch?v=C8LgvuEBraI&t=312s)
- [Techworld with Nana - Corso completo su Go - 3 ore e 24 minuti](https://www.youtube.com/watch?v=yyUHQIec83I)
- [**A PAGAMENTO** Nigel Poulton Pluralsight - Fondamenti di Go - 3 ore e 26 minuti](https://www.pluralsight.com/courses/go-fundamentals)
- [FreeCodeCamp - Impara la programmazione Go - Tutorial di Go per principianti](https://www.youtube.com/watch?v=YS4e4q9oBaU&t=1025s)
- [Hitesh Choudhary - Playlist completa](https://www.youtube.com/playlist?list=PLRAV69dS1uWSR89FRQGZ6q9BR2b44Tr9N)
- [Un ottimo repository pieno di tutto ciò che riguarda il DevOps e gli esercizi](https://github.com/bregman-arie/devops-exercises)
- [GoByExample - Apprendimento basato su esempi](https://gobyexample.com/)
- [go.dev/tour/list](https://go.dev/tour/list)
- [go.dev/learn](https://go.dev/learn/)

Questo conclude il linguaggio di programmazione per 7 giorni! C'è ancora molto altro che potrebbe essere trattato e spero che tu sia stato in grado di continuare attraverso i contenuti sopra e di comprendere alcuni degli altri aspetti del linguaggio di programmazione Go.

Ora ci concentriamo su Linux e alcuni degli aspetti fondamentali che dovremmo tutti

 conoscere qui.

Ci vediamo a [Giorno 14](day14.md).