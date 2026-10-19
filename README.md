# PianoLed per Android

Scarica l'APK dalla [release piu recente](https://github.com/almahub/pianoled/releases/latest), aprilo sul telefono e conferma l'installazione.

**Non disinstallare la versione precedente:** gli aggiornamenti con la stessa firma conservano libreria e impostazioni.

Dalla versione 0.2.0, apri **Aggiornamenti** nell'app e abilita le notifiche. Il controllo avviene all'apertura (almeno 15 minuti tra controlli riusciti) e circa ogni 6 ore con Internet. Android puo ritardarlo per risparmiare batteria. Il player funziona offline.

**Aggiorna VERSIONE** scarica l'APK e ne verifica integrita, versione e firma. Android richiede conferma prima di installare. Se richiesto, consenti a PianoLed di installare app, torna alla schermata e premi **Installa**.

La versione 0.1.0 richiede una prima installazione manuale dell'APK recente per abilitare questa funzione. Nella 0.6.0 apri **Impostazioni → App e aggiornamenti → Aggiornamenti** (nelle versioni 0.3–0.5 era direttamente in Impostazioni).

## Novità 0.6.0

Il **Player mostra i tasti suonati dal vivo** dalla tastiera Bluetooth MIDI:
verde pieno per i tasti premuti, bordo verde per le note tenute dal pedale.
Funziona anche con il brano fermo, con zoom, Espandi e rotazione. I colori
sinistra/destra delle tracce restano separati dalla visualizzazione dal vivo.
Il suono continua a uscire dal pianoforte.

Le sezioni principali sono **Player, Libreria e Impostazioni**. Dentro
Impostazioni trovi quattro aree: **Live MIDI**, **LED Studio**,
**Connessione ESP32**, **App e aggiornamenti**.

Per collegare la tastiera: **Impostazioni → Live MIDI → Cerca tastiere**,
consenti **Dispositivi nelle vicinanze**, scegli **Collega** e torna al Player.
Sul Roland FP-30: FUNCTION + La0 attiva Bluetooth; FUNCTION + Si0 seleziona
MIDI. Se non compare, chiudi altre app collegate al pianoforte e riprova.
La ricerca dura 15 secondi. Cambiare sezione mantiene la connessione;
uscire dall'app la chiude e pulisce i tasti. Al ritorno ricollegare.

**Non serve aggiornare il firmware ESP32.** LED Live MIDI, USB e Attendi nota
non sono ancora attivi. Compilazione e test automatici superati; verificati
ricevitore e interfaccia sull'emulatore Android 16 con MIDI simulato. La prova
della nuova visualizzazione sul telefono e sul Roland reali resta da effettuare.

## Supporto matrice dalla 0.4.0

Compatibilità con il firmware Android matrice: primo modulo Do1–Si1,
12 colonne da 10 LED. Riconoscimento automatico del profilo della scheda,
luminosità limitata al 15% e prova del modulo in LED Studio. Le note scendono
con due secondi di anticipo; l'audio parte dopo circa 2,5 secondi di preparazione.
Le note fuori dal modulo continuano a suonare sul telefono. Rimane supportato
il firmware Android v2 per la striscia da 176 LED.

Il firmware matrice si installa separatamente via USB: l'aggiornamento APK
non modifica la scheda. L'estensione a 850 LED non è attivata.

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

Lo sviluppatore compila e firma localmente con la chiave originale. Aggiunge una nuova cartella `releases/VERSIONE/` con `PianoLed.apk` e `latest.json`. GitHub Actions verifica dimensione e SHA-256 e pubblica entrambi in una release prima in bozza, poi visibile. Le release gia pubblicate non vengono sovrascritte.

Il telefono consulta `https://github.com/almahub/pianoled/releases/latest/download/latest.json`.
