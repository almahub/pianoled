# NotaLume per Android

**Music becomes light.**

NotaLume è il nuovo nome di PianoLed: stesso package Android, stessa firma e
stessi dati. La versione 0.8.0 aggiorna anche chi ha installato la build locale
0.7.0. Il repository e l'indirizzo degli aggiornamenti restano gli stessi.

## Novità 0.8.0

**LED Studio** permette di provare ogni matrice separatamente: Do1–Si1 fino
a Do7–Si7, colonna Do8 oppure tutte le matrici. La lista segue il profilo
del dispositivo collegato.

Due nuovi **effetti test**, senza audio:

- **Arcobaleno**: onde multicolore sulle dieci righe, continue tra i moduli.
- **Kit**: punto rosso con scia sulla riga vicina ai tasti, da sinistra a destra
  e ritorno.

Gli effetti seguono la matrice selezionata, durano 30 secondi e si fermano con
**Ferma test**, uscendo da LED Studio, sospendendo l'app o perdendo la connessione.
Rimane il limite di luminosità al 15%.
Richiedono il firmware matrice revisione 3 con supporto LED Studio; l'APK non
aggiorna il firmware via Wi-Fi. Con il firmware precedente rimangono disponibili
player e test sequenziale dei moduli.

Le diciture di collegamento ora sono **Connessione a NotaLume**,
**Trova NotaLume** e **NotaLume connesso**. Indirizzi di rete e ricerca restano
compatibili.

## Novità 0.7.1

Nome aggiornato nelle schermate, nel launcher, nelle notifiche e nei nuovi APK.
Libreria, playlist, preferiti, mani, colori e connessioni rimangono conservati.
LED Studio e l'area Connessione mostrano l'estensione della matrice e il numero
di moduli, fino a **Do1–Do8: 85 note, 850 LED**. Il comando **Avvia test matrice**
segue tutte le colonne dichiarate dalla scheda. Luminosità limitata al 15%.

Live MIDI continua a visualizzare nel Player i tasti suonati; la matrice segue
i brani riprodotti. L'APK non aggiorna il firmware dell'ESP32: per passare dal
primo modulo alla matrice estesa occorre caricare separatamente il profilo
firmware corrispondente al proprio montaggio.

Scarica l'APK dalla [release piu recente](https://github.com/almahub/pianoled/releases/latest), aprilo sul telefono e conferma l'installazione.

**Non disinstallare la versione precedente:** gli aggiornamenti con la stessa firma conservano libreria e impostazioni.

Dalla versione 0.2.0, apri **Aggiornamenti** nell'app e abilita le notifiche. Il controllo avviene all'apertura (almeno 15 minuti tra controlli riusciti) e circa ogni 6 ore con Internet. Android puo ritardarlo per risparmiare batteria. Il player funziona offline.

**Aggiorna VERSIONE** scarica l'APK e ne verifica integrita, versione e firma. Android richiede conferma prima di installare. Se richiesto, consenti all’app di installare app, torna alla schermata e premi **Installa**.

La versione 0.1.0 richiede una prima installazione manuale dell'APK recente per abilitare questa funzione. Nella 0.6.0 apri **Impostazioni → App e aggiornamenti → Aggiornamenti** (nelle versioni 0.3–0.5 era direttamente in Impostazioni).

## Novità 0.6.0

Il **Player mostra i tasti suonati dal vivo** dalla tastiera Bluetooth MIDI:
verde pieno per i tasti premuti, bordo verde per le note tenute dal pedale.
Funziona anche con il brano fermo, con zoom, Espandi e rotazione. I colori
sinistra/destra delle tracce restano separati dalla visualizzazione dal vivo.
Il suono continua a uscire dal pianoforte.

Le sezioni principali sono **Player, Libreria e Impostazioni**. Dentro
Impostazioni trovi quattro aree: **Live MIDI**, **LED Studio**,
**Connessione a NotaLume**, **App e aggiornamenti**.

Per collegare la tastiera: **Impostazioni → Live MIDI → Cerca tastiere**,
consenti **Dispositivi nelle vicinanze**, scegli **Collega** e torna al Player.
Sul Roland FP-30: FUNCTION + La0 attiva Bluetooth; FUNCTION + Si0 seleziona
MIDI. Se non compare, chiudi altre app collegate al pianoforte e riprova.
La ricerca dura 15 secondi. Cambiare sezione mantiene la connessione;
uscire dall'app la chiude e pulisce i tasti. Al ritorno ricollegare.

Per la visualizzazione MIDI nel Player non serve un nuovo firmware. LED Live MIDI, USB e Attendi nota
non sono ancora attivi. Compilazione e test automatici superati; verificati
ricevitore e interfaccia sull'emulatore Android 16 con MIDI simulato. La prova
della nuova visualizzazione sul telefono e sul Roland reali resta da effettuare.

## Matrice modulare Do1–Do8

Compatibilità con il firmware Android matrice: da uno a sette moduli di
12 colonne da 10 LED, più la colonna Do8 finale per un totale di 850 LED.
Riconoscimento automatico del profilo della scheda, luminosità limitata al
15% e prova sequenziale in LED Studio. Le note scendono
con due secondi di anticipo; l'audio parte dopo circa 2,5 secondi di preparazione.
Le note fuori dal modulo continuano a suonare sul telefono. Rimane supportato
il firmware Android v2 per la striscia da 176 LED.

Il firmware matrice si installa separatamente via USB: l'aggiornamento APK
non modifica la scheda. Configurare il firmware per i moduli effettivamente
collegati e collaudare progressivamente montaggio e alimentazione.

## Funzioni del Player e Studio

Player scuro con piano roll, tastiera, zoom e vista espansa; modalità Semplice
e Studio; layout adattivo per telefono e tablet. Importazione offline di file
MIDI formato 0/1 e JSON, preferiti e raccolte playlist. Selezione delle mani
per audio e LED, colori azzurro/arancione personalizzabili, luminosità e test
sequenziale degli 88 tasti. Connessione e aggiornamenti sono in Impostazioni.

Live MIDI USB e Attendi nota sono previsti dopo la verifica di compatibilità
del telefono e del pianoforte. Non sono attivi in questa versione.

## Contenuti pubblicati

Contiene solo APK, metadati e automazione di distribuzione. Sorgenti, brani personali, credenziali e chiave di firma rimangono sul PC dello sviluppatore.

Questa funzione aggiorna l'app Android; il firmware ESP32 non viene modificato.

## Pubblicare una versione

Lo sviluppatore compila e firma localmente con la chiave originale. Aggiunge
una nuova cartella `releases/VERSIONE/` con `NotaLume-VERSIONE.apk` e
`latest.json`. GitHub Actions verifica dimensione e SHA-256 e pubblica prima
in bozza, poi rende disponibile la release. Le vecchie release mantengono
il loro file `PianoLed.apk` e non vengono sovrascritte.

Il telefono consulta `https://github.com/almahub/pianoled/releases/latest/download/latest.json`.
