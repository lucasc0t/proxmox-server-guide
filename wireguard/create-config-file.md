# Creazione e Uso di un File `.conf` per WireGuard

Questa guida spiega come creare un file `.conf` per un nuovo client WireGuard utilizzando PiVPN e come configurarlo su dispositivi mobili o computer.

---

## 1️⃣ Creare un File `.conf` per WireGuard

### Passaggi:

1. **Accedere alla VM o LXC**  
   - Utilizza [PuTTY](https://www.putty.org/) o un altro servizio SSH per connetterti alla macchina.  
   - Accedi inserendo le credenziali corrette.

2. **Visualizzare le opzioni di PiVPN**  
   - Una volta collegati, esegui:  
     ```bash
     pivpn --help
     ```
   - Verrà mostrata una lista di comandi utili. 

3. **Aggiungere un nuovo client**  
   - Per creare un nuovo file `.conf`, esegui:  
     ```bash
     pivpn -a
     ```
   - Quando richiesto, digita un nome univoco per il nuovo client e premi **Invio**.  
   - Dopo la conferma, verrà mostrato un messaggio che indica la directory in cui il file `.conf` è stato salvato.

---

## 2️⃣ Usare il File `.conf`

### Per dispositivi mobili (con fotocamera)
1. **Scaricare l'app WireGuard**  
   - Su iOS: [WireGuard su App Store](https://apps.apple.com/it/app/wireguard/id1441195209?l=en-GB)  
   - Su Android: [WireGuard su Play Store](https://play.google.com/store/search?q=wireguard&c=apps&hl=it)

2. **Generare il QR Code del file `.conf`**  
   - Nel terminale, esegui:  
     ```bash
     pivpn -qr
     ```
   - Verrà mostrata una lista di client.  
   - Seleziona il client desiderato per visualizzare il QR Code.

3. **Scansionare il QR Code**  
   - Apri l'app WireGuard e utilizza la funzione di scansione del QR Code per configurare il dispositivo.

---

### Per dispositivi senza fotocamera
1. **Copiare il file `.conf` sul computer**  
   - Apri il **Prompt dei Comandi** su Windows (Win + `cmd`).  
   - Esegui il comando seguente, sostituendo i parametri con i tuoi dati:  
     ```bash
     pscp.exe <username>@<ip-address>:</path/to/folder/file.conf> </destination/path/>
     ```
   - **Esempio**:  
     ```bash
     pscp.exe wg@192.168.1.55:/home/wg/configs/file.conf d:\
     ```

2. **Installare `pscp` (se necessario)**  
   - Se il comando `pscp` non è disponibile, installalo seguendo le istruzioni di [PuTTY Download Page](https://www.putty.org/).

3. **Configurare WireGuard**  
   - Scarica l'app desktop WireGuard: [WireGuard Install](https://www.wireguard.com/install/).  
   - Importa il file `.conf` appena trasferito.

---

🎉 **Complimenti!** Ora il client WireGuard è configurato e pronto all’uso.
