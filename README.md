# WikiCar Vintage - Sito Web dedicato alle Auto d'Epoca

## EXECUTIVE SUMMARY

### Tema assegnato
Sito web dedicato alle auto d'epoca.

### Obiettivo del sito
L'obiettivo del sito è quello di attrarre le persone verso il mondo delle auto d'epoca, mettendo a disposizione dell'utente diverse funzionalità con lo scopo di fornire informazioni utili agli appassionati di questo settore.

### Descrizione preliminare sintetica
Al giorno d'oggi vengono fabbricate continuamente auto sempre più all'avanguardia che presentano il massimo dei comfort, mentre le storiche vetture che hanno fatto la storia finiscono sempre più nel dimenticatoio. Il sito che abbiamo realizzato è un vero e proprio archivio di auto d'epoca che offre anche la possibilità di salvare i modelli preferiti, sia per averli a disposizione nei successivi accessi, sia per poterli confrontare tra loro.

Il nome del sito nasce dall'unione di Wiki (richiamando il concetto di enciclopedia online) e Car (macchina). A queste due parole abbiamo aggiunto il termine Vintage per completare e definire meglio il contesto tematico.

Il sito si rivolge principalmente agli appassionati di veicoli a quattro ruote, ma è stato progettato per essere accessibile anche ai neofiti di questo settore. Le informazioni fornite sono accurate e aggiornate, ma invitiamo gli utenti a verificarne la validità in base alla propria esperienza e alle fonti ufficiali.

---

## PROGETTAZIONE

Il team ha definito le basi di "WikiCar Vintage" attraverso wireframe dettagliati che hanno permesso di strutturare il sito web. Le idee sono state chiare fin dall'inizio, consentendo di mantenere una corrispondenza del 90% tra i wireframe iniziali e l'implementazione finale. Per la creazione dei wireframe è stato utilizzato lo strumento Lucidchart.

### Struttura del sito web

Di seguito sono illustrate le schermate dell'homepage pre e post login:

![Homepage pre/post login](https://github.com/user-attachments/assets/c61f69b4-9c81-4f28-803e-7264e9a1a686)

Abbiamo implementato funzionalità aggiuntive per gli utenti autenticati, immediatamente visibili dopo l'accesso. Come si può osservare nel wireframe di destra, sono presenti pulsanti dedicati che danno accesso a funzioni esclusive.

#### Schermate di Accesso/Registrazione:

![Accesso/Registrazione](https://github.com/user-attachments/assets/a65d4293-6e6b-4a68-ace1-bd436a1448a7)

#### Schermate delle funzioni aggiuntive:

![Funzioni aggiuntive](https://github.com/user-attachments/assets/dfd0b48b-ee54-4995-82f4-cf0242c47ac9)

### Fogli di stile esterni

La struttura dei CSS è organizzata in tre fogli di stile differenti:

1. **headerstyle.css**: collegato a tutte le pagine dinamiche, eccetto quelle che gestiscono il garage attraverso il database. Nell'intestazione dei file HTML/PHP è presente il riferimento: `<link rel="stylesheet" href="css/headerstyle.css">`.

   **Caratteristiche principali**:
   - Palette cromatica coerente su tutte le pagine per mantenere l'identità visiva
   - Implementazione di un gradiente lineare per creare un effetto sfumato, partendo da un colore scuro in alto e trasparente in basso
   - Header posizionato in modo fisso per garantire visibilità durante lo scrolling
   - Utilizzo di pseudo-classi per gli elementi interattivi:
     ```css
     nav li a:hover{background-color: #fdf4dc; color: #221711;}
     nav li:last-child{margin-right: 0;}
     ```

2. Foglio di stile dedicato all'homepage
3. Foglio di stile dedicato alle pagine di registrazione/login

### Configurazione del database

La configurazione del server database è definita nel file `tswdb.php`. Il server è configurato per operare sulla porta 5432 (porta predefinita per PostgreSQL) con host impostato su localhost. Specifiche di connessione:
- Nome database: gruppo09
- Nome utente: www
- Password: tw2024

Il codice genera una stringa di connessione utilizzata dalla funzione `pg_connect($connection_string)` per stabilire la comunicazione con il database, consentendo operazioni di lettura e scrittura dei dati.

![Configurazione database](https://github.com/user-attachments/assets/e6da553a-8de2-4c08-944b-19593bc36714)

---

## DESCRIZIONE DEL SITO

Il sito presenta 5 pagine web dinamiche che mantengono un'identità visiva coerente grazie all'utilizzo di una palette cromatica specifica (marrone, beige) e del logo aziendale. Di seguito la descrizione dettagliata di ciascuna pagina:

### Registrazione

Questa pagina consente all'utente di registrarsi per accedere a funzionalità avanzate. Il design è stato mantenuto essenziale, con l'inserimento del logo e l'utilizzo di colori che richiamano l'atmosfera vintage. Il form di registrazione implementa la funzionalità "sticky", preservando i dati inseriti in caso di errori di compilazione.

![Pagina di registrazione](https://github.com/user-attachments/assets/fa5a3211-e059-42e9-b963-b017aaf1a5ba)

### Login

Anche questa pagina mantiene un design minimalista, focalizzando l'attenzione dell'utente sull'obiettivo principale: l'accesso ai contenuti. L'interfaccia presenta requisiti di input semplificati rispetto alla pagina di registrazione.

![Pagina di login](https://github.com/user-attachments/assets/29122447-827f-4696-b35a-40380f8bc74b)

### Homepage

La schermata principale di WikiCar Vintage presenta diversi elementi che la rendono coinvolgente:

- **Video introduttivo** con testo di benvenuto e invito all'azione tramite il pulsante "Scopri di più"
- **Catalogo auto** con modelli selezionati, completi di immagini e informazioni essenziali (prezzo e anno)
- **Pulsante "Dettagli"** per ciascun modello, che reindirizza alla pagina Wikipedia dell'auto
- **Funzionalità aggiuntive** per utenti autenticati: confronto modelli e accesso al garage personale
- **Slideshow automatico** nella parte inferiore con immagini tematiche
- **Header funzionale** con:
  - Pulsante "Homepage"
  - Pulsante "Confronta"
  - Pulsante "Area personale" (sostituito da "Registrati" per utenti non autenticati)
  - Barra di ricerca per modelli specifici
  - Menu a tendina accessibile dall'area personale per visualizzare profilo o effettuare logout
- **Footer** con sezione contatti (email del team)

![Homepage sezione superiore](https://github.com/user-attachments/assets/676865b7-7dcb-49fb-8070-58449340d353)
![Homepage sezione centrale](https://github.com/user-attachments/assets/c046fb47-9d2f-4be1-a5ba-689dc55490f3)
![Homepage sezione inferiore](https://github.com/user-attachments/assets/663142d3-4965-48be-9aff-df374b706cd4)

### Confronta

Questa pagina è dedicata al confronto dei modelli selezionati, con la possibilità di ordinarli per prezzo.

![Pagina confronto modelli](https://github.com/user-attachments/assets/712eddd3-ee4f-4046-a517-259b8f944835)

### Garage (Area Personale)

Questa sezione consente agli utenti di:
- Salvare i modelli preferiti per accessi futuri
- Rimuovere auto precedentemente salvate
- Modificare l'immagine del profilo, visibile nell'header tra il pulsante dell'area personale e la barra di ricerca

![Pagina garage personale](https://github.com/user-attachments/assets/a6029801-3edd-4558-95ac-e33aa2137087)

---

## TECNOLOGIE UTILIZZATE

- HTML5 e CSS3 per la struttura e lo stile delle pagine
- PHP per la gestione delle pagine dinamiche
- PostgreSQL per la gestione del database
- JavaScript per le funzionalità interattive

---

## TEAM DI SVILUPPO

Il progetto è stato realizzato nell'ambito del corso universitario da un team di studenti appassionati di sviluppo web e auto d'epoca.
