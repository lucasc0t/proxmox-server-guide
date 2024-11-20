# Aggiornamento di Plex Media Server

Ecco come aggiornare Plex Media Server sulla tua macchina.

## Passaggi
1. **Connettersi alla macchina via SSH**  
   Usa un client SSH come [PuTTY](https://www.putty.org/) per comodità.  
   Accedi con le tue credenziali.

2. **Scaricare il file .deb dal sito di Plex**  
   - Vai alla pagina di download ufficiale di Plex:  
     [Plex Media Server Downloads](https://www.plex.tv/media-server-downloads/?cat=computer&plat=linux#plex-media-server).  
   - Seleziona il pacchetto in base al sistema operativo in uso.  
   - Copia il link del file .deb.

3. **Scaricare il file sulla macchina**  
   - Nel terminale, esegui il comando seguente, sostituendo `<link-appena-copiato>` con il link che hai copiato:  
     ```bash
     wget <link-appena-copiato>
     ```

4. **Installare l’aggiornamento**  
   - Una volta completato il download, esegui il comando seguente:  
     ```bash
     sudo dpkg -i <nome-del-file-appena-scaricato>
     ```

5. **Riavviare il servizio** (opzionale ma consigliato)  
   - Esegui il comando:  
     ```bash
     sudo systemctl restart plexmediaserver
     ```

6. **Fatto!**  
   Plex Media Server dovrebbe essere ora aggiornato all’ultima versione.

