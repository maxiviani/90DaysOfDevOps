---
title: '#90DaysOfDevOps - Application Focused - Day 3'
published: false
description: 90DaysOfDevOps - Application Focused
tags: 'devops, 90daysofdevops, learning'
cover_image: null
canonical_url: null
id: 1048825
italian_version: maxiviani
translate_date: 2023-07-27
---

## Ciclo di Vita DevOps - Focalizzato sull'Applicazione

Mentre procediamo nelle prossime settimane, incontreremo spesso questi titoli (Continuous Development, Testing, Deployment, Monitor) ancora e ancora, Se stai puntando al ruolo di DevOps Engineer, dovrai abituarti alla ripetitività, ma migliorare costantemente ad ogni iterazione è ciò che rende le cose interessanti.

In quest'ora, daremo uno sguardo ad alto livello all'applicazione dall'inizio alla fine e poi di nuovo, come un ciclo costante.

### Sviluppo (Development)

Prendiamo come esempio una nuova Applicazione, all'inizio non abbiamo nulla già realizzato, potresti dover discutere con il cliente o l'utente finale per stabilire i requisiti e creare un piano o le specifiche per la tua Applicazione. Successivamente, dovremo creare la nostra nuova applicazione basandoci su questi requisiti.

Per quanto riguarda gli strumenti in questa fase, non ci sono requisiti specifici, tranne la scelta dell'IDE (Ambiente di Sviluppo Integrato) e del linguaggio di programmazione da utilizzare per scrivere la tua applicazione.

Come DevOps engineer, ricorda che probabilmente non sarai tu a creare il piano o a scrivere l'applicazione per l'utente finale, poiché sarà compito di uno sviluppatore esperto.

Tuttavia, non farebbe male se tu fossi in grado di leggere parte del codice in modo da poter prendere decisioni migliori riguardo all'infrastruttura dell'applicazione in futuro.

Abbiamo già menzionato che questa applicazione può essere scritta in qualsiasi linguaggio. È importante mantenere il codice utilizzando un sistema di controllo versione, di cui parleremo in dettaglio più avanti e in particolare, ci immergeremo in **Git**.

È probabile che non sarà un solo sviluppatore a lavorare su questo progetto, quindi sarebbe utile avere un repository in cui archiviare il codice e collaborare con gli altri sviluppatori del team. Questo repository potrebbe essere privato o pubblico e potrebbe essere ospitato o distribuito in modo privato, solitamente si sente parlare di **GitHub o GitLab** come repository di codice. Ne parleremo più approfonditamente nella nostra sezione su **Git** più avanti.

### Testing

A questo punto, abbiamo i requisiti e stiamo sviluppando l'applicazione. Ma dobbiamo assicurarci di testare il codice in tutti i diversi ambienti a nostra disposizione o specificatamente nel linguaggio di programmazione scelto.

Questa fase consente al team controllo qualità (QA) di testare eventuali bug, e sempre più spesso vediamo l'uso di containers per simulare l'ambiente di test, il che può far risparmiare sui costi rispetto all'utilizzo di infrastrutture fisiche o cloud.

Questa fase probabilmente sarà automatizzata come parte dell'area successiva, ovvero Continuous Integration.

L'automazione del testing al posto di avere decine, centinaia o anche migliaia di collaudatori (QA) che lo fanno manualmente parla da sé. Questi ingegneri possono concentrarsi su altre attività per garantire uno sviluppo più rapido e una maggiore funzionalità rispetto al testing di bug e software, che tende ad essere un ostacolo nei rilasci tradizionali che seguono la metodologia a cascata.

### Integrazione (Integration)

L'integrazione è una fase molto importante nel ciclo di vita DevOps. Si tratta della parte in cui gli sviluppatori effettuano commit delle modifiche al codice sorgente in modo più frequente, giornalmente o settimanalmente.

Per ogni commit, la tua applicazione può attraversare le fasi di testing automatizzato, permettendo una rapida identificazione di problemi o bug prima della fase successiva.

Potresti dire a questo punto "ma noi non creiamo applicazioni, le acquistiamo da fornitori di software". Non preoccuparti, molte aziende fanno così e continueranno a farlo, e sarà il fornitore di software a concentrarsi sulle prime 3 fasi. Ma potresti voler adottare comunque l'ultima fase poiché ti permetterà di effettuare rilasci più rapidi ed efficienti delle tue applicazioni preconfezionate.

Ti suggerirei anche di considerare che queste conoscenze sono molto importanti poiché potresti acquistare software preconfezionato oggi, ma cosa accadrà domani o in futuro... il prossimo lavoro magari?

### Distribuzione (Deployment)

Bene, abbiamo costruito e testato la nostra applicazione in base ai requisiti dell'utente finale e ora dobbiamo procedere con il *deployment into prodiction* (ndt: distribuzione dell'applicazione in produzione) per gli utilizzatori.

Questa è la fase in cui il codice viene distribuito ai server di produzione, ed è qui che le cose diventano estremamente interessanti. Nel corso dei prossimi 86 giorni, ci immergeremo in queste aree in modo più approfondito. Diverse applicazioni richiedono hardware o configurazioni diverse. In questa fase potrebbe essere fondamentale l'**Application Configuration Management** e l'**Infrastructure as Code** nel ciclo di vita DevOps. Potrebbe darsi che la tua applicazione sia **containerizzata** ma disponibile anche per essere eseguita su una macchina virtuale. Questo ci porterà a parlare di piattaforme come **Kubernetes**, che orchestrerà questi contenitori e garantirà che il tuo sistema sia disponibile secondo lo stato desiderato per gli utenti finali.

Approfondiremo questi temi nei prossimi giorni per ottenere una migliore conoscenza di base su cosa siano e quando utilizzarli.

### Monitoraggio

Le cose si muovono velocemente qui: abbiamo la nostra Applicazione, che stiamo continuamente aggiornando con nuove funzionalità e miglioramenti, e abbiamo il nostro testing che si assicura di non andare incontro a problemi. La nostra applicazione è in esecuzione nell'ambiente di produzione e possiamo continuamente mantenere la configurazione e le prestazioni necessarie.

Ma ora dobbiamo essere certi che gli utenti finali ricevano l'esperienza desiderata. In questa fase, è necessario monitorare continuamente le prestazioni della nostra Applicazione. Questo consentirà ai nostri sviluppatori di prendere decisioni migliori riguardo alle migliorie da apportare all'applicazione nelle future release per migliorare il servizio agli utenti finali.

In questa sezione raccoglieremo anche i feedback riguardo le funzionalità implementate e come gli utenti finali vorrebbero migliorarle.

L'affidabilità è un fattore chiave anche qui, vogliamo che la nostra Applicazione sia sempre disponibile quando necessaria. Questo ci porterà anche a trattare altre aree come **observability, security and data management** (ndt: visibilità, sicurezza e gestione dei dati), che dovrebbero essere monitorate continuamente e i feedback utilizzati per migliorare, aggiornare e rilasciare l'applicazione in modo continuo.

Inoltre, alcuni contributi della comunità, in particolare [@_ediri](https://twitter.com/_ediri), hanno menzionato che durante questo processo continuo dovrebbero essere coinvolti anche i team FinOps (ndt: Financial Operations, si occupa della gestione finanziaria e operativa delle risorse tecnologiche). Le Applicazioni e i Dati sono eseguiti e archiviati da qualche parte, e monitorare continuamente questo aspetto ti aiuterà a evitare costi eccessivi sulle tue bollette Cloud dovuti a variazioni delle risorse utilizzate.

Penso che sia anche un buon momento per parlare del "DevOps Engineer" menzionato in precedenza: anche se ci sono molti ruoli di DevOps Engineer, non è l'approccio ideale per posizionare il processo DevOps. Quello che intendo è che, secondo quanto ho sentito da altre persone della comunità, il titolo di DevOps Engineer non dovrebbe essere l'obiettivo per nessuno, perché in realtà ogni posizione dovrebbe adottare i processi DevOps e la cultura descritta qui. DevOps dovrebbe essere utilizzato in diverse posizioni come ingegnere/architetto Cloud-Native, amministratore di virtualizzazione, architetto/ingegnere Cloud e amministratore di infrastrutture, solo per citarne alcune, ma la ragione per utilizzare il termine DevOps Engineer in precedenza era per evidenziare l'ampiezza del processo utilizzato in tutte queste posizioni e altro ancora.

## Risorse

Sono sempre disponibile ad aggiungere risorse aggiuntive a questi file di lettura poiché sono utili per l'apprendimento.

Il mio consiglio è di guardare tutto ciò che è elencato di seguito e spero che tu possa aver appreso qualcosa dal testo e dalle spiegazioni precedenti.

- [Continuous Development](https://www.youtube.com/watch?v=UnjwVYAN7Ns) Aggiungo che questo è focalizzato sulla produzione, ma la Lean Culture può essere seguita da vicino anche con DevOps.
- [Continuous Testing - IBM YouTube](https://www.youtube.com/watch?v=RYQbmjLgubM)
- [Continuous Integration - IBM YouTube](https://www.youtube.com/watch?v=1er2cjUq1UI)
- [Continuous Monitoring](https://www.youtube.com/watch?v=Zu53QQuYqJ0)
- [The Remote Flow](https://www.notion.so/The-Remote-Flow-d90982e77a144f4f990c135f115f41c6)
- [FinOps Foundation - What is FinOps](https://www.finops.org/introduction/what-is-finops/)
- [**NOT FREE** The Phoenix Project: A Novel About IT, DevOps, and Helping Your Business Win](https://www.amazon.com/Phoenix-Project-DevOps-Helping-Business/dp/1942788290/)

Se sei arrivato fin qui, ora sai se questo è il percorso che vuoi seguire o no. Ci vediamo al [Giorno 4](day04.md).
