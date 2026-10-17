# PianoLed per Android

Scarica l'APK dalla [release piu recente](https://github.com/almahub/pianoled/releases/latest), aprilo sul telefono e conferma l'installazione.

**Non disinstallare la versione precedente:** gli aggiornamenti con la stessa firma conservano libreria e impostazioni.

Dalla versione 0.2.0, apri **Aggiornamenti** nell'app e abilita le notifiche. Il controllo avviene all'apertura (almeno 15 minuti tra controlli riusciti) e circa ogni 6 ore con Internet. Android puo ritardarlo per risparmiare batteria. Il player funziona offline.

**Aggiorna VERSIONE** scarica l'APK e ne verifica integrita, versione e firma. Android richiede conferma prima di installare. Se richiesto, consenti a PianoLed di installare app, torna alla schermata e premi **Installa**.

La versione 0.1.0 richiede una prima installazione manuale della 0.2.0 per abilitare questa funzione.

## Questo repository

Contiene solo APK, metadati e automazione di distribuzione. Sorgenti, brani personali, credenziali e chiave di firma rimangono sul PC dello sviluppatore.

Questa funzione aggiorna l'app Android; il firmware ESP32 non viene modificato.

## Pubblicare una versione

Lo sviluppatore compila e firma localmente con la chiave originale. Aggiunge una nuova cartella `releases/VERSIONE/` con `PianoLed.apk` e `latest.json`. GitHub Actions verifica dimensione e SHA-256 e pubblica entrambi in una release prima in bozza, poi visibile. Le release gia pubblicate non vengono sovrascritte.

Il telefono consulta `https://github.com/almahub/pianoled/releases/latest/download/latest.json`.
