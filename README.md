# Room-boh

Riverbero VST3 gratuito per **Mac Apple Silicon**, macOS 11 o successivo.

![Interfaccia di Room-boh](docs/interface.png)

## Download

Scarica **Room-boh-mac-arm64.zip** dalla [release più recente](https://github.com/vallaproductionsoriginal-byte/Room-boh/releases/latest). Il file `SHA256SUMS.txt` permette di verificare l'integrità dello ZIP.

## Installazione

1. Estrai completamente lo ZIP e chiudi la DAW.
2. Copia `Room-boh.vst3` in `~/Library/Audio/Plug-Ins/VST3/`. In alternativa esegui `Install.command` dalla cartella estratta.
3. Riapri la DAW e aggiorna la scansione VST3.

Serve una DAW con supporto VST3 eseguita nativamente su Apple Silicon. Il bundle ha una firma ad hoc locale ed è privo di notarizzazione Apple; macOS può richiedere ulteriori verifiche o bloccarne il caricamento.

Per disinstallarlo, chiudi la DAW ed elimina `Room-boh.vst3` dalla cartella di installazione.

## Controlli

- **Space:** Mix, Pre-delay, Decay, Depth, Lo Cut e Hi Cut.
- **Early:** Size, Send, Diffusion, Space, Cross, Mod Rate e Mod Depth.
- **Late:** Size, Bass Mult, Bass Xover, High Mult, High Xover, Cross, Mod Rate e Mod Depth.
- **Mode:** Open Hall, Small Studio, Air Bloom, Silk Hall, Warm Loft, Shadow Hall, Night Vault, Orbit, Prism, Nebula, Abyss e Mosaic.
- **Preset:** dodici programmi di fabbrica modificabili.
- **Bypass** e meter stereo RMS/peak.

Mix a 100% per un bus ausiliario. Depth bilancia le riflessioni iniziali e la coda; Decay indica il tempo di decadimento medio approssimativo. Bass Mult e High Mult regolano il decadimento delle rispettive bande. Lo Cut a 0 Hz disattiva il filtro; Cross a 0 rende mono la relativa sezione. Doppio clic per ripristinare il valore iniziale di un controllo; clic sul valore per digitarlo.

## Compatibilità

Sono disponibili configurazioni mono, stereo e ingresso mono con uscita stereo. Il percorso dry ha latenza zero. Tutti i ventitré parametri sono esposti alla DAW e vengono salvati nella sessione. Il caricamento VST3 e l'audio sono stati verificati in un host JUCE locale a 44.1, 48, 96 e 192 kHz; la compatibilità può variare tra DAW.

## Licenza

Il codice e il materiale originali di Room-boh sono concessi sotto **licenza MIT**, riportata in [LICENSE](LICENSE). La MIT permette uso, copia, modifica, distribuzione e vendita, mantenendo l'avviso di copyright e la licenza. La release pubblica contiene il plugin compilato; i sorgenti rimangono privati.

La distribuzione usa la licenza commerciale JUCE Starter. La MIT di Room-boh non si applica ai componenti di terze parti: JUCE e le altre dipendenze conservano i propri termini e avvisi, riportati in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) e nella cartella [licenses](licenses).

Per segnalare problemi, apri una issue indicando DAW, versione macOS, frequenza di campionamento e passaggi per riprodurre il problema.
