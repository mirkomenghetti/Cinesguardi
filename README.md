# Cinesguardi — Archivio delle presentazioni

Sito statico per pubblicare l'archivio delle presentazioni di Cinesguardi.
Funziona su **GitHub Pages** (o qualsiasi server web). È composto da tre cose:

```
index.html        → il sito (homepage + schede). Non va modificato per aggiungere film.
films.json        → i dati di tutti i film (numero, titolo, testo, ecc.)
locandine/        → le immagini, una per film, nominate col numero: 940.jpg, 939.jpg, ...
```

## Come pubblicarlo su GitHub Pages (da zero)

1. Crea un nuovo repository su GitHub (es. `cinequarantena`).
2. Carica **tutto il contenuto di questa cartella** nel repository:
   `index.html`, `films.json`, la cartella `locandine/` e il file `.nojekyll`.
   (Puoi trascinarli nella pagina del repo con "Add file → Upload files".)
3. Vai in **Settings → Pages**.
4. Alla voce "Branch" scegli `main` e cartella `/ (root)`, poi **Save**.
5. Dopo un minuto il sito sarà online all'indirizzo:
   `https://TUONOME.github.io/cinequarantena/`

> Nota: apri sempre il sito tramite questo indirizzo (https), **non** facendo
> doppio click su `index.html` dal computer: il caricamento dei dati richiede un server.

## Come aggiungere un nuovo film

1. Metti la sua locandina in `locandine/`, nominandola col numero del film: es. `941.jpg`.
2. Apri `films.json` e aggiungi un blocco come questo (in cima alla lista):

```json
{
 "n": 941,
 "titolo": "Titolo del film",
 "regista": "Nome Regista",
 "lingua": "lingua",
 "sottotitoli": "italiano",
 "anno": 2025,
 "durata": "100 min",
 "file": "941.jpg",
 "presentazione": [
   "Primo paragrafo...",
   "Secondo paragrafo..."
 ],
 "trailer": "ID_YOUTUBE",
 "data_pub": "24 giugno 2026"
}
```

3. Salva e fai commit. Il sito si aggiorna da solo.

### Formattazione del testo nelle presentazioni
Dentro i paragrafi di `"presentazione"` puoi usare:
- `<em>...</em>` per il corsivo (titoli di film citati);
- `<em class="filmtitle"><strong>...</strong></em>` per il titolo del film della scheda (corsivo + grassetto);
- i riferimenti scritti come `[Archivio N. 685]` diventano automaticamente **link cliccabili**
  quando quel film è presente in archivio.

### Trailer
Nel campo `"trailer"` va solo l'ID del video YouTube (la parte dopo `v=`).
Esempio: per `https://www.youtube.com/watch?v=tXlBt6toQiY` scrivi `"trailer": "tXlBt6toQiY"`.
Lascia `""` se non c'è trailer.
