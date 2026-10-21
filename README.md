# Room-boh

Riverbero gratuito: VST3 per **Windows x64** e **Mac Apple Silicon**, Audio Unit per Mac.

Produttore: **Valla Productions**.

![Interfaccia di Room-boh](docs/interface.png)

## Download

Scarica il pacchetto adatto al tuo sistema dalla [release 1.0.3](https://github.com/vallaproductionsoriginal-byte/Room-boh/releases/tag/v1.0.3):

- **Room-boh-win-x64.zip**: Windows 10/11 a 64 bit, VST3.
- **Room-boh-mac-arm64.zip**: Mac Apple Silicon, macOS 11 o successivo, VST3 e Audio Unit.

Il file `SHA256SUMS.txt` permette di verificare l'integrità di entrambi gli ZIP.

## Installazione

### Windows x64

1. Estrai completamente `Room-boh-win-x64.zip` e chiudi la DAW.
2. Copia l'intera cartella `Room-boh.vst3` in `C:\Program Files\Common Files\VST3\`, mantenendo la struttura del bundle. Windows può richiedere i privilegi di amministratore.
3. Riapri la DAW a 64 bit e aggiorna la scansione VST3. Il produttore è **Valla Productions**.

Il runtime MSVC è incluso staticamente. Per disinstallarlo, chiudi la DAW ed elimina la cartella del plugin.

### Mac Apple Silicon

Serve un **Mac con chip Apple Silicon (serie M)**, macOS 11 o successivo e una DAW con supporto VST3 o Audio Unit avviata nativamente, senza Rosetta. Questa versione non è compatibile con i Mac Intel. Per controllare il chip, apri il menu ** > Informazioni su questo Mac**.

**Il plugin non è firmato con un certificato Apple Developer ID e non è notarizzato da Apple.** È presente una firma locale ad hoc, che non identifica lo sviluppatore presso Apple: per questo macOS può bloccare l'installazione o il primo caricamento nella DAW. Segui i passaggi qui sotto per autorizzarlo. Per installare il plugin non servono Xcode né un account sviluppatore.

#### Installazione passo passo

1. Scarica **Room-boh-mac-arm64.zip** dalla [release ufficiale](https://github.com/vallaproductionsoriginal-byte/Room-boh/releases/tag/v1.0.3) e fai doppio clic sullo ZIP per estrarlo.
2. Chiudi completamente la DAW (il programma con cui lavori all'audio, ad esempio Logic Pro, Ableton Live o REAPER).
3. Apri il **Finder**, premi **Maiuscole + ⌘ + G** (menu **Vai > Vai alla cartella…**), incolla `~/Library/Audio/Plug-Ins/VST3/` e premi Invio. Copia qui **Room-boh.vst3** dalla cartella estratta.
4. Per usare anche l'**Audio Unit**, richiesto da Logic Pro, ripeti il passaggio con `~/Library/Audio/Plug-Ins/Components/` e copia qui **Room-boh.component**. Puoi installare entrambi i formati o soltanto quello usato dalla tua DAW.
5. Riapri la DAW e avvia una nuova scansione dei plugin dalle sue impostazioni. Cerca **Room-boh**, produttore **Valla Productions**. I file `.vst3` e `.component` si caricano nella DAW: non si aprono come applicazioni autonome.

Il simbolo `~` indica la tua cartella utente. Se una cartella di destinazione manca, apri `~/Library/` nel Finder e crea le cartelle mancanti nella sequenza **Audio > Plug-Ins > VST3** oppure **Audio > Plug-Ins > Components**, rispettando i nomi.

**Alternativa automatica:** dalla cartella estratta puoi fare doppio clic su **Install.command**. Si apre Terminale e lo script copia entrambi i formati nelle stesse cartelle, conservando una copia di eventuali versioni precedenti. Se macOS blocca lo script, usa la procedura seguente oppure l'installazione manuale appena descritta.

#### Se macOS segnala “sviluppatore non verificato” o “Apple non può verificare…”

Questa procedura vale per **Install.command** e per il plugin quando viene bloccato durante la scansione della DAW. Autorizza soltanto i file scaricati dalla release ufficiale di Room-boh.

1. Dopo il tentativo di apertura o scansione, chiudi l'avviso con **Fine** o **Annulla**.
2. Apri ** > Impostazioni di Sistema > Privacy e sicurezza** e scorri fino alla sezione **Sicurezza**. Accanto al messaggio relativo a Room-boh o a Install.command, premi **Apri comunque**. Nelle versioni meno recenti di macOS il percorso è **Preferenze di Sistema > Sicurezza e Privacy > Generali**.
3. Conferma con la password del Mac o Touch ID, se richiesto, e premi **Apri** nell'eventuale nuovo avviso. Se hai autorizzato l'installer, lascia terminare l'installazione.
4. Chiudi e riapri la DAW, quindi ripeti la scansione. Se installi entrambi i formati, macOS può chiedere di autorizzarli separatamente.

Il pulsante compare dopo un tentativo bloccato; se manca, riprova ad aprire lo script o a scansionare il plugin. Riferimento: [guida ufficiale Apple per aprire software non autenticato](https://support.apple.com/it-it/102445).

#### Se il plugin resta bloccato e “Apri comunque” non compare

Dopo aver copiato il plugin nelle cartelle indicate sopra, chiudi la DAW e apri **Terminale** cercandolo con **⌘ + Spazio**. Per la copia scaricata dalla release ufficiale, incolla il comando del formato che hai installato e premi Invio. Se li hai installati entrambi, esegui entrambi i comandi, uno alla volta.

**VST3:**

```sh
xattr -dr com.apple.quarantine "$HOME/Library/Audio/Plug-Ins/VST3/Room-boh.vst3"
```

**Audio Unit:**

```sh
xattr -dr com.apple.quarantine "$HOME/Library/Audio/Plug-Ins/Components/Room-boh.component"
```

Questi comandi rimuovono l'attributo di quarantena soltanto dai bundle di Room-boh indicati, lasciando attive le protezioni generali di macOS. Non richiedono `sudo` né la password. Se compare `No such file or directory`, verifica di aver copiato il formato corrispondente nella cartella corretta.

Riapri la DAW e ripeti la scansione; se il plugin era stato escluso, usa la funzione della DAW per ripetere la verifica dei plugin non caricati. Se l'Audio Unit non compare ancora, riavvia il Mac e ripeti la scansione. Se macOS segnala un file danneggiato, scarica nuovamente lo ZIP ufficiale e reinstallalo prima di riprovare.

Per disinstallarlo, chiudi la DAW ed elimina `Room-boh.vst3` e/o `Room-boh.component` dalle rispettive cartelle di installazione.

## Controlli

- **Space:** Mix, Pre-delay, Decay, Depth, Lo Cut e Hi Cut.
- **Early:** Size, Send, Diffusion, Space, Cross, Mod Rate e Mod Depth.
- **Late:** Size, Bass Mult, Bass Xover, High Mult, High Xover, Cross, Mod Rate e Mod Depth.
- **Mode:** Open Hall, Small Studio, Air Bloom, Silk Hall, Warm Loft, Shadow Hall, Night Vault, Orbit, Prism, Nebula, Abyss e Mosaic.
- **Preset:** dodici programmi di fabbrica modificabili.
- **Bypass** e meter stereo RMS/peak.

Mix a 100% per un bus ausiliario. Depth bilancia le riflessioni iniziali e la coda; Decay indica il tempo di decadimento medio approssimativo. Bass Mult e High Mult regolano il decadimento delle rispettive bande. Lo Cut a 0 Hz disattiva il filtro; Cross a 0 rende mono la relativa sezione. Doppio clic per ripristinare il valore iniziale di un controllo; clic sul valore per digitarlo.

## Compatibilità

Sono disponibili configurazioni mono, stereo e ingresso mono con uscita stereo. Il percorso dry ha latenza zero. Tutti i ventitré parametri sono esposti alla DAW e vengono salvati nella sessione. DSP, caricamento VST3, audio, preset, stato ed editor sono verificati su un runner Windows x64 e in un host JUCE locale Mac a 44.1, 48, 96 e 192 kHz; Audio Unit è verificato su Mac; la compatibilità può variare tra DAW.

## Licenza

Il codice e il materiale originali di Room-boh sono soggetti alla **licenza proprietaria** riportata in [LICENSE](LICENSE). Copyright (c) 2026 Francesco Valla. Tutti i diritti riservati. L'uso, anche commerciale, richiede l'autorizzazione espressa del titolare ed è consentito nei limiti del permesso accordato. Modifica, redistribuzione, sublicenza e rivendita richiedono il suo previo consenso scritto. Per le richieste: [vallaproductionsoriginal@gmail.com](mailto:vallaproductionsoriginal@gmail.com). La release pubblica contiene il plugin compilato; i sorgenti sono riservati e accessibili solo alle persone autorizzate.

La distribuzione usa la licenza commerciale JUCE Starter. La licenza proprietaria di Room-boh non si applica ai componenti di terze parti: JUCE e le altre dipendenze conservano i propri termini e avvisi, riportati in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) e nella cartella [licenses](licenses).

Per segnalare problemi, apri una issue indicando DAW, versione del sistema operativo, frequenza di campionamento e passaggi per riprodurre il problema.
