# Listino Piante Interattivo

Listino di piantine pensato per il telefono: chi richiede cerca le specie (anche per nome
latino), le filtra e le ordina per altezza, crescita, ombra o frutti, sceglie le quantità per
formato e vede subito il totale con IVA. La richiesta arriva al vivaio per email (o WhatsApp)
già completa di dati del richiedente, piante, prezzi e un link che riapre la stessa selezione.

È un solo file (`index.html`): nessun server, nessun database, nessun costo di gestione.

## Personalizzare

Tutto si modifica in `index.html`, nella parte `<script>`:

1. **`CONFIG`**: nome e luogo del vivaio, aliquota IVA, formati e prezzi, email e WhatsApp per
   le richieste, vivai tra cui scegliere il ritiro. Se più listini stanno sullo stesso dominio,
   dai a ciascuno un `id` diverso.
2. **`CONFIG.demo`**: copertina animata all'apertura, nota "demo non ufficiale" e `[DEMO]`
   nell'oggetto delle email. Con `attiva: false` resta il listino definitivo.
3. **`PLANTS`**: una riga per specie. `c1`, `c3`, `c20` (le chiavi di `CONFIG.formati`) valgono
   `1` se il formato è disponibile, `0` se no. `h` = altezza in metri, `g` = crescita (1-3),
   `o` = ombra (1-3), `f` = frutti (0-2).
4. **`LATIN`**: nome scientifico di ogni specie, usato per foto e scheda da Wikipedia.
   `LATIN_SHOW` lo sostituisce nella pagina quando serve più precisione (es. una cultivar).

Se cambi solo i prezzi, i link e le selezioni salvate restano validi. Se aggiungi o togli
specie, i vecchi link vengono ignorati, così non finiscono sulle piante sbagliate.

## Pubblicare

Basta caricare `index.html` su un hosting statico (GitHub Pages, Netlify, Cloudflare Pages) o
sul sito del vivaio.

## Foto e testi

Foto e descrizioni vengono da Wikipedia / Wikimedia Commons. Nella scheda di ogni specie
compaiono autore e licenza della foto, come richiesto da quelle licenze.
