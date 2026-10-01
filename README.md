# Listino Piante Interattivo

Listino prezzi per vivai, pensato per il telefono: il cliente cerca le piante, le ordina per
dimensione, crescita, ombra o frutto, sceglie le quantità e vede subito il totale con IVA.
L'ordine arriva al vivaio su WhatsApp o per email, con un link che riapre la stessa selezione.

È un solo file (`index.html`): nessun server, nessun database, nessun costo di gestione.

## Personalizzare per un nuovo vivaio

Tutto si modifica in `index.html`, nella parte `<script>`:

1. **`CONFIG`**: nome del vivaio, sottotitolo, aliquota IVA, formati e prezzi, generi da
   evidenziare, numero WhatsApp (con prefisso, es. `393331234567`) ed email per gli ordini.
   Se più listini stanno sullo stesso dominio, dai a ciascuno un `id` diverso.
2. **`PLANTS`**: una riga per pianta. `c1`, `c3`, `c20` (o le chiavi scelte in
   `CONFIG.formati`) valgono `1` se il formato è disponibile, `0` se no. `h` = altezza in
   metri, `g` = crescita (1-3), `o` = ombra (1-3), `f` = frutto (0-2).
3. **`LATIN`**: nome scientifico di ogni pianta, usato per la foto e la scheda da Wikipedia.

Se cambi solo i prezzi, i link e le selezioni salvate dai clienti restano validi. Se aggiungi
o togli piante, i vecchi link vengono ignorati, così non finiscono sulle piante sbagliate.

## Pubblicare

Basta caricare `index.html` su qualunque hosting statico (GitHub Pages, Netlify, Cloudflare
Pages) o sul sito del vivaio. Un indirizzo diverso per ogni cliente.

## Foto e testi

Foto e descrizioni vengono da Wikipedia / Wikimedia Commons. Sotto ogni scheda compaiono
autore e licenza, come richiesto da quelle licenze. Per una versione premium si possono
sostituire con le foto del vivaio.
