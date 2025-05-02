# tvproxy

Ecco il README.md completamente formattato per essere facilmente copiabile e incollabile.


---

📜 M3U8 Proxy Dockerizzato

🚀 M3U8 Proxy è un server proxy basato su Flask e Requests che consente di:

Scaricare e modificare flussi M3U/M3U8.

Proxyare i segmenti .TS, mantenendo gli header personalizzati.

Superare restrizioni di accesso (es. Referer, User-Agent).

Dockerizzarlo per l'uso su qualsiasi macchina o server.



---

🔧 Installazione e Uso con Docker

1️⃣ Clonare il Repository

git clone https://github.com/tuo-username/m3u8-proxy.git
cd m3u8-proxy

2️⃣ Costruire l'Immagine Docker

docker build -t m3u8-proxy .

3️⃣ Avviare il Container

docker run -d -p 7680:7680 --name m3u8-proxy m3u8-proxy

4️⃣ Verificare che il Proxy sia Attivo

curl http://localhost:7680/

Dovresti ricevere una risposta tipo:

Not Found
The requested URL was not found on the server. If you entered the URL manually please check your spelling and try again.

---


📌 Gestione del Container Docker

🔹 Controllare i log del container

docker logs -f m3u8-proxy

🔹 Fermare il container

docker stop m3u8-proxy

🔹 Riavviare il container

docker start m3u8-proxy

🔹 Rimuovere il container

docker rm -f m3u8-proxy


---

📌 Deployment su un Server

Se vuoi eseguire il proxy su un server remoto (es. VPS con Ubuntu), segui questi passi:

1️⃣ Installa Docker su Ubuntu

sudo apt update && sudo apt install -y docker.io

2️⃣ Copia i file sul server

Se sei su Windows, usa WinSCP o scp:

scp -r m3u8-proxy user@server-ip:/home/user/

3️⃣ Accedi al server e avvia il container

ssh user@server-ip
cd /home/user/m3u8-proxy
docker build -t m3u8-proxy .
docker run -d -p 7680:7680 --name m3u8-proxy m3u8-proxy

Ora il proxy sarà raggiungibile da qualsiasi dispositivo all’indirizzo:

http://server-ip:7680/proxy/m3u?url=<URL_M3U8>

ricorda non proxare la lista completa ma dento la lista prima di ogni url m3u8 metti http://server-ip:7680/proxy/m3u?url=<URL_M3U8>

se hai headers diversi allora metti http://server-ip:7680/proxy/m3u?url=<URL_M3U8><HEADERS_PERSONALIZZATO>

esempio <HEADERS_PERSONALIZZATO>

&header_user-agent=Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/133.0.0.0 Safari/537.36&header_referer=https://ilovetoplay.xyz/&header_origin=https://ilovetoplay.xyz


---

🎉 Conclusione

✔ Supporta .m3u e .m3u8 automaticamente
✔ Mantiene e inoltra gli header HTTP per l'autenticazione
✔ Supera restrizioni basate su Referer, User-Agent, Origin
✔ Funziona su qualsiasi player IPTV
✔ Dockerizzato per un facile deployment

🚀 Ora puoi usare il tuo proxy per guardare flussi M3U8 senza restrizioni! 🚀




