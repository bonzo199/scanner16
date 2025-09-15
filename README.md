# Scanner 16 (Web App)
Pagina singola per leggere QR/DataMatrix/1D via camera del telefono o PC.
Accetta SOLO blocchi da **16** caratteri (alfanumerici, uppercase); anche concatenati (multipli di 16).

## Pubblicazione rapida (GitHub Pages)
1. Crea un nuovo repository, es. `scanner16`.
2. Aggiungi il file `scanner.html` in root e fai commit.
3. `Settings` → `Pages` → _Build and deployment_ = **Deploy from branch**, Branch **main**, folder **/**.
4. Apri l’URL pubblicato (es. `https://USERNAME.github.io/scanner16/scanner.html`).

> Alternativa: Netlify / Vercel / Cloudflare Pages (drag&drop della cartella o collegamento al repo).

## Uso dentro Telegram (WebApp del bot)
- Nel bot, mostra un bottone `InlineKeyboardButton(web_app=WebAppInfo(url=HTTPS_URL))` che apre `scanner.html`.
- In pagina, se è aperta in Telegram, `tg.sendData(JSON.stringify({ codes:[...] }))` rimanda i codici al bot.
- HTTPS è obbligatorio.

## Endpoint facoltativo (fuori Telegram)
- Compila i campi `endpoint` e `token` e premi **Invia** per POSTare `{ codes: [...] }` al tuo server.

## Note
- Permessi camera: assicurarsi che il browser mobile consenta l’accesso.
- iOS: solo su HTTPS e con interazione utente (già previsto dai pulsanti).
