# Stato

**App: https://zaphod95.github.io/stato/**

Una pagina web che riassume un file Excel con le finanze personali: patrimonio, conti, entrate e uscite, spese per categoria e il loro andamento mensile, investimenti. Funziona sia sul computer sia sul cellulare.

## Privacy

- La pagina **non contiene dati**: si apre il file `.xlsx` dal dispositivo e lo legge solo il browser.
- Una Content Security Policy (`connect-src 'none'`) impedisce alla pagina qualsiasi invio in rete.
- Non viene salvato nulla: chiudendo la scheda i dati spariscono.
- Il `.gitignore` esclude i file `.xlsx`, `.xls` e `.csv`, così nessun dato può finire nel repository.

L'unica risorsa esterna è la libreria [SheetJS](https://sheetjs.com/), che serve a leggere il file Excel e viene caricata da cdnjs.

## Stima del fondo pensione

Il fondo pensione è registrato nel file solo da agosto 2026. Per i mesi precedenti la pagina ne stima il valore: ipotizza versamenti mensili costanti dall'avvio (luglio 2023) con un rendimento annuo costante e li calibra sul primo valore reale. Per modificare le ipotesi basta cambiare `PENSION` in `index.html`.
