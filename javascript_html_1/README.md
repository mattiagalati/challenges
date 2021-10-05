# Verifica adeguatezza password

## Scenario

Il nostro cliente ci chiede di implementare sul suo portale una funzione che permetta agli utenti di modificare autonomamente la password di accesso del proprio account.

Per questioni di sicurezza è necessario che la password scelta dall'utente rispetti alcuni semplici ma **obbligatori ed imprescindibili** criteri che il cliente ci ha fornito.

Per verificare la bontà del nostro lavoro, il cliente ci ha fornito un elenco (a titolo di esempio) di circa 60 mila parole nel file **_words.js_** e vuole che il nostro algoritmo le controlli, restituendoci solo quelle che rispettano i requisiti (_lui sa già quali sono ma non ce lo dirà in modo da non influenzarci_).

---

## Requisiti tecnici dello Script

Daremo al nostro cliente almeno 4 file:

- words.js
  - questo file contiene le parole da controllare e **non va modificato**
- performance.js
  - questo file contiene alcune funzioni per tracciare la velocità dell'algoritmo e **non va modificato**
- app.js
  - questo file va modificato realizzando l'algoritmo
- index.html
  - questo file è già predisposto per avviare la procedura e mostrare il risultato, ma impaginazione e grafica **possono essere modificate** (_al nostro cliente fa piacere un pizzico di gratificazione visiva_)

e gli chiederemo di aprire il file **_index.html_** con il browser **Google Chrome**. Il cliente sarà poi invitato a cliccare sull'unico pulsante della pagina per avviarel'algoritmo e vedere il risultato delle nostre fatiche.

L'algoritmo dovrà stampare a video **solo** le parole che rispettano questi requisiti:

- la parola deve essere **lunga almeno 5 caratteri** e contenere **almeno 3 vocali**
- la parola deve essere **un palindromo** (_al nostro cliente piacciono i giochi di parole_)

Se al cliente piacerà lo script, non è escluso che ci chieda in futuro di aggiungere criteri o modificare quelli esistenti, oppure fargli macinare milioni di parole. Poter capire facilmente cosa fa lo script per migliorarne le performance sarebbe ottimo sia per il cliente che per noi (_Win/Win_).

---

## Indicazioni dell'ambiente di sviluppo

Il flusso operativo è così organizzato:

```
─┬ index.html       // <button> avvia la funzione start() al click
 └─┬ performance.js // start() cicla 400 volte la funzione process()
   └─ app.js        // deve contenere process()
```

Per portare a termine il compito è necessario perciò modificare la pagina **_app.js_** avendo però cura però di mantenere al suo interno la funzione dal nome **_process()_** affinchè sia possibile richiamarla per avviare l'algoritmo.

Abbiamo già detto che la pagina **_performance.js_** non va modificata ed il motivo è che al suo interno viene fatto un ciclo, eseguendo per 400 volte la funzione **_process()_**. Questo perchè aprendo la console di sviluppo di Chrome (tasto F12) e visualizzando la tab **_Console_** sarà possibile vedere un log di questo tipo:

```
Total: 26.880126953125 ms
performance.js:12 Avg  28.10577889243562  -  398
performance.js:9 Total: 26.787109375 ms
performance.js:12 Avg  28.102506264110556  -  399
performance.js:9 Total: 27.093994140625 ms
performance.js:12 Avg  28.09999999821186  -  400
performance.js:9 Total: 30.654052734375 ms
performance.js:12 Avg  28.106483788858924  -  401
```

Che sta ad indicare che, dopo 400 cicli, il nostro algoritmo ha di media impiegato 28 millisecondi per mostrare il risultato. Questo può dare allo sviluppatore un indicatore di quanto rapidamente il suo script sta girando e lo spinge a migliorarsi.
