# Sicurezza dell'informazione 2021-2022

<!-- lezione del 23/09/2021-->
## 00.Introduzione

### Scopo della sicurezza informatica

Il tema della sicurezza informatica è molto importante, in un mondo come quello di oggi, dove l'informatica domina buona parte delle relazioni sociali, lavorative, economiche e politiche. Questo tema è ancora più sentito con l'arrivo del COVID in cui il mondo si presta a digitalizzarsi.
Lo scopo della sicurezza informatica è di proteggere le risorse da accessi indesiderati, garantire la riservatezza delle informazioni, assicurare il funzionamento e la disponibilità dei servizi a fronte di eventi imprevedibili.
Per essere più precisi, è l’insieme dei prodotti, dei servizi, delle regole organizzative e dei comportamenti individuali che proteggono i sistemi informatici di un’azienda.

### I tre capisaldi della sicurezza informatica (CIA Trade Triangle)

L'acronimo CIA viene usato per rappresentare le tre proprietà fondamentali della sicurezza informatica:

- **Confidenzialità** (o **riservatezza**): solo chi è autorizzato può accedere (in sola lettura) a risorse o sapere almeno che esse esistano;
- **Integrità**: solo chi è autorizzato può modificare, eliminare e creare risorse;
- **Disponibilità**: solo chi è autorizzato può accedere alle risorse senza interferenze ed ostacoli.

![cia](./img/img1.png)

A queste proprietà se ne possono aggiungere altre come:

- **Autenticità**: occorre effettivamente dimostrare chi è stato a creare il dato o sapere da chi proviene;
- **Non ridupio**: quando una qualsiasi operazione sul dato è conclusa, si può dimostrare con certezza a una terza parte la paternità di quell'operazione.

### Terminologia

- **Vulnerabilità**: punto debole del sistema che può rendere realizzabile una minaccia;
- **Minaccia**: atto ostile intenzionale o meno che ha un qualsiasi effetto negativo sulle risorse o sugli utenti del sistema;
- **Attacco**: qualsiasi azione che sfrutta una vulnerabilità per concretizzare una minaccia;
- **Contromisura**: azione, dispositivo, procedura o tecnica che consente di rimuovere o ridurre una vulnerabilità.

Esempio:

- **Vulnerabilità**: un ponte ha una crepa;
- **Minaccia**: rischia di crollare;
- **Attacco**: un peso totale eccessivo sul ponte;
- **Contromisura**: cercare di controllare il numero di veicoli sul ponte.

<!-- lezione del 27/09/2021 -->
### Calcolatore sicuro

La sicurezza di un calcolatore deve essere garantita a livello hardware, firmware e software. Ovviamente questa ipotesi non è sempre verificata, ma in questo corso lo si darà per scontato.

### Valutazione, Certificazione, Enti

Gli enti di certificazione definiscono delle metodologie che consentono di verificare che un progetto sia effettivamente sicuro. Applicando questi standard, gli enti garantiscono la sicurezza del prodotto che si installa.

Esempi di standard internazionali per valutazione e certificazione della sicurezza: Orange book del NCSC, ISO 17799, CINI, CERT, ecc.

### Modello a canale insicuro

D'ora in poi per analizzare e studiare i meccanismi di sicurezza si farà riferimento ad un modello molto specifico, chiamato _modello a canale insicuro_.

Questo modello prevede che ci sia una sorgente dei dati, una destinazione a cui sono rivolti e che ci sia un canale che mette in comunicazione sorgente con destinazione.

Si assume che:

- La sorgente sia in un ambiente sicuro (hardware e sistema operativo sicuri);
- La destinazione sia in un ambiente sicuro (hardware e sistema operativo sicuri);
- Il canale sia insicuro, ovvero la possibilità di presenza di intrusori che possano fare degli attacchi su tale canale.

Definito un modello di questo genere, l'obiettivo finale sarà di garantire che la destinazione possa consumare ed interpretare correttamente i dati inviati dalla sorgente.

### Classificazione attacchi

Gli attacchi si classificano in due tipologie:

- **Passivo**: l'intrusore si inserisce sul canale e osserva solo i dati trasmessi. Ad esempio, se il canale è un cavo di rete, si usa uno _sniffer_. Viene minato il requisito di _confidenzialità_;
- **Attivo**: l'intrusore si inserisce sul canale ed altera il normale flusso dei dati. Può:
  - **Modificare** il flusso intenzionalmente per cambiare il contenuto dei dati. Viene minato il requisito di _integrità_;
  - **Aggiungere** nuove informazioni facendo credere alla destinazione che siano state inviate dalla sorgente legittima. Viene minato il requisito di _autenticità_;
  - **Interrompere** il normale flusso impedendo che i dati arrivino alla destinazione. Viene minato il requisito di _disponibilità_.

### Contromisure

Esistono 3 tipologie di contromisure per gli attacchi:

- **Prevenzione**: si previene la possibilità di un attacco;
- **Rilevazione**: si rileva un attacco in corso;
- **Reazione**: si reagisce dopo che un attacco è avvenuto.

Il tipo di contromisura da adottare viene scelta anche in base al sistema e a cosa si vuole proteggere (nel corso il focus è incentrato sui dati).

La contromisura ha:

- Un costo in termini economici, di impegno delle risorse informatiche del sistema, di impatto sugli utenti;
- Una sua efficacia (a fronte di una certa minaccia) e dei suoi effetti collaterali (la creazione di nuove vulnerabilità).

Una certa contromisura, quindi, deve essere applicata attentamente, valutando sia la probabilità che si verifichi una certa minaccia in grado di sfruttare una certa vulnerabilità, sia il danno che ne discende. Questa attività è chiamata _analisi del rischio_.

Come i [veri ingegneri dimostrano](https://youtu.be/EOR8Uz27s3Y?t=420), l'obiettivo è capire a fronte di più possibilità progettuali quale risulti la migliore scelta per garantire la [sicurezza](https://twitter.com/AndreaDraghetti/status/1455576154425933828) del proprio [sistema](https://raidforums.com/Thread-Italy-s-Ministery-of-Healthcare-hacked-and-Blackmails-WhiteHatsicurezza) e dei propri dati.

### Possibili contromisure per attacchi passivi

L’unica contromisura da utilizzare è la _prevenzione_. La _rilevazione_ e la _reazione_ risultano inutili dopo che l'attacco è avvenuto poiché l'intrusore ha intercettato i messaggi.

Si può:

- **Impedire** l'accesso al canale. Ciò viene implementato tramite l'utilizzo di canali dedicati tra sorgente e destinazione. Questa soluzione non è tuttavia né economicamente sostenibile né scalabile;
- **Cifrare** i dati da inviare, ovvero rendere incomprensibili i dati trasmessi, tranne al destinatario legittimo.

### Possibili contromisure per attacchi attivi

Le contromisure da adottare, a differenza degli attacchi passivi, includono anche la _rilevazione_ e la _reazione_. L'unico modo per _prevenire_ un attacco attivo è quello di controllare l'accesso al canale. Tuttavia, è quasi impossibile per i motivi specificati in precedenza. Questa contromisura, quindi, non viene usata.

Si può:

- **Aggiungere** un attestato di integrità e/o di autenticità. In questo modo la destinazione è in grado di comprendere se il flusso dei messaggi è integro e/o autentico oppure se è stato manomesso (integrità e autenticità);
- **Impedire** l'interruzione del flusso di dati. La destinazione si assicura che abbia ricevuto il numero corretto di messaggi (disponibilità).

## 01.Dati Sicuri

### Algoritmi e protocolli

Per proteggere i dati a fronte di eventuali attacchi occorre utilizzare delle trasformazioni.

![cia](./img/img26.png)

L'_algoritmo_ è una sequenza di istruzioni, e rappresenta una singola trasformazione (blocco `Ts` o `Td`).

![cia](./img/img27.png)

Nei casi complessi, è necessario che si eseguano più trasformazioni e la sequenza da eseguire deve essere ben precisa. In questo caso, si parla di _protocollo_.

In alcuni casi è necessario l'intervento di una terza entità che operi da _arbitro_/_giudice_.

### Come rendere sicuri i dati

La sicurezza dei dati può essere garantita tramite l'impiego di una codifica ridondante dei dati, che consiste nell'aggiunta di bit in più rispetto alla lunghezza del messaggio originario. In tal casi si ha ridondanza in termini di:

- **Spazio**: necessario per la memorizzazione;
- **Tempo**: maggiore tempo di trasferimento.

### Crittografia e Crittoanalisi

La disciplina che studia gli algoritmi ed i protocolli da applicare dal lato sorgente e lato destinatario di un canale insicuro è detta _crittologia_. A sua volta è formata da due distinte e correlate discipline:

- **Crittografia**: è la disciplina che studia gli algoritmi che si possono adottare per proteggere i dati in in termini di riservatezza, autenticità e integrità;
- **Crittoanalisi**: è la disciplina che studia il modo in cui è possibile rompere le trasformazioni che proteggono i dati in termini di riservatezza, autenticità e integrità.

Nel corso si studierà solo crittografia.

### I principi della difesa

Ci sono tre principi che guidano la progettazione delle trasformazioni:

- Deve essere impossibile _sapere_ la trasformata/i calcoli da parte dell'intrusore;
- Deve essere impossibile _dedurre_ la trasformata/i calcoli da parte dell'intrusore;
- Deve essere impossibile _indovinare_ la trasformata/i calcoli da parte dell'intrusore.

### Proteggere la proprietà di confidenzialità

Per proteggere i dati si ha bisogno di una trasformata che renda incomprensibile il contenuto. In questo modo, l'intrusore non sarà in grado di capire i messaggi.
La riservatezza si ottiene con una trasformazione di tipo _preventivo_: l'intrusore che accede ai dati non sarà in grado di comprenderli.

![confidenzialità](./img/img2.png)

Lo scenario applicativo è il seguente:

- La sorgente `A` non può inserire i dati `m` sul canale insicuro, ma deve prima trasformarli tramite un'encryption `E`;
- Questa trasformazione è conosciuta solo dalla sorgente `A` ed è l'unica in grado di eseguirla;
- I dati `m` vengono trasformati in dati incomprensibili `c`;
- La destinazione `B` riceve `c` e tramite la trasformazione di decryption `D`, risale al contenuto dei dati `m`.

Devono essere rispettate le seguenti proprietà:

- **Segretezza**: la trasformazione `E` e `D` sono conosciute solo rispettivamente dalla sorgente e dal destinatario, non è possibile risalire al messaggio in chiaro;
- **Calcoli difficili**: dato il messaggio `m` deve essere facile calcolare il messaggio cifrato. L'operazione inversa, se non si conosce la trasformata di `D`, deve essere computazionalmente difficile.

Altre considerazioni:

- **Il flusso è bidirezionale**: lo schema della figura può essere applicato sia da `A` verso `B` che da `B` verso `A`. Ovviamente `B` potrà eseguire l'operazione di encryption, mentre `A` di decryption;
- **A e B non è detto che siano entrambi online**: possono essere online contemporaneamente oppure A online e B offline. I messaggi possono essere decifrati in momenti diversi;
- **B = A**: la sorgente potrebbe coincidere con la destinazione. Ad esempio, vogliamo cifrare dei dati che abbiamo sul nostro hard disk. Quando effettuiamo il logout dal sistema essi vengono cifrati mentre quando effettuiamo il login li decifriamo.

### Proteggere la proprietà di integrità

Proteggere l'integrità vuol dire costruire delle trasformazioni in grado di rilevare modifiche al contenuto dei dati trasmessi. In questo caso, la contromisura da adottare è quella della _rilevazione_ perché le modifiche ai messaggi sul canale non possono essere evitate a priori.

Se si vuole costruire una trasformazione che protegga l'integrità, bisogna far si che la sorgente utilizzi ridondanza al messaggio e affianchi al dato iniziale un'informazione aggiuntiva che deve essere costruita opportunamente. Questa informazione si chiama _riassunto_ o _impronta_. La sua dimensione deve essere inferiore perché la si deve poi trasmettere sul canale.

Il riassunto lo si calcola tramite una funzione hash.

![integrità](./img/img3.png)

In generale, una funzione hash `H` è una funzione che prende un dato `m` di lunghezza arbitraria e restituisce in uscita un'impronta `H(m)`.

Una funzione hash ha la seguente proprietà:

- **Calcoli difficili**: dato il messaggio `m` deve essere facile calcolare la sua impronta. L'operazione inversa invece deve essere computazionalmente difficile;

Oltre alla proprietà appena scritta, risulta importante che essa sia _crittograficamente sicura_ e abbia anche le seguenti proprietà:

- **Comportamento da "oracolo casuale"**: se si decide che l'impronta sia costituita da `n` bit, le possibili uscite della funzione hash sono `2^n`. 
Considerato il messaggio `m`, bisogna fare in modo che la probabilità che esca un' uscita rispetto ad un'altra sia la stessa. Inoltre, se il messaggio viene ripetuto, la risposta sarà la medesima, dato che è stata assegnata precedentemente dall'oracolo.

![zeus](./img/zeus.jpg)

- **Resistente alle collisioni**: per un intrusore deve essere molto difficile individuare due messaggi che abbiano la stessa impronta.
È inevitabile che due messaggi diversi possano avere in uscita la stessa impronta perché lo spazio di input è molto più grande dello spazio di output (`m > n`). Per un intrusore deve essere computazionalmente difficile trovare un messaggio `m2` con impronta `H(m2)` uguale a quella di `m1`, cioè `H(m1)`.
Ad esempio, se i messaggi sono `10` e il numero di bit è pari a `3`, le possibili uscite della funzione hash sono `8` e alcuni messaggi avranno sicuramente la stessa impronta.

Le funzioni hash possono essere classificate in due categorie:

- **Funzioni hash semplici**: l’individuazione di due messaggi con la stessa impronta è un calcolo facile. In presenza di certi disturbi, è più probabile che i bit che variano siano sempre gli stessi, per cui è possibile calcolare la probabilità;
- **Funzioni hash sicure**: se le funzioni hash sono crittograficamente sicure (vedi proprietà scritte in alto).

![attestazioneIntegrità](./img/img4.png)

Lo scenario applicativo è il seguente:

- La sorgente `A` manda sul canale insicuro un messaggio `m`;
- L'impronta `H(m)` deve viaggiare su un canale sicuro per evitare che un intrusore possa sostituire `m` con un altro messaggio `m'` e di conseguenza sostituire anche `H(m)` con `H(m')` (la funzione `H` non è segreta);
- `B` applica la funzione hash al messaggio ricevuto, e verifica che l'hash ricevuto coincida con quello ottenuto;
- Se si equivalgono, il messaggio è stato trasmesso correttamente. In questo modo la destinazione è in grado di rilevare se il messaggio ha subito modifiche.

### Esempio

Le trasformazioni possono essere combinate fra di loro. Ad esempio, per garantire la riservatezza e l'integrità dei dati si possono usare in questo modo:

`p = m || H(m)` 

`c = E(p)`

`p* = D(c*) = m* || H*(m)`

`H*(m) =? H(m*)`

Il protocollo che assicura riservatezza e integrità dei dati è costituito dai questi passi:

- La sorgente esegue due trasformazioni:

  - **Passo 1**: viene applicata la funzione hash crittograficamente sicura e la si concatena con il messaggio;
  - **Passo 2**: viene applicata la funzione di encryption `E`. Dato che il messaggio `c` è cifrato, lo si può inviare direttamente sul canale insicuro.
- La destinazione esegue due trasformazioni:
  - **Passo 3**: la destinazione riceve `c` che può essere, o quello inviato dalla sorgente o un altro che è stato modificato dall'intrusore. Per questo motivo, dato che non si ha la certezza, si indica il messaggio `c` con `c*`. La destinazione applica la funzione `D` su `c*` ottenendo di nuovo `m* || H*(m)`;
  - **Passo 4**: per vedere se il messaggio sia integro, dobbiamo verificare che la funzione crittograficamente sicura `H(m*)` coincida con `H*(m)`. Se non coincidono il messaggio viene scartato.

L'intrusore può modificare solo casualmente i bit del cifrato perchè calcolarsi l'operazione inversa senza conoscere la trasformata `D` è computazionalmente difficile. Inoltre, le trasformate `D` e `E` sono segrete.

### Esempio 2

In questo caso, l'integrità è rispettata mentre la riservatezza no:

`p = m`

`c = E(p) || H(m)`

`p* = D(c*) = E*(p) || H*(m)`

`m* = D(E*(p))`

`H*(m) =? H(m*)`

L'**integrità** _è rispettata_ perché se si modificano i bit di:

- **E(p)**: se si cambiano dei bit di `E(p)` casualmente, è difficile che corrisponda la stessa impronta per la proprietà alla _resistenza alle collisioni_;
- **H(m)**: H(m) corrisponde a un altro messaggio per la resistenza alle collisioni;
- **E(p) e H(m)**: la probabilità che il messaggio modificato corrisponda proprio a quell'impronta che è anch'essa modificata risulta essere molto bassa.

La **riservatezza**, invece, _non è rispettata_ perché:

- L'intrusore ha a disposizione molte informazioni di contesto. 
L'intrusore sa che Luca sta trasmettendo dei dati alla sua amata Lucia. Dato che `E(p)` è impossibile che lo sappia, da un messaggio scelto in chiaro `m'` si può calcolare l'impronta `H(m')`. Se nota che l'impronta è la stessa, la riservatezza del messaggio è violata.

### Esempio 3

In questo caso, la proprietà di integrità _non viene rispettata_ mentre quella di riservatezza sì:

`p = m`

`c = E(p) || H(E(p))`

`p* = D(c*) = E*(p) || H*(E(p))`

`m* = D(E*(p))`

`H*(E(p)) =? H(E(m*))`

La **riservatezza** _è verificata_ perché:

- Non si riuscirebbe a confrontare l'impronta `H(m')` scelta dall'intrusore con quella `H(E(p))`, poiché è assente la parte di cifratura del messaggio.

L'**integrità** non è garantita:

- L'intrusore può modificare `E(p)` e ottenere `E*(p)` e sostituire `H(E(p))` con `H(E*(p))`. Se `m` è un messaggio senza un particolare significato (ad esempio un numero), `D(E(p))` restituisce `m*` e la destinazione potrebbe non accorgersi che `m*` non sia corretto. Se invece `m` è un messaggio dotato di significato, la destinazione potrebbe accorgersi che `m*` è scorretto, e quindi può scartato.

### Proteggere la proprietà di autenticità

Chi riceve un messaggio è importante che sappia chi è l'autore o chi lo ha inviato. L'intrusore può creare _ad hoc_ un messaggio, inserirlo nel normale flusso dei dati e fingere di provenire dalla sorgente originale. Questo attacco lo si può solo _rilevare_.

![autenticazione](./img/img5.png)

Per garantire l'autenticità di una sorgente, si deve costruire una trasformazione `S` che, dato un messaggio `m`, deve produrre in uscita un _attestato di autenticità_ `c` che rappresenta in maniera non imitabile il messaggio `m` originale.

La destinazione riceve l'attestato di autenticità `c` ed effettua una trasformazione `V` sull'attestato di autenticità, producendo in uscita una risposta che afferma l'autenticità o meno del messaggio. In caso affermativo viene restituito il messaggio `m`.

Devono essere rispettate le seguenti proprietà:

- **Calcoli difficili**: dato il messaggio `m` deve essere facile calcolare l'attestato di integrità `c`. L'operazione inversa invece non è fattibile;
- **Segretezza**: la trasformazione `S` deve essere segreta per la sorgente perché altrimenti eventuali intrusori potrebbero effettuare la trasformazione. Invece, `V` può essere noto, dato che qualsiasi destinazione deve essere in grado di dire se l'attestato è autentico o no.

Alcune considerazioni:

- **A e B non è detto che siano entrambi online**: `B` può verificare l'autenticità in un secondo momento;
- **B = A**: se nel file system vogliamo garantire la loro autenticità, durante la fase di logout e login, oltre a decifrarli, occorre verificare che siano anche autentici.

<!-- lezione del 29/09/2021-->
<!-- doppione -->
<!-- ### Garantire autenticità

Per garantire autenticità si ricorre all'operazione di firma o _sign_, che produce un certificato di autenticità e che viene inserito e inviato insieme al testo dell'informazione eventualmente cifrato. La destinazione avrà una funzione `V` di _verify_, utilizzata per verificare se il certificato è effettivamente autentico e per ricavare il mittente.

Viene utilizzato per rilevare _fabrication_, un attacco attivo in cui l'intrusore crea un messaggio dichiarandolo come proveniente da una sorgente legittima.

Vengono quindi rispettati due principi:

- **Trasformazioni segrete**: in questo caso l'operazione di _sign_. Nessun altro, oltre alla sorgente legittima, deve conoscere la trasformazione che è stata applicata, altrimenti chiunque può effettuare _fabrication attack_.

- **Calcoli impossibili**: i calcoli per costruire un messaggio apparentemente autentico e senza conoscere la trasformazione della sorgente devono essere complessi.-->

Esistono 2 schemi alternativi per realizzare sign-verify: _la firma digitale_ e _hash_.

### Firma digitale

Il primo schema alternativo per realizzare _sign-verify_ è la _firma digitale_.

![firmadigitale](./img/img6.png)

Lo scenario applicativo è il seguente:

- La sorgente `A` prende il messaggio `m` e lo sottopone a una trasformazione `H`, costruendo l’impronta `H(m)`, che garantisce l’integrità;
- La funzione `S` di _sign_ viene eseguita su `H(m)`, e sul canale di comunicazione viene trasmesso `m` concatenato con `c`;
- La destinazione `B` verifica tramite `V` che `c` proviene dalla sorgente leggittima. In questo modo viene verificata l'autenticità del messaggio. Dato che `c` contiene `H(m)`, possiamo verificare anche la proprietà di integrità.

Questo schema ha due vantaggi rispetto allo schema normale di _sign_:

- **Efficienza**: la funzione di _sign_ `S` è una trasformazione costosa. Anzichè applicare `m` direttamente a _sign_, viene applicata a `H(m)`, che ha dimensione inferiore, rispetto a `m`. Si può applicare anche all'impronta perché è univoca per la proprietà di resistenza alle collisioni;
- **Avere subito la disponibilità del dato**: si può prendere direttamente `m` e si verifica l'autenticità in un secondo momento, come previsto dallo schema a blocchi.

Questo schema assicura anche la proprietà di:

- **Non ripudio**: dato che la sorgente `A` è l'unica che esegue `S`, non può disconoscere in un secondo momento l'attestato di autenticità;
- **integrità**: per la funzione hash.

### Hash del messaggio e di un segreto

Il secondo schema alternativo per realizzare _sign_-_verify_ è l'uso di un _hash_.

![hashs](./img/img7.png)

- Due entità `A` e `B` (mittente e destinatario) condividono un segreto `s`;
- `A` calcola `H(m || s)` a partire da `m`, cioè il messaggio che si vuole trasferire, e invia alla destinazione `m || H(m || s)`;
- Dato che il messaggio viaggia sul canale insicuro, l'intrusore può aver modificato il messaggio. Per questo motivo `m` si indica con `m*`;
- La destinazione riceverà il messaggio `m*` e andrà a calcolare `H(m* || s)`;
- Se `H(m* || s) = H(m || s)`, le due proprietà sono state garantite (integrità e autenticità).

Rispetto allo schema di _firma digitale_, **non** viene garantita la proprietà di _non ripudio_, poiché la sorgente `A` potrebbe sospettare che la destinazione `B` si sia costruita un `H(m || s)`, e che la sorgente `A` non abbia inviato nessun messaggio. Questo è dovuto al fatto che `A` e `B` condividono un segreto, quindi non si è in grado di risalire a chi è effettivamente l'autore del messaggio inviato.

### Firma digitale vs Hash del messaggio e di un segreto

Lo schema _hash_ risulta essere più efficiente rispetto alla _firma digitale_, ma potrà essere usato solamente quando si è sicuri del corretto comportamento di `A` e `B`. Può essere utilizzato, ad esempio, con sistemi IoT che richiedono consumi ridotti di batteria e alta efficienza.

Viceversa, la firma digitale è meno efficiente poiché ha la funzione di _sign_ `S` ma garantisce il _non ripudio_.

### Esempio 1

In questo caso, si invia un messaggio che rispetta le proprietà di **riservatezza**, **autenticità** e **integrità**:

`p = m || H(m || s)`

`c = E(p)`

`p* = D(c*) = m* || H*(m || s)`

`H*(m || s) =? H(m* || s)`

Il messaggio `m` viene concatenato al certificato e cifrato dal client.

Questo schema è usato dal protocollo SSL il quale adotta le funzioni hash crittograficamente sicure con un segreto per costruire il certificato di autenticità.

Da un punto di vista di efficienza, le trasformazioni in fase di ricezione sono due:

- Decodifica del messaggio cifrato;
- Autenticazione tramite funzione hash crittograficamente sicura.

### Esempio 2

In questo caso, si invia un messaggio che rispetta le proprietà di **riservatezza** e **autenticità**:

`p = m`

`c = E(p), H(m || s)`

Il messaggio `m` viene cifrato e viene inviato il cifrato concatenato con l'attestato di autenticità costruito sul messaggio.

Questo schema viene usato dal protocollo SSH. Permette di aprire shell remote sicure.

Da un punto di vista di efficienza, le trasformazioni in fase di ricezione sono due:

- Decodifica del messaggio cifrato;
- Autenticazione tramite funzione hash crittograficamente sicura.

### Esempio 3

In questo caso, si invia un messaggio che rispetta le proprietà di **riservatezza** e **autenticità**:

`p = m`

`c = E(p), H((E(p) || s)`

In fase di invio, il messaggio viene cifrato e autenticato, mentre in fase di ricezione viene controllato l'attestato di autenticità e decifrato il messaggio.

Questo schema viene usato dal protocollo IPsec. È un protocollo SSL a livello di trasporto (TCP). Vengono creati _socket sicuri_ in cui i messaggi sono autenticati.

La ricezione è _efficiente_: viene risparmiata una trasformazione. Se il testo cifrato ha subito delle modifiche, chi riceve verifica il certificato e, se qualche operazione illegale è avvenuta, si evita l'operazione di decifratura.

### Anonimato/Identificazione

Per _identificazione_ si intende un insieme di azioni che richiedono di identificare chi sta partecipando a un'interazione. Ad esempio, risulta indispensabile quando si effettua un pagamento o quando si vuole accedere a certe risorse. L'opposto dell'identificazione è l'_anonimato_. Un esempio di utilizzo è nel caso di voto elettronico o di pagamento via criptovaluta.

Il processo di identificazione ha le seguenti caratteristiche:

- **Real-time**: l'identificazione deve avvenire entro un breve intervallo di tempo prestabilito e non oltre;
- **Efficienza**: l’identificazione di una entità deve avvenire in maniera _efficiente_, dato che deve il processo deve essere real-time;
- **Sicurezza**: possono essere presenti:
  - **Falsi positivi**: una determinata persona possiede diritti di accesso, ma non riesce ad accedere. Ciò causa inefficienza. Bisogna minimizzare questo numero;
  - **Falsi negativi**: l'accesso viene effettuato da persone non autorizzate. Occorre prevenire la presenza di falsi negativi.

Un sistema di identificazione si può basare su:

- **Conoscenza**: sistemi che si basano sulla conoscenza di un'informazione (password, pin, chiavi di sicurezza);
- **Possesso**: sistemi che si basano sul possesso di un oggetto che solo quella persona può avere (carte magnetiche, token, smart card);
- **Conformità**: sistemi che si basano su una caratteristica di un'entità (dati biometrici come impronte o analisi della retina, dati comportamentali come il numero di login durante il giorno, quante volte un impiegato entra ed esce dall'ufficio etc.)

### Protocollo di identificazione

Un processo d’identificazione avviene tramite l'uso di protocolli.

![kronk](/img/img8.png)

Qualunque protocollo di identificazione prevede due fasi:

- **Registrazione**: durante la registrazione, l’identificando ed il verificatore concordano e memorizzano rispettivamente il segreto `S` con cui l'identificando si farà riconoscere ed il _termine di paragone_ `T = H(S)`, che consentirà al verificatore di accertare che l'identificando conosce `S`. Il verificatore non può memorizzare direttamente il segreto `S` perchè se è malintenziato potrebbe usarlo a sua volta;
- **Identificazione**: l'identificando e il verificatore devono essere entrambi online (univocità del tempo).
Questo processo può scomporsi in:
  - **Dichiarazione**: l'identificando dichiara la sua identità;
  - **Interrogazione**: il verificatore interroga l'identificando che deve dimostrare la sua identità;
  - **Dimostrazione**: l'identificando deve fornire la stessa prova che aveva fornito in fase di registrazione. La dimostrazione deve essere semplice per chi è il legittimo identificando, mentre complesso per l'intrusore.

![kronk](/img/kronk.jpeg)

In generale, un intrusore può:

- Dedurre o indovinare la prova (il segreto);
- Rubare il dispositivo (smartcard);
- Replicare una prova che ha viaggiato sul canale in una legittima transizione di identificazione e riutilizzarla.

### Funzioni one-way

Una funzione `f` è detta unidirezionale se:

- È invertibile (biunivoca);
- È semplice da calcolare: dato lo spazio di input `x` è facile calcolare l'uscita `f(x)`;
- È difficile, dato `f(x)`, risalire a `x` che ha originato l'output.

Ad esempio, sono funzioni unidirezionali la:
- Funzione hash crittograficamente sicura `H`;
- Funzione di cifratura `E` e `D`;
- Funzione di sign `S`.


Nella teoria della complessità computazionale, non esistono funzioni che siano unidirezionali. In crittografia, invece, sono state individuate diverse funzioni che sono candidate ad avere un comportamento di unidirezionalità (come ad esempio le funzioni di compressione, di cifratura e di firma). Vengono chiamate _pseudo-unidirezionali_ le funzioni che appaiono unidirezionali se non si possiede una particolare informazione sulla loro costruzione.

### Trasformazioni segrete

Possiamo avere tre approcci:
- **Macchine a funzionamento segreto**: non conoscere la struttura della macchina. Ad esempio, la _macchina enigma_;
- **Algoritmo**: le operazioni sono segrete. Ad esempio, gli algoritmi delle prime SIM, algoritmi USA durante la guerra fredda;
- **Parametro**: la macchina e l'algoritmo sono noti, ma un parametro di ingresso dell'algoritmo è segreto (chiave crittografica).

I primi due approcci non sono molto funzionali:
- **No manutenibilità**: _security through obscurity is always a bad idea_. <!--stfu Microsoft and Apple)-->
- **No scalabilità**: vedi sopra; <!--apple-->
- **No Certificazione**: chi garantisce che quello che si sta usando è davvero sicuro, se nessuno conosce come è stato costruito?

L'approccio usato al giorno d'oggi, quindi, risulta essere la trasfrormazione segreta tramite _parametro_.

![chiave](/img/img9.png)

- Con `T` si indica la trasformazione nota (quindi la conosce anche l'intrusore);
- Con `k` indichiamo la _chiave_, ovvero il parametro non noto, in ingresso;
- Con _spazio delle chiavi_ si intende l'insieme delle ![formula](https://render.githubusercontent.com/render/math?math=\color{red}\2^n) possibili configurazioni dove `n` è il numero di bit della chiave. La chiave è costituita da una delle ![formula](https://render.githubusercontent.com/render/math?math=\color{red}\2^n) configurazioni. Più è grande `n`, più è complicato per un intrusore indovinare la chiave.

### Algoritmo forza bruta

Un intrusore può sempre disporre di un _algoritmo di ricerca esauriente_, noto come _algoritmo di forza bruta_.

![intrusore](./img/img10.png)

Se l'intrusore non conosce la chiave, può esplorare tutto lo spazio delle chiavi. Se `n` è il numero di bit della chiave e $ 2^{n} $ è il numero totale di configurazioni, effettua diversi tentativi fino a quando non indovina la chiave. 
Occorre conoscere la trasformata `T`. Se il cifrato che ottiene è uguale a quello presente sul canale, allora ha avuto successo nel trovare la configurazione corretta.

### Relazioni fra le chiavi

Si possono individuare due famiglie di cifrari:

- **Cifrari a chiavi simmetriche**: le chiavi `ks` e `kd` o sono uguali o facilmente ricavabili l'una dall’altra, quindi devono essere tenute segrete;
- **Cifrari a chiave pubbliche**: le chiavi `ks` e `kd` sono diverse e una delle due è difficilmente calcolabile dall'altra. Ogni entità dispone di una coppia di chiave `ks` e `kd`, di cui `ks` è segreta, mentre `kd` pubblica.

### Proprietà delle chiavi simmetriche

Le chiavi simmetriche devono avere le seguenti proprietà:

- **Robustezza**: un intrusore non deve essere in grado facilmente di individuare la chiave;
- **Riservatezza**: il sistema deve garantire la riservatezza della chiave perché deve essere segreta;
- **Integrità**: si deve essere sicuri che la chiave non sia stata alterata altrimenti non è possibile usarla;
- **Autenticità**: la chiave è conosciuta solo dalla sorgente e dalla destinazione autentica.

### Proprietà delle chiavi asimmetriche

Le chiavi asimmetriche devono avere le seguenti proprietà:

- **Robustezza**: un intrusore non deve essere in grado facilmente di individuare la chiave privata `ks`;
- **Riservatezza**: la riservatezza è legata alla chiave `ks` privata;
- **Integrità**: è importante che le chiavi `ks` e `kd` siano quelle corrette e non modificate;
- **Autenticità**: si deve essere certi che la chiave pubblica `kd` appartenga a un certo utente.

### Crittoanalisi

Come riportato precedentemente, la crittoanalisi si occupa di progettare tutte quelle trasformazioni che minano le proprietà di sicurezza.
Bisogna evitare che un intrusore possa:

- Indovinare la chiave;
- Intercettare la chiave;
- Dedure la chiave.

### Indovinare la chiave

È sempre possibile risalire alla chiave tramite attacco con _forza bruta_. Per ridurre le probabilità di successo di questo attacco, occorrono alcuni accorgimenti:
- **Lo spazio delle chiavi deve essere molto grande**: se `n` è il numero di bit che rappresenta la chiave, $ 2^{n} $ è l'insieme delle possibili configurazioni. Più è grande `n` più è difficile per un intrusore indovinare la chiave;
- **I bit devono essere casuali**: bisogna evitare che un intrusore possa trovare un modo per risalire alla chiave;
- **Limitare il numero di prove che l'intrusore ha a disposizione**, come ad esempio il pin del bancomat. Dopo tre tentativi si disabilita l'accesso;
- **Cambiare frequentemente la chiave**: se i dati devono essere mantenuti a lungo termine, occorre cambiare frequentemente la chiave. In questo modo, si riducono le probabilità di individuare quest'ultima da parte dell'intrusore.
<!--Fine correzione 04/11, ore 20:28-->

### Intercettare la chiave

La chiave se è un parametro può essere intercettata. Ogni volta che si deve eseguire l'algoritmo, vuol dire che bisogna trasferire in RAM l'algoritmo e i parametri dato che i calcolatori usano l'architettura di Von Neumann:

- Il parametro sicuramente deve essere memorizzato in maniera sicura (cifrato) e solo il proprietario deve avere accesso alla cella in cui è memorizzata la chiave;
- Si deve evitare anche che quando si mette il parametro sul bus non ci sia modo di intercettarlo;
- Ci deve essere anche un supporto alla sicurezza che protegga la RAM;
- L’unità di elaborazione dopo aver eseguito l'algoritmo deve cancellare poi accuratamente il dato dalla memoria.

Nel corso, l'hardware è sicuro ma non è detto che lo sia.

Esistono diverse celle di memoria dove può risiedere la chiave:

- **Soluzione meno robusta**: calcolatore costituito da HDD, CPU e RAM;
- **Soluzione intermedia**: supporto di memorizzazione come ad esempio, smart card passiva in cui si conserva solo il segreto. Si ha bisogno di un pc per poter eleborare. Quindi il segreto deve passare per la RAM;
- **Soluzione sicura**: smart card attiva in cui c'è anche una CPU e RAM. Nulla viene eseguito all'interno di un calcolatore.

I motivi per cui la soluzione viene classificata come sicura, intermedia e meno robusta si intuiscono leggendo la parte iniziale di questo paragrafo.

### Esempio

Nei file system, una chiave `s` viene memorizzata in forma cifrata in una parte della memoria chiamata _portachiavi_.

![intrusore](./img/img53.png)

La chiave `s` viene generata una volta (o più, se si decide di cambiarla
nel tempo) tramite un RNG (si vedrà più avanti che cosa è) ed è subito cifrata con la funzione `E` accoppiata ad `u`. Poi è portata e memorizzata in modo cifrato sulla memoria `M` (ovvero `Eu(s)`).

In seguito, per eseguire gli accessi esiste una _passphrase_ dettata
decisa dall’utente, facile per lui da ricordare, su cui viene eseguita
una funzione hash per calcolarne l’impronta `u`. Una volta creata
`u`, essa deve essere impiegata per decifrare `s`. Una volta decifrata la chiave essa viene utilizzata per tradurre il testo e quindi calcolare y = T(s,x). Immediatamente dopo, una primitiva cancella `s` dalla memoria del processore (grazie al wiper sicuro).

In caso di smarrimento o danneggiamento della passphrase è necessario un sistema di _recovery_.

## Dedurre la chiave

Esistono diverse tipologie di attacco:

- **Attacco con solo testo cifrato**: l'intrusore dispone esclusivamente di testo cifrato che lo preleva dal canale insicuro. L'intrusore può sfruttare conoscenze, ipotesi sul linguaggio di origine che è stato usato per scrivere il messaggio cifrato, può disporre di tecniche e statistiche per effettuare determinati attacchi. Avendo il testo cifrato e queste tecniche può dedurre delle informazioni sul testo originario o sulla chiave stessa;
- **Attacco con testo in chiaro noto**: l'intrusore ha la fortuna di avere il testo in chiaro e il cifrato. In questo modo si può studiare il codice usato per cifrare il testo;
- **Attacco con testo in chiaro scelto**: l'intrusore sceglie un testo in chiaro e ha la possibilità di cifrare il messaggio ingannando la vittima;
- **Attacco con testo cifrato scelto**: l'intrusore riesce a farsi decifrare un testo cifrato da lui scelto dalla sorgente legittima.

La contromisura da adottare è quella _preventiva_: il legame tra il testo in chiaro ed il testo cifrato deve essere così ben nascosti da far apparire quest’ultimo all’intruso come una variabile aleatoria che assume con uguale probabilità tutti i suoi possibili valori.

## Teoria della complessità

Finora si è sempre usato i termini di _calcolo facile_. E’ però utile avere a disposizione una definizione rigorosa: per questo motivo si fa riferimento alla _Teoria della complessità_.

La complessità computazionale può essere determinata con una serie di indicatori:

- **Tempo di esecuzione**: ovviamente non è un tempo _vero_ perché ogni tecnologia ha un concetto di tempo diverso. Per misurare il tempo di esecuzione si fa riferimento al numero di operazioni eseguite dall'algoritmo per terminare;
- **Memoria occupata dal programma**
- **Memoria occupata dai dati**

Negli algoritmi di crittografia gli ultimi due parametri non sono presi in considerazione.

### Definizioni

- **Tempo disecuzione di un algoritmo**: si intende il numero di operazioni `N` che occorre eseguire per terminare l'algoritmo quando il dato d’ingresso è rappresentato da una stringa di `n` bit `n = log [valore del dato]`).\
\
Il numero `n` (dimensione input) incide sul numero di operazioni richieste, in alcuni casi, anche il valore stesso può incidere sul numero di passi da eseguire. Dunque, a parità di `n`, si hanno diversi valori di `N`.

- **Tempo di esecuzione nel caso peggiore**: si intende il numero massimo di operazioni $ N_{max} $ che occorre eseguire per qualsiasi dato d’ingresso di `n` bit.\
\
Tramite la notazione del _O grande_ è possibile evidenziare come incrementa il tempo di esecuzione dell’algoritmo al crescere senza limiti della dimensione dell’input.

### Classificazione degli algoritmi

Gli algoritmi possono essere classificati in due categorie:

- **Tempo polinomiale**: algoritmo in grado di completare l'elaborazione di una dimensione `n` di dati in ingresso in un tempo di esecuzione pari a $ O(n^{k}) $ dove `k` è un numero intero positivo;
- **Tempo esponenziale**: algoritmo in grado di completare l'elaborazione di una dimensione `n` di dati in ingresso in un tempo di esecuzione pari a $ O(e^{n}) $ dove `n` è la dimensione `n` di dati in ingresso.

### Classificazione dei problemi

Un problema si può classificare in:

- **Facile**: se esiste un algoritmo polinomiale in grado di risolverlo su una macchina di Turing deterministica;
- **Difficile**: se non sono stati fino ad ora individuati
(e probabilmente non saranno mai individuati) algoritmi che lo risolvono in tempo polinomiale.

### Complessità e Sicurezza

Per ottenere sicurezza è necessario:

- **Trovare il valore n al di sopra del quale l'andamento diventa esponenziale**: se l'andamento è polinomiale l'intrusore è capace di entrare nel sistema. Dunque, la chiave dovrà avere un numero di bit in modo tale che la ricerca nello spazio delle chiavi diventi esponenziale;
- **Vedere qual è il caso migliore**: l'intrusore non si deve trovare di fronte ad istanze del problema di facile soluzione.

Le unità di misura che si possono adottare sono:

- **Anno MIPS**: il tempo di esecuzione di un attacco è espresso in anni MIPS. Questa unità di misura fa riferimento a quante istruzioni può elaborare un calcolatore e con il passare degli anni il numero di riferimento aumenta. Attualmente, un calcolatore è in grado di eseguire un milione di istruzioni al secondo. Questo parametro dipende dalla tecnologia;
- **Livello di sicurezza**: assume come riferimento il tempo
d’esecuzione dell’algoritmo di ricerca esauriente. L’algoritmo di ricerca esauriente è in grado di risolvere tutti i problemi e quindi si deve individuare qual è il numero di bit della chiave tale per cui l'andamento diventa esponenziale. Il parametro è indipendente dalla tecnologia.

Naturalmente è possibile passare dalla misura in anni MIPS a quella in livello di sicurezza e viceversa.

![dedurre](./img/img13.png)

Una chiave deve avere un numero minimo di bit:

- **In una chiave simmetrica**: se si usa una chiave privata a 128 bit, l'intrusore è difficile che riesca a trovarla perché l'andamento dell'algoritmo diventa esponenziale;
- **In una chiave asimmetrica**: in questo caso i bit non possono essere solo di 128 bit perché l'attacco non è solo quello di forza bruta. Nelle chiavi asimmetriche esistono algoritmi di fattorizzazione che consente di risalire dalla chiave pubblica alla chiave privata il cui andamento è sub-esponenziale. In questo caso, il numero di bit per evitare attacchi alle chiavi asimmetriche devono essere almeno di 2000 bit.

<!-- lezione del 07/10/2021-->
## 02.Meccanismi di base

Si è visto come funzionano a livello concettuale le trasformazioni per garantire i requisiti di sicurezza. Adesso si vedono come sono costruite.

### Generatori di numeri casuali (RNG)

I componenti per generare numeri casuali si chiamano RNG.
In generale, per generare una chiave crittografica è importante che un componente RNG abbia due determinate caratteristiche:

- Ogni valore deve essere casuale;
- Ogni valore deve essere indipendente dal punto di vista statistico dal precedente e successivo perché bisogna evitare che un intrusore possa riuscire ad ipotizzare come sono fatti i bit.

### True Random Number Generator (TRNG)

Questi componenti non si possono usare per generare gradi quantità di chiavi crittografiche per due motivi:

- **Bassa frequenza di generazione**: se bisogna generare un numero elevato di chiavi in un tempo brevissimo non sono adatti questi componenti perché usano ad esempio fenomeni fisici per generarli (decadimento radioattivo, rumore termico etc);
- **Non riproducibilità**: mittente e destinazione devono disporre dello stesso segreto per applicare una determinata trasformazione. Se il mittente genera una chiave deve passarla al destinatario altrimenti se il destinatario provasse a generare una chiave non otterrebbe mai la stessa.

### Pseudo Random Number Generator (PRNG)

Per superare i problemi del TRNG, si usano questi altri tipi di generatori. Sono componenti che consentono di generare lunghe sequenze di numeri casuali in modo deterministico a partire da un dato iniziale detto _seme_. Per questo motivo si chiamano _pseudo_ perché se il _seme_ iniziale è uguale sia nella sorgente che nella destinazione, viene riprodotta la stessa sequenza di bit.

![dedurre](./img/img54.png)

Questi componenti non garantiscono la proprietà di _imprevedibilità_ cioè un intrusore che è riuscito ad intercettare l’uscita o ad individuare, in tutto o in parte, lo stato del generatore, riesce a dedurre da quale seme si è partiti o quali saranno i prossimi valori generati.

### Cryptographically Secure PseudoRandom Bit Generator (CSPRBG)

Nella sicurezza informatica, si ha bisogno che si rispetti assolutamente la proprietà dell'_imprevedibilità_.

![dedurre](./img/img28.png)

Questo generatore prevede che il seme sia generato da un _True Number Generator_ una volta sola. A questo punto, il seme viene dato in ingresso ad un PRNG il cui modello è un automa a stati finiti dove la funzione di stato futuro o di uscita deve deve essere unidirezionale in modo da rendere impossibile ad un avversario che ha individuato uno stato di risalire agli stati precedenti ed al seme. Inoltre, il seme deve essere anch'esso imprevedibile e tenuto segreto.

La funzione unidirezionale impiegata può sfruttare algoritmi di crittografia per produrre in uscita questi bit casuali:

- **Crittografia simmetrica**: le proprietà sono solo sperimentalmente verificabili: hanno alta velocità di generazione delle sequenze di uscita;
- **Crittografia asimetrica**: si può dimostrare teoricamente che l'uscita è casuale, imprevedibile e indeducibile ma hanno prestazioni più basse.

### Esempio

Un esempio di PRNG è la classe Secure Random di Java.

### Algoritmi di hash

Gli algoritmi che realizzano la funzione hash devono presentare le seguenti proprietà:

- **Efficienza**: deve essere facile calcolare l'impronta anche se il messaggio in ingresso è molto lungo;
- **Robustezza alle collisioni**: si possono individuare due tipi di robustezza:
  - **Robustezza debole alle collisioni**: per ogni messaggio `m`, è difficile trovare un altro messaggio `m'` tale che `H(m') = H(m)`. Quindi conoscendo l'hash di un messaggio, non si è in grado, con una potenza di calcolo ragionevole, di trovare un altro input che genera lo stesso hash. Da notare che la proprietà suppone che si conosca il messaggio di origine e che questo non deve aiutare nel trovare un secondo messaggio con hash identico;
  - **Robustezza forte alle collisioni**: deve essere difficile trovare una qualsiasi coppia `x` e `y` tale che `H(y) = H(x)`. Non si parte da un messaggio dato, ma si sceglie una qualsiasi coppia di messaggi `m` e `m'` che generano lo stesso hash. Se si riesce, non si viola la resistenza alle collisioni deboli;
- **Unidirezionalità**: data un'impronta deve essere computazionalmente difficile risalire al messaggio originario che l'ha generata.

### Efficienza

Per garantire efficienza, la maggior parte degli algoritmi utilizzano uno _schema di Merkle-Damgard_ o _compressione iterata_.

![dedurre](./img/img14.png)

Consiste nel prendere il messaggio `m` di lunghezza arbitraria e lo si suddivide in blocchi di dimensione prefissata a seconda dello specifico algoritmo di implementazione di `f`. Si applica a `m0` formato da `r` bit (`r>n` dove `n` è l'uscita del blocco) la funzione `f` (che ha le caratteristiche di robustezza debole, forte alle collisioni e unidirezionalità) e un vettore di inizializzazione che avrà un valore iniziale. In uscita, viene prodotta un'impronta `h1`. In pipeline, viene poi elaborato il secondo blocco `m1` concatenato all'impronta generata al passo precedente. L'impronta `h`-iesma è ottenuta applicando una funzione `f` all'impronta ottenuta al passo ottenuto `i-1` con il messaggio `h`-iesmo.
L'impronta finale dell'intero messaggio, corrisponde con l'ultima impronta generata dall'ultimo blocco.

Questo schema è soggetto ad un attacco che si chiama _attacco con estensione_.

![dedurre](./img/img15.png)

Dalla sorgente `A` si invia un messaggio `c` concatenato al suo attestato di autenticità che è costruito con la funzione hash `H(s || m)` dove `s` è il segreto condiviso tra mittente e destinatario. Se la funzione hash è implementata secondo lo _schema di Merkle-Damgard_, allora è presente una vulnerabilità. `H(s || m)` non è altro che l'impronta di uscita dell'ultimo blocco del messaggio `m`. Mettendola come input di un nuovo blocco `f` insieme al messaggio dell'intrusore `m'` suddiviso in blocchi, si riesce a calcolare il nuovo attestato di auntenticità.

Per evitare il problema serve aggiungere all'ultimo blocco delle informazioni aggiuntive, ad esempio, qual è la lunghezza del messaggio. Tuttavia, non è sempre robusto perchè chi riceve il messaggio, deve elaborare queste informazioni aggiuntive.

Oppure, si potrebbe pensare di invertire la posizione di `s` e di `m` all’interno dell’autenticatore, che eviterebbe l’estensione dell’algoritmo. Si capisce la differenza fra schema concettuale, che potrebbero risultare equivalenti, ed implementazioni. Ma questo trucchetto è utile solo se la funzione hash non è resistente alla collisione debole. Infatti, supponiamo che un intrusore possa trovare un messaggio `m'` in collisione con `m`. Con questa ipotesi si avrebbe `H(m || s) = H(m' || s)`. Dunque, all’intrusore sarebbe sufficiente inviare sul canale il messaggio `m'` concatenato con `H(m || s)` che, per la collisione, autenticherebbe `m'`.

### Robustezza alle collisioni

Le funzioni hash non garantiscono sempre la resistenza alle collisioni. Non ci si limita, quindi, a eseguire solo una volta l'operazione di hash ma la si effettua più volte. Ad esempio, HMAC è uno standard a due compressioni cioè si effettua l'impronta di un'impronta.

La resistenza alle collisione è fondamentale quando la funzione hash è usata per costruire attestati di autenticità. Ad esempio, in uno schema di firma digitale perchè l'intrusore potrebbe trovare una coppia di messaggi che producono la stessa impronta. L'intrusore potrà eludere le vittime facendo firmare un contratto su un messaggio `m` a loro favorevoli, per poi in futuro usare l’attestato di autenticità su un messaggio `m'` (favorevole ora all’intrusore), dato che c’è collisione. In questo esempio, non è rispettata la collisione forte.

### Complessità del calcolo di una collisione

**Ipotesi**: per la proprietà di oracolo casuale, le funzioni hash devono avere un comportamento aleatorio cioè devono restituire con uguale probabilità una delle 2^n configurazioni.

**Problema**: data una funzione hash con `n` possibili output e un determinato `H(x)`, se `H` viene applicato a `K` input casuali, quale deve essere il valore di `k` tale che la probabilità che almeno un input `y` soddisfi `H(y) = H(x)` sia maggiore di 0.5?

- **Resistenza debole**: si indica con $ P_1(2^{n}, 1) = \frac{1}{2^n} $ la probabilità di un tentativo di trovare una collisione. La probabilità di insuccesso, quindi, è 1 - 1/2^n. Se si hanno k tentativi, P_k(2^n, k) = 1 - (1 - 1/2^n)^k. Questo vuol dire che k= P_k(2^n, k) * 2^n. 2^n per avere un andamento esponenziale deve essere almeno 128. Dunque, l'impronta deve essere almeno 128 bit;
- **Resistenza forte (paradosso del compleanno)**: nell’ipotesi che le date di nascita siano equiprobabili, è sufficiente scegliere a caso 253 persone per avere una probabilità > 0,5 che una di queste compia gli anni in un dato giorno. Sono invece sufficienti 23 persone scelte a caso per avere una probabilità > 0,5 che due o più compiano gli anni nello stesso giorno. Quindi, non bastano 128 bit. Il numero di bit deve essere il doppio perché per la resistenza forte sono necessari 2^(n/2) tentativi. Dunque, è più facile effettuare un attacco rispetto alla resistenza debole.

### Unidirezionalità

L'unidirezionalità è un'altra proprietà importante. Un caso tipico in cui `H` deve essere one-way si ha quando un messaggio in chiaro `m` è autenticato da `H(m || s)` altrimenti invertendo la funzione si risalirebbe al segreto.

## 03.Meccanismi Simmetrici

### Cifrario simmetrico

Nella crittografia classica, è stato individuato un cifrario perfetto chiamato _One-time pad_. Il cifrario perfetto è per definizione un algoritmo in grado di occultare il testo in chiaro escludendo ogni tipo di attacco, ne segue che un testo cifrato con un cifrario perfetto non può essere letto in nessun modo se non si è in possesso della chiave di cifratura unica per decifrarlo. Tuttavia, il suo impiego nella pratica è molto complicato.

Per questo motivo si parla di _cifrario computazionalmente sicuro_ cioè per risalre dal testo cifrato al testo in chiaro corrispondente si ha bisogno di una potenza di elaborazione superiore a quella a disposizione dell'intrusore.

Per la _teoria dell'informazione_ sviluppata da Shannon, il cifrario è computazionalmente sicuro se adotta i criteri di:

- **Confusione**: il cifrato deve essere aleatorio e l'aleatorietà non permette di individuare delle relazioni tra testo cifrato e la chiave usata;
- **Diffusione**: la modifica di un solo carattere del messaggio in chiaro deve provocare una modifica sostanziale del messaggio criptato in modo da non poter usare attacchi con statistica.

Ci sono due tecniche che garantiscono _confusione_ e _diffusione_:
- **Tecnica di sostituzione**: tecnica che garantisce la confusione;
- **Tecnica di trasposizione**: tecnica che garantisce la diffusione.

Dalla _teoria dell'informazione_ di Shannon discende che un _cifrario simmerico_ è computazionalmente sicuro se usa _diffusione_ e _sostituzione_.

I cifrari simmetrici vengono utilizzati per garantire riservatezza. In rarissimi casi, viene usato per garantire autenticazione, per generatori di numeri pseudo-casuali crittograficamente sicuri e per alcuni protocolli di identificazione.

Esistono come cifrari simmetrici due famiglie distinte:

- **Cifrario a flusso**: si ispira al cifrario _One-time pad_. È un cifrario che opera su uno o pochi bit alla volta con una regola variabile al progredire del testo. Garantisce la  protezione dei singoli bit di una trasmissione seriale. Ad esempio, nel settore della telefonia, applicazione web etc;
- **Cifrario a blocchi**: si ispira al _Cifrario poligrafico_ ed al _Cifrario composto_. Trasforma con una regola fissa blocchi di messaggio formati da molti bit. La lunghezza del blocco dipende dallo specifico algoritmo. Ad esempio, protezione di pacchetti, di file, posta elettronica etc.

Un _cifrario a flusso_, è più veloce di un _cifrario a blocchi_ perché non introduce rallentamenti. Se il _cifrario a flusso_ non è impiegato correttamente, è meno sicuro di un cifrario a blocchi non impiegato correttamente.

### Cifrario a flusso

Encryption `E` e decryption `D` sono implementati con degli `XOR`:

![dedurre](./img/img34.png)

- **Encryption**: viene preso il bit `i`-esimo di testo in chiaro `m`, lo si mette in `XOR` (somma modulo 2) con il bit `i`-esmo della chiave `k`;
- **Decryption**: al bit `i`-esimo del messaggio cifrato `c`, si mette in `XOR` lo stesso `i`-esmo bit di chiave `k` usato nella fase di cifratura.

Per questo motivo ci deve essere _sincronismo_ tra i flussi di chiave della sorgente e della chiave.

Il testo cifrato `c` sarà sicuramente più lungo di 128 bit per cui non ha senso usare l'attacco di forza bruta perché in questi tipi di cifrari, la chiave è lunga quanto il testo. Inoltre, la chiave varia da messaggio a messaggio.

I cifrari a flusso si suddividono in:

- **Cifrario a flusso sincrono**: il flusso di chiave dipende solo dal seme;

  ![dedurre](./img/img43.png)

- **Cifrario a flusso autosincronizzante**: il flusso di chiave dipende dal seme ma anche dai bit di testo cifrato precedenti.

  ![dedurre](./img/img42.png)

I più usati sono quelli a _cifrario flusso sincrono_ perché i componenti a _cifrario a flusso autosincronizzante_ sono più costosi.

### Esempio

Uno degli algoritmi più famosi è RC4 ma ormai è stato disabilitato nei browser a causa delle sue vulnerabilità.
Al giorno d'oggi vengono usati algoritmi come Salsa e Sosemanuk.

### Possibili vulnerabilità

Per garantire la _riservatezza_, i cifrari a flusso devono avere certe proprietà e bisogna capire quali sono le loro vulnerabilità:
- Attacchi attivi;
- Uso della chiave una sola volta;
- Malleabilità.

### Attacchi attivi

Nel _cifrato a flusso sincrono_, nel caso di attacchi attivi:

- **Se si modifica un bit del cifrato**: la destinazione non decifra correttamente un bit perché è stato cambiato. Si dice che non si ha perdita di sincronismo perché solo il `i`-esimo è è stato cambiato. Tuttavia, la decifrazione non è corretta;
- **Se si cancella/inserisce un bit**: dal punto in poi in cui è stato cancellato il bit, i restanti non corrisponderanno mai a quelli inviati. Si dice che si ha perdita di sincronismo perché tutti i bit sono da buttare via.

Nel _cifrato a flusso autosincronizzante_, nel caso di attacchi attivi:

- **Se modifica, cancella o elimina un bit del cifrato**: si ha una perdita di sincronismo ma non permanete, solo di un transitorio. Il transitorio è legato alla dimensione del registro di scorrimento (SHIFT) perché dipende da quanti cicli, il bit modificato/cancellato/inserito rimane dentro a questo registro.

### Uso della chiave una sola volta

Il requisito fondamentale è che la chiave deve essere usata una e una sola volta. Se si usa lo stesso flusso di chiave su messaggi distinti si possono fare attacchi di analisi sui cifrati perché si sfruttano le proprietà dell'`XOR`.

![marco togni](./img/img41.png)

Ad esempio, si consideri:\
`m1 XOR k = c1`

`m2 XOR k = c2`

Fare `c1 XOR c2` è come fare l'`XOR` su due messaggi in chiaro: `m1 XOR m2`.

### Esempio

Nell'implementazione del protocollo WEB si presenta questo tipo di vulnerabilità.

![marco togni](./img/img17.png)

L'obiettivo è ottenere un _seed_ variabile ma in realtà questo protocollo presenta alcuni limiti:

- Il vettore di inizializzazione ha una dimensione limitata (24 bit). Dopo 2^{24} generazioni si ha che il seed si ripete;
- Quando si spegneva, il vettore si inizializzava a zero e poi funzionava ad incremento. Il comportamente è molto prevedibile.

<!-- 11/10/2021 -->
### Malleabilità

La proprietà di _malleabilità_ consiste nella possibilità di alterare il cifrato in modo da produrre un effetto desiderato sul testo in chiaro originario. L'attacco ha successo se e solo se l'intrusore conosce una parte del messaggio `m` che il mittente deve inviare.

Il mittente effettua `m XOR k`, l'attaccante prende `(m XOR k) XOR p` dove `p` è scelto da lui e sostituisce il messaggio sul canale con il nuovo messaggio cifrato modificato. La destinazione, decifra `((m XOR k) XOR p)) XOR k` e quindi non sarebbe altro che fare `m XOR p`.

Fare le tabelle di verità per credere!

![marco togni](./img/img25.png)

Ad esempio, il mittente sta cifrando dei dati strutturati. All'inizio di questi dati, c'è sempre la parola "From". L'attaccante, conosce che il flusso è strutturato. Il suo obiettivo è quello di cambiare la provenienza del messaggio `m`. Si ipotizzi che l'inizio del messaggio sia "From Dario" con rappresentazione esadecimale "44 61 72 69 6F". L'obiettivo dell'intrusore è ottenere "From Lucia" con rappresentazione esadecimale "4C 75 63 69 61". Bisogna trovare quel `p` tale per cui `m XOR p = Lucia`. Dunque, `p` deve essere "08 14 11 00 0E".

### Cifrari a blocchi

### Electronic Code Book (ECB)

Si prende un messaggio e lo si suddivide in blocchi di uguale lunghezza prefissata. Se l'ultimo blocco contiene meno bit della lunghezza che dovrebbe avere lo si completa con dei bit di padding.

![marco togni](./img/img35.png)

Ogni blocco viene dato in input alla funzione di encryption `E` tramite una chiave fissa condivisa dalle due parti. Il testo cifrato, quindi, non è altro che la concatenazione dei cifrati ottenuti dai singoli blocchi.

L'operazione di cifrare a blocchi ricorda molto la tecnica di base della sostituzione monoalfabetica della crittografia classica ma a differenza di quest'ultima, la grossa dimensione dei blocchi la rende immune da un attacco con statistiche.

La chiave deve essere modificata frequentemente perché essa cifra moltissimi blocchi di testo in chiaro e quindi ci sono più possibilità di individuarla. Dunque, l'attacco con forza bruta è possibile ed è necessario dimensionare la chiave almeno con 128 bit.

Vantaggi:

- **Alto parallelismo**: se si dispone di più CPU, l'esecuzione è parallela;
- **No propagazione dell'errore**: se l'intrusore modifica a caso un bit, si dice che la propagazione dell'errore rimane confinata a quel blocco. Chi decifra avrà solo un blocco _sbagliato_.

Svantaggi:

- **Determinismo**: a blocchi in chiaro identici corrispondono blocchi cifrati assolutamente identici. Sono informazioni in più che un intrusore può sfruttare a suo favore;
- **Maleabilità**: un intrusore è in grado di modificare il testo cifrato in modo tale che la destinazione quando lo decifra ottiene un testo da lui scelto. Ad esempio, si consideri una transazione bancaria. Nel primo blocco si ha il mittente, nel secondo il destinatario e nel terzo la cifra da trasferire. L'intrusore, sostituisce al blocco del destinatario, il suo. Se il mittente è "Luca", il destinatario è "Lucia" e la somma da trasferire "100", l'attaccante basta che sostituisca "Lucia" con il suo nome.

Questa modalità si usa solo in casi specifici: ad esempio, cifrare delle informazioni che sono già per natura aleatoria (per evitare determinismo) o un testo che risiede interamente in un solo blocco (per evitare la possibile sostituzione di blocchi). Ad esempio, si usa per cifrare una chiave di sessione.

### Esempio

Esistono tanti algoritmi di cifratura per i cifrari a blocchi (DES, TDES, AES). Oggi lo standard è AES.

### Modalità di cifratura

L'obiettivo, quindi, è quello di trovare modalità di _cifrature aleatorie_. Esistono le modalità CBC, CFB, OFB, CTR.

### Cipher Block Chaining (CBC)

Solo questa modalità di cifratura utilizza il padding.

![marco togni](./img/img18.png)

La modalità CBC prende il messaggio in chiaro, lo suddivide in blocchi e l'ultimo blocco è sottoposto a padding se necessario. Per ogni blocco, il testo in chiaro viene messo in `XOR` con il cifrato del blocco precedente e il risultato viene messo in input alla funzione di cifratura `E` ottenendo un testo cifrato c_i. Solo per quanto riguarda il blocco 1, il testo in chiaro viene dato in `XOR` con quello che si chiama _vettore di inizializzazione_ (IV) altrimenti questo blocco sarebbe sempre deterministico. IV può essere o concordato o inviato come primo blocco del cifrato e la sua dimensione è grande quanto quella del blocco.

In fase di decifrazione, le operazioni sono inverse ed è sufficiente invertire il verso delle frecce. Se si perde IV dopo aver cifrato il messaggio, si riesce comunque a decifrare tutto lato destinazione tranne il primo blocco.

Per ottenere aleatorietà, questo vettore deve essere:

- **(pseudo)casuale**;
- **Imprevedibile** anche se si genera un numero randomico ma si conosce il seed si può prevedere che numero verrà dopo. È importante questo punto altrimenti viola confidenzialità;
- **Non ripetibile**: se si ripete il vettore e si hanno due messaggi uguali, si ottiene lo stesso cifrato.

Il vettore non deve essere necessariamente segreto che non è un requisito fondamentale cifrare IV per garantire la riservatezza. L'intrusore non conosce la chiave `k`.

In generale la dimensione del cifrato è maggiore del testo in chiaro. Se il messaggio è di `N` bit il cifrato sarà `N` bit + IV + padding.

Vantaggi:

- Un cambiamento in un singolo blocco ha effetto su tutti i blocchi cifrati seguenti.

Svantaggi:

- In questo caso, non si può procedere in modo parallelo con più CPU perché è necessario il cifrato del passo precedente in fase di cifrazione. Invece, il parallelismo lo si ottiene in fase di decifrazione se si hanno già tutti i pezzi di cifrato;
- Se un attaccante, modifica un qualcunque bit di un blocco, l'errore si propaga nei blocchi successivi.

### Chipher Feedback Block (CFB)

Questo schema ricorda un _cifrario a flusso autosincronizzante_. 

![marco togni](./img/img44.png)

Nel dettaglio, può essere rappresentato nel seguente modo:

![marco togni](./img/img19.png)

Si prende un registro a scorrimento che viene inizializzato con un vettore di inizializzazione che è casuale, non necessariamente segreto, imprevedibile e usato una sola volta. Il registro è formato da due parti: una parte formata dagli s bit meno significativi e l'altra dai b-s bit più significativi. A scorrimento vuol dire che ad ogni clock s bit "escono" dal registro. Lo stato del registro a scorrimento viene sottoposto ad una cifratura con la chiave `K`. L'uscita va a finire in un altro registro a scorrimento che è formato da s bit più significativi e b-s bit meno significativi. Il cifrato finale è ottenuto mettendo in `XOR` s bit del testo in chiaro con gli s bit più significati del vettore a scorrimento di cifratura. Il risultato è il cifrato costituito da s bit.

![marco togni](./img/img20.png)

In decifrazione, si procede analogamente. Per decifrare il primo blocco di testo in chiaro bisogna avere il cifrato ottenuto al passo precedente vuol dire scorrere indietro. La prima cosa da fare è partire dall'ultimo blocco e recuperare a ritroso. Inoltre, si usa sempre la stessa funzione `E` cioè l'implementazione dell'algoritmo è la stessa (quindi stesso circuito hardware).

Si ha la propagazione dell’errore (una modifica su un cifrato si propaga sul successivo), ma si esaurisce dopo un certo lasso di tempo (si vedano cifrari a flusso auto-sincronizzante).

Si usa, ad esempio, quando si ha una trasmissione carattere per carattere (8 bit alla volta).

### Output Feedback (OFB)

Questo schema ricorda un _cifrario a flusso sincrono_.

![marco togni](./img/img45.png)

Nel dettaglio, può essere rappresentato nel seguente modo:

![marco togni](./img/img21.png)

Come in CFB, anche in questo caso IV serve per inizializzare il registro. Il procedimento iniziale è identico, tranne per l’ultimo passaggio: C1 viene infatti prodotto allo stesso modo, ma non viene mandato in ingresso al registro, al passo successivo.

![marco togni](./img/img22.png)

In decifrazione, non si usa la funzione inversa ma si continua ad usare la funzione di encryption `E` (stesso circuito hardware).

Il vettore non deve essere necessariamente segreto. Sicuramente aumenta la robustezza ma non è un requisito necessario. Inoltre, il vettore non deve essere necessariamente imprevedibile ma unico perché si ha un problema di confidenzialità se la chiave è usata più volte.

L'OFB si preferisce usarlo quando i canali sono rumorosi (ad esempio i satelliti) perché la modifica di un blocco cifrato non si propaga sul blocco successivo.

### Counter (CTR)

Il comportamento è quello di un cifrario a flusso sincrono.

![marco togni](./img/img29.png)

Funziona esattamente come una modalità ECB: il testo in chiaro viene suddiviso in blocchi, ciascuno dei quali viene lavorato indipendentemente dagli altri. Il flusso di chiave di L bit casuali, dove L è la lunghezza del blocco, è sommato modulo 2 con un pari numero di bit del testo in chiaro. Tali bit sono ottenuti cifrando lo stato di un contatore a L bit, incrementato di un’unità prima di procedere all’elaborazione di un nuovo blocco, con la chiave k.

L’i-esimo bit di chiave non dipende né dal messaggio né dagli altri bit di chiave, bensì solo dal seed iniziale. Infatti, viene fornito come input della funzione Ek il seed iniziale e i suoi N incrementi unitari, dove N è il numero di blocchi da cifrare.

I blocchi possono lavorare in parallelo sia in fase di `E` che di `D`.

Si utilizza la sola funzione di cifratura Ek sia per cifrare che per decifrare.

Questo schema viene usato, ad esempio, su reti ATM.

### Beast Attack (Browser Exploit Against SSL/TLS)

In questo esempio la modalità CBC non è usata correttamente.

Se la versione di TLS è la 1.0 si rischia di subire questo attacco però è bene ricordare che l'attacco è molto difficile da realizzare.
L'intrusore deve riuscire ad entrare in una sessione già avviata tra client e server e alterare il normale flusso dei dati (attacco _Man In The Middle_). Secondo la classificazione degli attacchi, questo fa parte della categoria _attacco con testo in chiaro scelto_.

All'inizio di una connessione TCP, il client e il server negoziano gli algoritmi di cifratura, la chiave della sessione e i parametri che vengono usati dai cifrari come il vettore di inizializzazione e anche la modalità di cifratura da usare. I dati a livello applicativo hanno una certa dimensione e vengono suddivisi in blocchi perché vanno a finire in pacchetti SSL il cui payload è di dimensione inferiore.

![marco togni](./img/img24.png)

Se il vettore di inizializzazione non è imprevedibile si incorre a questo tipo di attacco.

Si suppone che ci siano due persone che stanno parlando tra di loro: Luca e Lucia.

Luca inizia sempre la conversazione con "Mia amata Lucia". Si suppone che "Mia amata" finisca in un blocco e "Lucia" in un altro. Le operazioni sono le seguenti:

- "Mia amata" `XOR` con il vettore di inizializzazione casuale, imprevedibile e usato una e una sola volta, producendo un cifrato;
- "Lucia" `XOR` con il cifrato del passo precedente producendo un nuovo cifrato.

L'obiettivo dell'intrusore è cercare di capire se dando un input opportuno, si ha lo stesso output del blocco 2 così da poter confrontare e dedurre che "Lucia" è stato l'input del passaggio 2.

![marco togni](./img/img30.png)

Basta conoscere come si comporta l’`XOR`, cioè se si da due volte lo stesso input, è come se annullasse l’`XOR`.

Si indica con:

- `K1` il nuovo vettore di inizializzazione che ovviamente sarà diverso rispetto a quello del passaggio 2;
- `K` è il residuo che è stato usato nel passaggio 2.

Bisogna eliminare l'effetto `K1` perché è quello che SSL userebbe come input e vedere se si produce lo stesso cifrato. Avendo ipotizzato, per semplicità, che il vettore di inizializzazione è prevedibile, è possibile costruire un messaggio che abbia la forma:

`Lucia XOR K1 XOR K XOR K1`

`Lucia XOR K`

### Dimensione del blocco

Non solo la dimensione della chiave è importante ma anche la dimensione del blocco perché definisce quanti sono i dati possono essere cifrati con la stessa chiave. La cifratura deve essere robusta fino a 2^n input diversi.
Purtroppo molte modalità di cifratura diventano insicure dopo 2^n/2 cifrature a causa dell’aumento di probabilità di collisioni tra due blocchi di cifrato per il paradosso del compleanno.
Con 64 bit c'è questa problematica.

La modalità CBC è usata ma nonostante ciò si va contro a questo attacco: se ci sono due testi uguali cifrati in modalità CBC vuol dire che se si mettono ogni bit in XOR dei due cifrati, si ottiene l'XOR dei due messaggi in chiaro. Si guardi paragrafo precedente sulla malleabilità.

### Gestione della chiave

Quando si usano cifrari simmetrici, l'algoritmo deve essere robusto, la chiave deve essere generata, memorizzata e dimensionata in maniera opportuna e devono essere impiegate modalità di cifratura corrette. Se tutto questo è vero resta un problema: la chiave deve essere distribuita in modo sicuro.

Ci sono due famiglie:

- **Con precedente KA (key agremeent)**: modello che prevede un accordo fuori banda con canale dedicato;
- **Senza precedente KA (key agremeent)**: modello che prevede che non ci sia scambiato niente in precedenza.

### Con precedente KA (key agremeent)

Questo schema prevede che fuori banda e in maniera **assolutamente** robusta sia stata precondivisa una _master key_. Non è opportuno che `A` cifri molti dati con questa _master key_ perché questa chiave meno si cambia meglio è, dato che poi bisogna creare un canale fuori banda (costo elevato). La master key quindi deve avere una vita lunga e ogni tanta va rinnovata.

![marco togni](./img/img31.png)

 All’avvio della sessione, il mittente genera una chiave di sessione `k` tramite PNRG crittograficamente sicuro. Questa chiave `k` viene cifrata con la _master key_. Poi, il mittente cifra anche il messaggio con la chiave `k` e il relativo cifrato viene mandato al destinatario concatenato al cifrato della chiave `k`. Il destinatario, conoscendo la master key, decifra la chiave `k`, che userà per decifrare a sua volta il messaggio `m`. La chiave di sessione viene usata solo una volta.

Uno svantaggio di questo schema è che non è scalabile: quando il numero di utenti diventa alto il numero di scambi della _master key_ diventa improponibile.

<!-- 14-10-2021 -->
### Key Distribution Center (KDC)

È impossibile che ogni utente stabilisca una chiave segreta con ognuno degli altri utenti. Si ipotizzi una comunità formata da `Nu`, ogni utente deve:

- Fare `Nu - 1` incontri diretti;
- Memorizzare `Nu - 1` chiavi segrete;
- Aggiornarsi ogni volta che nella comunità si aggiunge un nuovo utente.

Occorrono dunque: Nc = Nu * (Nu-1)/2 canali _sicuri_; altrettante sono le chiavi segrete in circolazione. Per ridurre, quindi, il numero di chiavi pre-concordate si introduce una terza entità chiamata _centro di distribuzione delle chiavi_.

![marco togni](./img/img32.png)

L'idea è quella che `A` chiede a `T` una chiave di sessione `k`, `T` la genera e la passa ad `A` e poi `A` la invia a `B`. Ogni utente deve precedentemente pre-condividere con `T` una chiave simmetrica unica (KAT, KBT). Tutto in maniera assolutamente sicura.

![marco togni](./img/img55.png)

Il mittente `A` ha pre-condiviso con il centro di distribuzione la _master key_ `KA` mentre `B` ha condiviso la _master key_ `KB`.

- `A` deve comunicare a `T` che ha bisogno di una chiave. Invia un messaggio specificando chi è il mittente, con chi vuole comunicare e un numero random imprevedibile e unico ad ogni sessione R_a che ha lo scopo di _sfida_ per vedere se `T` è davvero il centro di distribuzione;
- `T` riceve il messaggio e risponde inviando a sua volta un messaggio. Questo messaggio non è altro che la concatenazione di Ra, il destinatario `B`, la chiave di sessione `k` e la chiave di sessione `k` concatenata con `A` cifrata con dalla master key di `B`. Per cifrare il messaggio si usa la chiave KA in modo tale che si dimostra che `T` sia a conoscenza della chiave;
- `A` riceve il messaggio e decifra EKA ottenendo Ra (sa che è davvero `T` con cui sta comunicando), il destinatario `B`, la chiave di sessione `k` e EKB(A || k). È ovvio che `A` non sappia decifrarlo ma lo deve inviare a `B`.

![marco togni](./img/img33.png)

Da un punto di vista della robustezza, il protocollo con soli tre passaggi non è sicuro da un punto di vista concettuale. Un attaccante può:

- **Modificare a caso un bit del messaggio sul canale**: si invalida solo la sessione perché il messaggio è aleatorio;
- **Effettuare un attacco con replica**: replica significa inoltrare lo stesso messaggio:

  - **punto 1** (non può avvenire l'attacco): Ra l'intrusore non può replicarlo perché è sempre diverso e anche se fosse servirebbe a poco. T non controlla che Ra è sempre diverso ma genera una chiave di sessione ogni volta diversa e quindi l'intrusore non può decifrarla;
  - **punto 3**: un intrusore che è riuscito ad intercettare il messaggio 3 E(A||k), può ripresentarlo a B iniziando praticamente il protocollo dal passo 3 e forzando B a mandare (quante volte volesse) campioni di messaggio cifrato. Per questo motivo il protocollo non può essere costituito solo da 3 passi ma si devono aggiungere altri passi:
    - `B` invia un messaggio per indicare che la chiave `k` è stata ricevuta davvero. Solo `B` è in grado di decifrare e risalire a `k` e per questo motivo si è sicuri che sia stato B a generarlo. Dentro questo messaggio c'è un numero random Rb;
    - `A` decifra il messaggio appena ricevuto, e spedisce il messaggio cifrato con all'interno Rb - 1 in modo che `B` sia sicuro che sia `A` il mittente.

Possibili soluzioni:

- `B` quando riceve il messaggio 3, preleva `k` e verifica se il messaggio è stato già inviato o no da parte di `A` (MA questo schema non lo prevede);
- Per evitare che l'intrusore conosca qualcosa sulla chiave o la chiave stessa, si limita la validità temporale.

In generale, i problemi del protocollo sono i seguenti:

- Collo di bottiglia (n° max di utenti);
- Overhed di comunicazione perché è installata una terza entità;
- Gestire la memoria in modo sicuro;
- Rendere il servizio sempre disponibile (online);
- Scalabile;
- Ente degno di fiducia.

### Esempio

Molti sono i progetti che lo hanno assunto come riferimento: il prototipo KryptoKnight, il servizio di autenticazione Kerberos realizzato dal MIT, lo standard DCE per ambienti distribuiti e Active Directory di Windows 2000.

### Implementazione Key Distribution Center (KDC)

A livello implementativo possono esserci delle vulnerabilità che a livello concettuale non ci sono:

- **ECB**: si sfrutta il determinismo e la malleabilità di questa modalità:

  - L'intrusore si mette in ascolto sul canale perché vuole avviare la comunicazione dei passi 3, 4 e 5 come se fosse la sorgente `A` leggittima;
  - Da una sessione precedente di `A`, l'intrusore intercetta il messaggio del passo 3 di `A`. Da questo messaggio si conserva Ekb(A). Il messaggio Ekb(A || k) può essere riscritto come Ekb(A) || Ekb(k);
  - `A` deve riaprire una nuova sessione con B altrimenti questo attacco non avrebbe senso;
  - A questo punto, l'intrusore avvia una sua comunicazione con `T` in modo da ottenere una sua chiave `k1`. Si conserva Ekb(k1);
  - L'intrusore nella sua comunicazione aperta, al passo 3 e al posto di inviare il messaggio Ekb(C || k1) -> Ekb(C) || Ekb(k) lo sostituisce. Ha il blocco Ekb(A) perché lo ha conservato da una sessione passata e lo concatena con Ekb(k1);
  - al passo 4, `B` risponde al messaggio pensando che sia `A`. Le sessioni aperte sono due: A - B e C (ma in realtà diventa A) - B;
  - al passo 5, dato che l'intrusore conosce k1 riesce a decifrare il messaggio.

  È difficile effettuare una session injection cioè l'attaccante si intromette nella sessione e modifica/crea i messaggi. Per questo l'intrusore deve creare una nuova comunicazione.
- **CBC**: da fare a casa
- **CFB**: da fare a casa
- **OFB**: da fare a casa
- **CTR**: da fare a casa

<!-- 18/10/2021 -->
### Key Distribution Center (KDC) - Alternativo

Il mittente `A` ha pre-condiviso con il centro di distribuzione la _master key_ `KA` mentre `B` ha condiviso la _master key_ `KB`.

![marco togni](./img/img56.png)

- `A` contatta `B` invia un messaggio contenente chi è il mittente || la master key di `A` costruita sul numero randomico imprevedibile e unico RA;
- `B` contatta `T` inviando il messaggio che ha ricevuto da parte di `A` || chi è il mittente || la prova EKB(RB);
- `T` genera la chiave `k` e la restituisce a `B` il messaggio EKB(K, A, RB) || EKA(K, B, RA);
- `B` invia ad `A`, la seconda parte del messaggio: EKA(K, B, RA)

Da un punto di vista della robustezza, il protocollo è sicuro da un punto di vista concettuale: un intrusore anche se intercettasse il messaggio 1, il protocollo si riavvierebbe dato che al passo 2 si genera sempre una nuova chiave K.

Presupponendo poi, per assurdo, che l’intrusore riuscisse davvero a conoscere k, non può impersonare A o B, perché rispetto a prima non ci sono mai comunicazioni cifrate con K ma solo con KA e KB. Ovviamente, se nelle comunicazioni future si riusa k, l'intrusore potrebbe usarla per decifrare i messaggi.

### Implementazione Key Distribution Center (KDC) - Alternativo

Per casa.

### Key Distribution Center (KDC) vs Key Distribution Center (KDC) - Alternativo

- Da un punto di vista di overhead: nel secondo protocollo, B potrebbe costituire un collo di bottiglia se contattato da più mittenti perchè la comunicazione avviene direttamente con B.
- Carico computazionale: l'entità A rispetto al protocollo 1 è sovracarricata in meno.

### Integrità e confidenzialità

L'attaccante può effettuare attacchi attivi. L'obiettivo è vedere se violando l'integrità si riesce a risalire al testo in chiaro cioè se si viola anche la proprietà di riservatezza.

### Senza precedente KA (key agremeent)

Un modello che non prevede distribuzione a priopri di chiavi prende il nome di Diffie-Hellman. L’accordo sulla chiave di sessione deve, quindi, poter essere preso in assenza di ogni altro precedente accordo e l’unico modo per prenderlo è di farlo tramite il canale insicuro.

Lo scambio detto DH (dai loro cognomi) si basa sul teorema dei logaritmi discreti. Si definisce:

- `p` un numero primo grande cioè è un numero formato da almeno 360 cifre decimali;
- `g` che è un altro numero, è detto generatore di `p` se le potenze modulo `p` generano tutti interi compresi tra 1 e p-1. Se `g` è il generatore allora g mod p, g^2 mod p, ..., g^p mod p sono tutti numeri distinti e compresi da valori compresi tra 1 e p-1.

Il teorema enuncia che per un qualsiasi intero b e un generatore g di p, si può trovare un esponente univoco i tale che b=g^i(mod p) dove 0 <= i <= (p-1) e i è chiamato _logaritmo discreto_ di b per la base g, modulo p.

L’obiettivo dello scambio DH è far sì che due utenti qualsiasi A e B, senza aver preso alcun precedente
accordo segreto, riescano a condividere un dato segreto K dopo aver calcolato ed essersi scambiati senza nessuna segretezza due dati YA e YB. A tal fine è necessario che ciascuno dei due utenti scelga a caso un numero X compreso fra 1 e (p-1), tenendoli segreti.

Il numero primo p e g sono noti (magari accordati inizialmente tra le due parti).

### Esempio

Si suppone che si stia usando un protocollo TCP. La macchina sorgente ha cifrato dei dati, vengono inviati usando il protocollo IPsec e ricevuti dalla macchina gateway che è in ascolto sulla porta 80. L'intrusore è in ascolto sulla porta 25 sul gateway.

![marco togni](./img/img36.png)

L'obiettivo è quello di non smistare i dati sulla porta 80 ma sulla porta 25. Quando i dati vengono decifrati, il vettore di inizializzazione viene messo in XOR con il primo blocco di messaggi cifrati. L'intrusore basta che modifichi il vettore di inizializzazione originario in un vettore che mandato in XOR con il blocco di cifrato restituisca 25 al posto di 80. Il vettore di inizializzazione viene cambiato in IV' XOR 80 XOR 25.

Se si vuole richiedere solo integrità si usa MAC (Message Autenthication Code).
Se il messaggio richiede integrità ma non confidenzialità bisogna usare un cifrario simmetrico nella modalità _authenticated encryption_.

### Autenticazione di m con E(m)?

Un cifrario simmetrico, si può usare la cifratura come meccanismo di autenticazione dell'origine di un messaggio?

Decifrando un messaggio con una chiave, si può confidare dal vero mittente con cui si condivide questa chiave? Questo è vero solo in scenari favorevoli:
- Il testo deve essere dotato di significato: basta che una modifica di pochi bit alteri completamente il significato del messaggio (non sempre così)
- Un intrusore non può effettuare attacchi attivi: quindi non modificando il testo, solo chi ha mandato il testo è davvero lui la sorgente leggittima

Si riprende lo schema come garantire integrità e autenticità: - HMAC (funzioni hash crittograficamente sicure). Sottopone a due compressioni per ridurre l'attacco con estensione, il messaggio concatenato con il segreto
- MAC (Message Autenthication Code)

Un primo modo per costruire raw CBC-MAC che sfrutti un cifrario simmetrico in modalità CBC:

![marco togni](./img/img37.png)

Si prende il messaggio originario, lo si suddivide in blocchi. Ogni blocco viene dato in XOR al cifrato precedente dove al primo passo, il blocco viene messo in XOR con un vettore di inizializzazione (0). Ai fini della confidenzialità non importa avere un vettore imprevedibile, assolutamente casuale e usato una sola volta. L'uscita dell'ultimo blocco non è altro che l'attestato di autenticità e integrità. Questa modalità diventa deterministica appunto perché il vettore è 0.

![marco togni](./img/img38.png)

Questa implementazione non è corretta. Quello che si usa è encrypted CBC-MAC. Questa modalità prende l'ultimo blocco cifrato che viene sottoposto ad un'ulteriore operazione di cifratura però con una chiave diversa.

Si suppone di avere adottato una modalità di cifratura raw CBC-MAC. Uno schema a cascata introduce sempre un problema a cascata con estensione. Se il messaggio è lungo un blocco il raw CBC-MAC si può usare. Il problema è che i messaggi sono di lunghezza arbitraria (da più blocchi). L'intrusore può:
- Scegliere un messaggio di 1 blocco arbitrario m
- La sorgente legittima crea il tag t su m E(k, m)
- Usare t come tag su un messaggio di due blocchi fatto così: (m, t EXOR m)

E(m, t XOR m) -> E(k, E(k, m) XOR t XOR m) -> E(k, t XOR t XOR m) -> E(k, m) -> t

L'intrusore è in grado di proporre un attestato di autenticità valido su due blocchi. Se non c'è un controllo sulla lunghezza del messaggio, l'intrusore è in grado di fare un attacco con estensione.

Per rendere il MAC  robusto è necessario inserire un padding. Le possibili soluzioni sono:
- Fare un padding con tutti zeri: il problema è:
m | 0000 se si calcola m su E su questo messaggio si ottiene un tag t
m 00 | 00 se si calcola m su E su questo messaggio si ottiene un tag t1
t = t1. Se il trasferimento sono 100 dollari è come fare 10000
- Standard ISO: mettere 1 che indica l'inizio del padding con tanti zeri. Bisogna ricordarsi di mettere anche altri pad "100...00".
CMAC: le API devono essere già corrette senza che il programmatore si ricordi di inserire il padding nel modo corretto.

### authenticated encryption

Garantisce confidenzialità contro un avversario che effettua un attacco attivo capace di decifrare alcuni testi cifrati (previene attacchi con testi cifrati scelti)

Problemi:
- Non previene attacchi di replay: si possono riproporre messaggi come se provenissero dalla stessa sorgente
- Non contrasta attacchi side channels (timing): <!--impedisce di modificare il cifrato in maniera di risalire al testo in chiaro: def del secondo punto?-->

Authenticated Encryption (AE) è un concetto introdotto nel 2000. Prima Il programmatore aveva il compito di combinare le API......e non tutte le combinazioni forniscono AE...

![marco togni](./img/img39.png)

Per tutte le implementazioni per motivi di efficienza, viene usato l'HMAC e non l'encrypted CBC-MAC

- SSL: autenticatore sul messaggio, si cifra tutto (messaggio + autenticatore);
- IPsec: si cifra + si costruisce il MAC sul cifrato
- SSH: si cifra + si costruisce l'autenticatore sul messaggio in chiaro

L'opzione 3 viene scartata: qualche bit del testo in chiaro per come funziona le funzione hash crittograficamente sicura, potrebbe anche rimanere anche nell'attestato di autenticità, ma visto che qui bisogna proteggere sia autenticità che integrità è importante che non riveli neanche nessuna informazione sul messaggio in chiaro ( non si può perdere la proprietà di riservatezza).

La soluzione ottimale è SSL perché se il messaggio non è integro ed autentico non lo si va a decifrare. Nel secondo caso, si deve lo stesso decifrare per poi calcolare integrità ed autenticità.

Esistono degli standard per ottenere authenticated encryption. A seconda della modalità di cifratura che si sta usando si possono avere degli attacchi. La modalità MAC-then-Encrypt (SSL) non è sempre robusta nelle implementazioni anche se a livello concettuale va bene (es. modalità CBC). Gli standard a prescindere dalla modalità di cifratura usata funzionano sempre bene e utizzano la modalità Encrypt-then-MAC.

### Esempio

È possibile trovare questo problema nelle vecchie versioni di TLS. Supponiamo che mittente e destinatario abbiano negoziato la modalità CBC per negoziare i dati. Nel protocollo, viene eseguito MAC-then-Encrypt cioè viene preso m, viene calcolato HMAC su m, m || HMAC viene sottoposto a CBC.

TLS ha un pacchetto formato da type, version, lenght, data, MAC, padding e tutto è cifrato. Nel padding, viene scritto i byte che sono stati riempiti. Esempio, 3 byte, il padding sarà 3 3 3.

Se c'era stato in decifrazione un errore legato al padding veniva restituito "padding error". Se invece veniva scartato il pacchetto TLS perché non era integro/autentico veniva restituito "MAC error". L'intrusore osservando questi messaggi sa cosa è successo.

Un attaccante può fare il seguente attacco (padding oracle):
- L'attaccante invia un testo cifrato scelto e può sapere se gli ultimi byte relativi a un padding validi o no.

Tuttavia, in SSL, anche se sono stati rimossi questi errori è possibile effettuare un attacco di timing attack: si osservano i tempi di decifrazione. Se la risposta arriva subito vuol dire che l'errore è relativo al padding altrimenti è un errore di decifrazione.

![marco togni](./img/img40.png)

Bisogna adottare la modalità MAC-then-encrypt. Il testo sorgente è cifrato è costituito da tre blocchi: c0, c1 e c2. L'attaccante intercetta il cifrato e vuole decifrare solo m1.

Toglie c2 e fa in modo che la destinazione decifri un testo cifrato scelto. Suppone che l'ultimo byte di m1 è 1 (quindi il padding). L'intrusore modifica l'ultimo byte di c0 e lo modifica (ad hoc perché non conosce il cifrato) 

da 2.16.36

### Integrità & Origine & Non ripudio

Il cifrario simmetrico non garantisce autenticazione (solo in sotto scenari). Confidenzialità: se l'intrusore fa attacchi passivi va bene altrimenti non viene garantita la proprietà. In questo caso bisogna usare authenticated encryption.

Se si dispone solo di un cifrario simmetrico, si può garantire non ripudio? Si, ma è complesso

La firma digitale è un concetto ad alto livello che garantisce non ripudio. Le proprietà di un servizio di firma digitale su un dato sono:
- Consente a chiunque di identificare univocamente il firmatario perché per dire ch è stata una determinata persona a firmare
- Non poter essere imitata da un impostare: un intrusore non deve imitare la firma
- Non poter essere trasportata da un messaggio ad un altro: se la sorgente usa dei bit che rappresentano una firma, questi non possono essere presi e spostati su un altro messaggio.
- Non poter essere ripudiata dall'autore
- Rendere inalterabile il messaggio in cui è stata apposta: quel contenuto deve essere conforme per quello che è stato firmato.

### 21-10-2021

00-54.00 rivedere questa parte!

È necessario inserire una terza entità (come un notaio). Come costruire il servizio di firma digitale con un cifrario simmetrico:

Ci sono A e B, T è la terza parte. Ci sono delle chiavi precondivise tra A e B e questa terza parte. A quando vuole inviare un documento firmato digitalmente, deposita il documento alla terza parte. T invierà ad A la ricevuta ad A. A invierà il contratto comn la ricevuta a B e B verifica con T la verifica del documento.

### Registro Atti Privati

Chiede solo le considerazioni e non il funzionamento. Ma che significa?

Con questo protocollo si risolvono i problemi del ripudio e della falsificazione ma si introducono altre problematiche:

- Autorità sempre online
- Collo di bottiglia
- Fidarsi dalla terza parte
- Amministrare le chiavi in modo robusto altrimenti viene compromesso il servizio

### Meccanismi asimmetrici

Viene usata per costruire generatori di numeri pseudo-casuali, cifrari che garantiscono riservatezza, schemi di meccanismi di firma digitale che garantiscano il non-ripudio e qualunque protocollo di identificazione/autenticazione. In particolare, viene usata soprattutto con schemi di firma digitale. Non viene utilizzata per motivi di efficienza per costruire cifrari con PNRG crittocraficamente sicuri.

Rispetto ai cifrari simmetrici, si inizia a vedere la distribuzione delle chiavi perché per poterli usare in modo efficace bisogna capire prima l'infrastruttura.

### Come distribuire le chiavi pubbliche in modo sicuro

Quandi si usa una chiave pubblica bisogna essere certi dell'identità del proprietario e quindi poterla verificare. Si immagini l'utlizzo della chiave per motivi di confidenzialità: se si deve cifrare i dati per Luca, si deve prendere la chiave pubblica di Luca, darla in pasto alla funzione di encryption E e poi Luca userà la chiave privata sulla funzione di decryption. Se si usa una chiave pubblica che appartiene ad un altra persona e non a Luca, vuol dire cifrare i dati probabilmente per un intrusore.

Lo stesso vale per l'operazione di verifica: se Luca vuole firmare un documento, lo darà in pasto alla trasformazione V. Se la sequenza di bit che arriva al destinatario non appartiene a Luca, vuol dire che è un intrusore ad averla cambiata.

### Autorità di certificazione

L'obiettivo è costruire un'infrastruttura che consenta di memorizzare le chiavi pubbliche e chiunque le prelevi è certo che la chiave pubblica appartenga a chi dice di essere. Si usa, quindi, una terza parte detta _autorità di certificazione_.

L'_autorità di certificazione_ ha il ruolo di dire se una sequenza di bit appartiene a Luca, la firma e chiunque può verificare l'attestato di autenticità per affermare che la chiave pubblica è autentica.

### Certificato a chiave pubblica

Un certificato è una struttura dati le cui informazioni minime che deve per forza contenere sono:

- nome del proprietario della chiave pubblica
- chiave pubblica
- firma su queste due informazioni

Come ogni struttura dati, per essere usati su larga scala, deve essere interoperabili e quindi esistere uno standard di rappresentazione in modo che tutti gli applicativi possano interpretare. Questo standard si chiama X.509.

![marco togni](./img/img46.png)

Le informazioni sono le seguenti:
- Versione dello standard: al momento le versioni dello standard sono 3 (1, 2 e 3);
- Numero seriale del certificato: ogni certificato ha un numero univoco che lo identifica all'interno della terza parte. Non è pensabile che ci sia una terza parte globale ma tante terze parti che si fanno garante del proprio dominio;
- Algoritmo: quale algoritmo della trasformata V è stato usato dalla terza parte per costruire l'attestato di autenticità;
- Iusser Name: quale nome è della terza parte ed è interpretabile dall'essere umano. Ad esempio, Posteitaliane in quanto organizzazione potrebbe avere più nomi. Posteitaliane per la pubblica amministeazione e Posteitaliane per i privati;
- Period of validity: dice quanto è valido il certificato da usare. La terza parte non assume a vita per un tempo illimitato che a Luca corrisponde una stringa di bit. Si assume legalmente la responsabilità. Se qualcosa va storto pagherà i danni economici conseguenti all'uso scorretto del certificato. Ad esempio, per un anno quell'associazione è corretta. Se durante questo anno va storto nelle clausole contrattuali sarà responsabile la terza parte;
- Subject Name: possessore del certificato
- Subject's public key info: stringa bit che corrisponde alla chiave pubblica
- Estensione: Campi aggiuntivo. rende flessibile ai fini applicativi il certificato. Se distribuisco in una repository pubblica un certificato, può servire il certificato qual è il ruolo di Luca o il suo indirizzo di lavoro, email istituizione? A volte si usa questo campo per aggiungere info a livello applicativo.

La firma viene fatta su tutte le informazioni della struttura dati perché deve essere garantita l'autenticità, tranne il campo estensione perché queste informazioni sono da verificare e non è detto che siano corrette.

Tutte le volte che si aggiungono campi bisogna chiedersi se sono necessarie perché si aggiunge un overhead di rete, di memorizzazione. 

### PKI (Public Key Infrastructure)

con PKI si intende un'infrastruttura costituita da un insieme di componenti che serve per gestire il ciclo di vita delle chiavi pubbliche. Senza questa architettura non si possono usare i cifrari asimmetrici su larga scala. Da un punto di vista architetturale i componenti sono i seguenti:

- **CA**: autorità di certificazione;
- **RA**: autorità di registrazione;
- **Directory**: repository in cui si trovano tutti i certificati.

<!--Gli utenti possono usufruire di molteplici servizi: possibilità di ottenere un certificato a chiave pubblica, di rinnovarlo quando scade, revocare un certificato quando sono cambiate informazioni, compromesso etc.

Fase di inizializzazione:
Un utente all'inizio deve farsi identificare, una volta identificato ottenere dall'autorità di certificazione un certificato. Una volta ottenuto dovrà essere pubblicato su un sistema di Directory

Fase a regime:
Gli utenti interagiscono con un sistema di Directory per ottenere i certificati degli altri utenti che si sono già registrati.

L'autorità di certificazione gestisce le operazioni di amministrazione del certificato, deve poter revocare il certificato e deve pubblicare un'informazione relativa la revoca di quel certificato.-->

### Directory

Esiste uno standard X.500 che può essere usato per integrato nell'infrastruttura PKI.

Consente di creare un sistema di Directory distribuito capace di garantire alte prestazioni e alta disponibilità.

![marco togni](./img/img48.jpg)

Dato che è distribuito, ci sono diversi nodi: DSA (Directory Service Agent) che gestisce un sottoinsieme di informazioni e quando un utente detto DUA chiede informazioni al proprio DSA e se non ha le informazioni richieste, si coordina con gli altri DSA per ottenere le informazioni richieste.

Inoltre, può differenziare tra accesso anonimo e accesso autenticato. Un certificato anonimo va bene per i certificati perché le informazioni non è critica ma per sua natura deve essere pubblica.

![marco togni](./img/img47.png)

Un Directory X.500 prevede di memorizzare le informazioni secondo un modello concettuale che ruota attorno a due concetti:
- Oggetto: definisce quali attributi sono richiesti e consentiti in una entry;
- Attributi: è formato da una coppia chiave-valore. Ogni attributo ha un tipo e uno o più valori

Il modello informativo è incentrato sulle entry, che sono composte da attributi; ogni entry è associata a una classe di oggetti che descrive diversi gli attributi e i valori che dovrebbe contenere.

Le entry all'interno di una directory sono memorizzate secondo una schema gerarchico a File System.

Esempio di schema:

![marco togni](./img/img49.png)

Sono utenti che appartengono ad una multinazionale. A livello concettuale è stato deciso di rappresentare nel seguente modo:

Si vuole dare le informazioni a livello geografico. Ad esempio in Canada che è la radice, si ha l'organizzazione e a sua volta ci sono le sedi fino ad arrivare ai dipendenti specifici. Le informazioni sono organizzate sotto forma di entry e sono organizzate gerarchicamente e ogni entry ha un suo nome.

X.500 definisce come devono essere organizzati lato server i DSA mentre lato client come accedere alla directory. Il protocollo di accesso alla directory è LDAP. Ad esempio, per l'autenticazione in UNIBO si usa questo protocollo.

### Richiesta di un certificato

Il protocollo che consente ad un utente di registrarsi a un PKI è il seguente:

Inizializzazione:
Luca deve generare una coppia di chiavi, deve farsi identificare da una registration authority e Luca quando deve richiedere un certificato:
- chi riceve la richiesta di certificato, ci deve essere il nome del richiedente perché deve essere verificato chi dice di essere;
- Nella richiesta, Luca possiede effettivamente la sua chiave privata?
Come si garantisce di possedere effettivamente la chiave privata:


### Protocolli di gestione

Esistono diversi modelli con cui è possibile mettere in piedi infrastrutture di chiave pubblica che supportino le richieste di certificato:

- **Schema centralizzato**: prevede che ci sia solo utente finale e un'autorità di ceritificazione (CA). La generazione delle chiavi avviene direttamente da parte dell'autorità di certificazione;
- **Schema a tre parti**: prevede che ci sia l'utente, un RA e una CA.

### Schema centralizzato

Da punto di vista operativo questo schema non viene mai usato. Questo modello può andare bene se si vuole realizzare solo un servizio di cifratura: un'azienda con i suoi dipendenti aziendali:
  - **Vantaggi**: una CA interna salva la chiave privata e distribuisce la coppia di chiavi ai dipendenti che la utilizzano poi per scambiare informazioni. L'azienda è proprietaria dei dati e in questo modo può risalire a tutti i dati in caso se la chiave privata venga persa;
  - **Svantaggi**:
    - il supporto al non ripudio non è garantito perché la chiave privata l'ha due entità diverse. Per questo motivo non la si può usare come firma digitale.
    - La CA è contattata da tutti gli utenti è quindi c'è un certo carico ma soprattutto c'è una porta in ascolto. Meno la CA ha aperte porte aperte verso l'esterno meglio è perché ha la coppia di chiavi con cui rilascia i certificati.

### Schema a tre parti

I modelli a tre parti, possono prevedere diverse alternative:

- L'utente comunica solo con la RA che a sua volta comunica solo con la CA. L'utente avvia il processo di generazione delle chiavi, si deve far identificare di persona dalla RA. Ad esempio, per ritirare il badge ci si presenta di persona per farselo rilasciare (sorta di RA). RA a questo punto, se l'utente si identifica e trova il possesso della chiave privata, invia una richiesta alla CA chiedendo di rilasciare il certificato e lo restituisce alla RA che a sua volta lo restituisce all'utente.

La normativa italiana prevede che la chiave segreta sia generata dall'utente perché deve avere il controllo pieno. Da un punto di vista tecnico la generazione può avvenire in due modi:
- Viene chiesto un certificato fisicamente: ci si reca dalla RA che restituisce un modulo crittografico ma vuoto. L'utente in sua presenza avvia la generazione della coppia di chiavi. Il modulo crittografico è collegato ad esempio tramite una seriale a una smart card e al software della RA e restituisce la coppia di chiavi. Successivamente, l'utente cambia il PIN iniziale. L'identificazione è verificata. Questo modello ha un rallentamento perché bisogna fare numerosi passaggi e c'è una fase in cui la chiave privata non è di proprietà dell'utente.
![img](./img/img50.png)
- Viene chiesto un certificato da remoto: prevede che l'utente sia stato identificato una volta dalla RA. RA rilascia un autenticatore che lo si conserva fino al momento del bisogno. Al momento dell'identificazione si genera una chiave pubblica da remoto e la si invia alla RA oppure direttamente alla CA. RA/CA deve identificare e poi verificare che l'utente abbia davvero la chiave segreta corrispondente e invia il certificato. (lo standard IAK)
![img](./img/img51.png)
Il protocollo 
Quando si fa una richiesta autenticata, l'utente deve aver ricevuto fuori banda un autenticatore iniziale, dopo deve aver generato le chiavi e deve aver creato una richiesta di certificato. La richiesta deve essere autenticata e si deve dimostrare di avere la chiave segreta.

### Prova di possesso (POP)

È fondamentale garantirla perché ovviamente se non si avessero le garanzie della prova di possesso:
- Luca mette sul canale la chaive pubblica ma l'intrusore mette la sua chiave. La CA prende la stringa di bit che ha generato l'intrusore e produce un certificato. Chinque vuole parlare con Luca in realtà parla con l'intrusore.
- L'intrusore manda una richiesta a nome di Luca, la CA prende la stringa di bit generata e la registra come appartenete a Luca anche se non è davvero lui.

La prova di possesso si può realizzare in vari modi:
- Da un punto di vista concettuale, si dovrebbe prendere il documento, appendere il certificato e dopo firmare tutto però questo a livello applicativo significa costruire applicazioni che prevedono la prova di possesso del certificato a tempo di firma. Ma può essere molto oneroso
- Si mette la prova di possesso già al rilascio del certificato. Controllo a livello di infrastruttura
- Metodi fuori banda:
- Metodi online

### Revoca di un certificato

Un'infrastruttura deve gestire anche la revoca di un certificato. Lo si deve revocare quando succede qualcosa di sbagliato durante la validità temporale del certificato:
- Può capitare che un utente non sia più fidato e quindi non si accetta più niente da lui
- Un certificato presenta delle informazioni che sono cambiate e quindi bisogna costruirne uno nuovo.

### Modelli di notifica della revoca

Un criterio con cui vengono classificati i modelli è il seguente:

- **Modello pull**: ci sono gli utenti che accedono alla directory e ritrovano le informazioni quando si accedono. Le informazioni vengono _tirate_
- **Modello push**: quando un certificato viene revocato, gli utenti ricevono la notifica.

Un secondo criterio si basa se si ha una connessione oppure no:

- **Schemi on-line**: consente di verificare lo stato di verifica di revoca online
  - Online Certificate Status Protocol
- **Schemi off-line**: consente di verificare lo stato di verifica di revoca offline
  - Certificate Revocation List
  - Certificate Revocation Tree

I modelli push non sono molto implementati perché sono piuttosto complessi. Bisogna vedere se un utente è mobile/stazionario etc. Quindi, si preferiscono i modelli push.

### Lezione 27-10-2021

### CRL (Certificate Revocation List)

Per rendere partecipi tutti gli utenti che una chiave non deve essere più usata, CA mantiene on-line una lista autenticata dei certificati revocati (CRL).

È un modello pull il cui funzionamento è off-line.

![marco togni](./img/img52.png)

La Certificate List è composta da alcuni campi che riguardano la revoca:

- **Revoked certificate**: questo campo contiene a sua volta:
  - **user certificate serial**: numero seriale del certificato. Il numero seriale è un ID univoco. In generale, in questo campo si potrebbe inserire:
    - **chiave pubblica**
    - **nome del possessore**: il nome del possessore non è una buona idea perché ad un nome possono essere associate più chiavi quindi non si sa quale è stata la chiave revocata.
    - **id univoco**: tra tutti i certificati si sa a quale chiave appartiene in modo semplice
  - **revocation date**: quando alla CA è arrivata la notifica di revoca. Tutto quello che è stato firmato prima, ovviamente, è valido.
  - **crlExtensions**: campo opzionale in cui si specifica il motivo della revoca.
- **This Update Date** e **Next Update Date**: l'autorità di certificazione emette a scadenze temporali, ad esempio, con scandenza bisettimanale, ogni ora etc, la lista di revoca. Le informazioni contenute in questa struttura dati valgono dal valore di "This Update Date", fino a "Next Update Date". Non valgono né prima né dopo.

Problemi:
- La lista di revoca viene pubblicata sulla Directory e verrà sostituita/affiancata (dipende dalla politica della CA) all'istante di tempo Next Update Date. Se questa lista viene pubblicata su una directory, sarà l'utente finale tramite il protocollo LDAP a recuperare la lista di revoca e può decidere se conservarla in locale fino al prossimo aggiornamento. Questa è una decisione lato cliente. Si può verificare lo stato di revoca in maniera offline.
Problema di freschezza delle informazioni: se in quell'arco temporale, un altro certificato viene revocato, come fa l'utente finale a saperlo? Deve solo aspettare l'aggiornamento successivo. Se si deve sapere in tempo reale in tempo reale, la lista di revoca non è l'opzione migliore.
- Dimensione della struttura dati: questa struttura dati cresce nel tempo. Se ad esempio, la frequenza di revoca è circa del 10 per cento all’anno, i certificati con validità temporale di due anni, popolazione stabile di circa 100000 certificati allora la dimensione media di una CRL circa 20000 entries. Non è tanto un problema lato directory perché esse sono pensate per mantenere un grande numero di dati ma è un problema sull'occupazione di banda e lato cliente. Se il dispositivo ha limitate capacità questo è un limite forte di progettazione.

Possibili soluzioni:
- Le CRL possono diventare molto grosse e quindi onerose da scaricare e da esaminare:
  - Eliminare la revoca dopo la prima CRL successiva alla scadenza del certificato: se un certificato è scaduto temporalmente, non ha senso mantenerlo nella lista di revoca perché non passerebbe l'operazione di verifica. (Da vedere);
  - pubblicare CRL complete (Base CRL) e poi solo le differenze (Delta CRL): Ad esempio, si suppone che dopo la prima settimana di operatività della CA, essa emette la prima lista di revoca. Questa lista è chiamata Base CRL e sarà sempre disponibile. Dalla seconda settimana in poi la Ca emetterà una variazione rispetto alla . Ogni settimana, la CA non emette tutta la storia fino a quel momento ma emette solo le variazioni di quello specifico arco temporale. Queste variazioni prendono il nome di Delta CRL. l'utente finale, la prima volta scarica la Base CRL. Se il certificato non è nella Base, scarica le Delta CRL fino a quando non trova il certificato. Nei casi fortunati, si scaricano poche liste e c'è anche un risparmio di memorizzazione però nel caso sfortunato si scarica tutta la storia.
  - partizionare le CRL in tanti gruppi (es. per ogni mille certificati emessi) usando CRL DP: la struttura dati complessiva viene partizionata. I criteri possono essere molteplici: tutti i certificati che hanno validità temporale di un anno finiscono in una partizione, in ordine seriale etc. Sulla directory viene pubblicata partizioni di lista di revoca. Quindi, bisogna definire un modello di distribuzione del criterio lato cliente. Nel certificato, ci sono campi estensioni in cui è possibile veicolare informazioni in più. Si aggiunge come campo "Distribution point". La CA sa di certo che se un certificato verrà revocato, finisce già in una certa partizione perché conosce qual è il criterio adotatto. Quindi, viene già indicato all'interno del campo. Il Distribution point è   È il percorso all'interno della gerarchia della directory. Come un file system. (vedi figura della directory) in cui si troverà eventualmente l'informazione sullo stato di revoca. L'utente, userà il distribution point nella query LDAP.

  A seconda del meccanismo che si usa, nella struttura dati CRL ci sono campi aggiuntivi come ad esempio se è una CRL Base o Delta, Distribution Point etc.

### OCSP

È un protocollo standard client-server che permette ad un utente finale di chiedere a un server lo stato di revoca di uno specifico certificato. Ci sono come componenti un RA e CA ma non una directory per lo stato di revoca. Si interroga un server che sempre è online perché deve restituire la risposta. Il protocollo definisce lo standard di richiesta di come deve essere mandato il messaggio di richiesta e di risposta (buono, revocato o sconosciuto)

Il server è un possibile collo di bottiglia per cui bisogna progettarlo in modo opportuno.

Il protocollo non dice qual è la sorgente da cui attingere i dati per dire se il certificato è buono o no. Il protocollo dice solo di restituire come risposta buono, revocato o sconosciuto.

Se il server restituisce un'informazione in tempo reale si supera il problema 1 messo in evidenza in CRL ma se il server usa le liste di revoca non si elimina il problema della freschezza. Dipende da come attinge le informazioni.

### Performance Evaluation Criteria

Per confrontare i diversi meccanismi a disposizione, bisogna adottare metodi di confronto. I principali sono:

- Freschezza dell'informazione di revoca: tempo massimo tra revoca e distribuzione
- Carico computazionale sulle entità coinvolte: lato CA, lato cliente etc
- overhed in termini di banda

È bene ricordare che esistono molti altri:

- Sicurezza: l'ìnformazione di revoca garantisce autenticità (cioè chi è che mi fornisce l'informazione), integrità, confidenzialità, non ripudio.
- Standard: adesione a uno standard, proprietario
- Espressività: motivo per cui il certificato è stato revocato.
- On-line vs Off-line: se si viaggia in aereo molto, prima scarico e durante il volo verifico.

<!--- -->
<!--[marco togni](./img/marco_togni.jpg)-->

<!--![cyber sesso](https://user-images.githubusercontent.com/56556806/134823047-da26060a-3813-4e73-a13c-256bcd0483c4.png)-->

<!--# How I Defeated Fascism with the Power of Love

## Chapter 1: The Power of Love

The first step in my journey was realizing that it is impossible to defeat
fascism with the power of love.

## Chapter 2: The Power of Incredible Violence-->
