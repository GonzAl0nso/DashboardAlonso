# Dashboard Alonso — Peralba Health Care

Dashboard amministrativa per la gestione di contabilità, fiscalità e analitiche.
Ospitata su **GitHub Pages**: https://gonzal0nso.github.io/DashboardAlonso/

---

## Struttura del repo

```
Dashboard Alonso/
├── index.html          ← Dashboard principale (tutto in un file)
├── Targhe.csv          ← Flotta veicoli (aggiornare qui)
├── analitica auto .csv ← Export analitica dal gestionale (aggiornare qui)
└── .gitignore
```

---

## Come aggiornare i dati

### Aggiornare la flotta veicoli (Targhe.csv)
1. Apri `Targhe.csv` con Excel o Notepad
2. Modifica le righe (separatore: `;`)
3. Salva, poi esegui:
```bash
git add Targhe.csv
git commit -m "Aggiornamento flotta"
git push
```
La dashboard si aggiorna automaticamente al prossimo caricamento.

### Aggiornare l'analitica spese (analitica auto .csv)
1. Esporta il file dal gestionale contabile
2. Copialo in questa cartella (sovrascrivendo quello precedente)
3. Esegui:
```bash
git add "analitica auto .csv"
git commit -m "Aggiornamento analitica [mese]"
git push
```
I grafici si aggiornano automaticamente.

---

## Fix del Worker OCR (da fare una volta sola)

Il Worker OCR su Cloudflare ha bisogno di un aggiornamento per gestire il CORS.

1. Vai su: https://dash.cloudflare.com → Workers & Pages → **ocr**
2. Clicca **Modifica codice** (o "Edit code")
3. Cancella tutto il codice esistente
4. Incolla il contenuto del file `ocr-worker-fix.js`
5. Clicca **Deploy**

---

## Setup GitHub Pages (una volta sola)

1. Vai su https://github.com/GonzAl0nso/DashboardAlonso/settings/pages
2. Sotto **Source**, seleziona **Deploy from a branch**
3. Branch: `main`, cartella: `/ (root)`
4. Clicca **Save**
5. Dopo ~2 minuti la dashboard è disponibile all'URL sopra

---

## Comandi Git rapidi

```bash
# Prima volta (clona il repo)
git clone https://github.com/GonzAl0nso/DashboardAlonso.git

# Aggiornamento standard
git add -A
git commit -m "Aggiornamento dati"
git push
```
