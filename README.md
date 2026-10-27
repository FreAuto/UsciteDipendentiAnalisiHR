# 👥 Dipendenti che lasciano l'azienda – HR Analytics

Progetto di **Francesco Autorino** – Data Analyst.

🛠️ Strumenti: **Excel · Python · Power BI**

📊 Dati: **1.470 dipendenti**, 35 caratteristiche ciascuno.

⚠️ È un dataset **fittizio** creato dai data scientist di IBM per esercitarsi: il progetto mostra il **metodo**, non i numeri di un'azienda reale.

---

## 🧭 1. Il progetto in breve

❓ **La domanda**: perché i dipendenti lasciano l'azienda, e si può capirlo in anticipo?

Le 6 domande più piccole:

1️⃣ 🏢 Quanti escono, e da quali reparti e ruoli?

2️⃣ ⏰ Straordinari e trasferte spingono ad andare via?

3️⃣ 💰 Stipendio e carriera contano?

4️⃣ 😊 Quanto pesano soddisfazione ed equilibrio vita-lavoro?

5️⃣ 🧑 Qual è il profilo di chi esce?

6️⃣ 🤖 Si può prevedere chi uscirà?

📝 Le risposte complete sono in **02Python/02_CONCLUSIONI.md**.

---

## 🎯 2. I risultati principali

🏢 Esce **1 dipendente su 6** (16%). I **venditori**: 4 su 10.

⏰ Chi fa **straordinari** esce 3 volte di più: **31%** contro 10%.

💰 Nel 25% meno pagato esce il **29%**. Senza stock option il **24%**.

😊 Coinvolgimento basso: **34%**. Equilibrio vita-lavoro pessimo: **31%**.

🧑 Giovani (18-25) che fanno straordinari: esce il **64%**.

🤖 Una regressione logistica prevede le uscite con **AUC 0,82** e trova 7 uscite su 10.

---

## 🛠️ 3. Perché questi strumenti

📗 **Excel**: i dati sono pochi (1.470 righe), perfetti per formule, menu a tendina e grafici.

🐍 **Python**: test statistici (chi-quadro, Mann-Whitney) e un modello di previsione.

📊 **Power BI**: dashboard interattiva con filtri per reparto e fattore.

---

## 🔄 4. Il percorso dei dati

```
GitHub IBM            01_scarica.py           02_pulizia.py               ANALISI
emp_attrition.csv ──► ❌ 1.470 righe ──────► ✅ 1.470 righe ─────────┬──► 📗 Excel
                      35 colonne              29 colonne + 6 fasce     ├──► 🐍 Python
                      (1GrezziNonPuliti)      (2Puliti)                └──► 📊 Power BI
```

🧹 **Cosa ho fatto durante la pulizia**

| Passo | Cosa |
|---|---|
| 0 | Controllo: nessun valore mancante, nessun duplicato |
| 1 | Tolte 3 colonne con un solo valore (EmployeeCount, Over18, StandardHours) |
| 2 | Tolte 3 colonne "tariffa" senza significato chiaro (DailyRate, HourlyRate, MonthlyRate) |
| 3 | Colonne e categorie tradotte in italiano; punteggi 1-4 trasformati in parole (Bassa, Media, Alta, Molto alta) |
| 4 | Create 5 fasce: età, anni in azienda, stipendio (quartili), distanza da casa, anni dall'ultima promozione |

---

## 📁 5. I file in questo repository

| File | A cosa serve |
|---|---|
| `README.md` | Questo file |
| `DESCRIZIONE_GITHUB.md` | Nome, descrizione e topics del repository |
| `00_LEGGIMI.md` (in ogni cartella) | Una spiegazione corta di quella cartella |

### 📂 01Excel

| File | A cosa serve |
|---|---|
| `01_Uscite_Dipendenti_Analisi.xlsx` | 📗 Il file Excel: 405 formule, 0 errori |

📗 **I fogli del file Excel**

| Foglio | Cosa c'è |
|---|---|
| LEGGIMI | Guida, legenda dei colori, fonte |
| Riepilogo | 12 numeri chiave (COUNTIF, AVERAGEIFS) |
| Fattori | Tasso di uscita per 18 fattori (COUNTIFS), colori rosso/verde, 8 grafici |
| Reparti_Ruoli | Uscite per reparto e ruolo, con barre colorate e grafico |
| Profilo_Rischio | ⭐ Scegli un profilo dai menu a tendina (celle gialle) e vedi il suo rischio |
| Dati | I 1.470 dipendenti in una tabella Excel con filtri |
| Controllo | 22 controlli automatici: devono essere tutti ✅ |

### 📂 02Python

| File | A cosa serve |
|---|---|
| `01_analisi_uscite_dipendenti.ipynb` | 📓 Il notebook con tutta l'analisi, già eseguito |
| `02_CONCLUSIONI.md` | ✅ Le risposte alle 6 domande e le azioni consigliate |

### 📂 03PowerBi

| File | A cosa serve |
|---|---|
| `01_UsciteDipendentiDashboard.zip` | ⭐ **La dashboard**: estrai lo zip e apri `UsciteDipendenti_Dashboard.pbip` con Power BI Desktop |
| `02_UsciteDipendenti_Dashboard.pdf` | 📄 Il PDF della dashboard |
| `03_misure_DAX.txt` | 🧮 Le misure DAX usate nella dashboard |

📊 **Le 6 pagine della dashboard**

1. **Il quadro generale**: 6 numeri chiave, uscite per ruolo, reparto e livello
2. **Lavoro e soldi**: straordinari, trasferte, stipendio, stock option
3. **Le persone**: età, anzianità, equilibrio vita-lavoro, coinvolgimento, età × straordinari
4. **Tutti i fattori**: scegli un fattore e guarda tutti i suoi valori
5. **Il modello**: cosa spinge a uscire e cosa trattiene
6. **Conclusioni**

---

## 📦 6. Dati e script

📌 Qui ci sono solo i **risultati**: analisi, query, notebook, file Excel e dashboard.

📥 I dati si possono riscaricare dalla fonte (link più sotto).

🐍 Gli script Python di raccolta e pulizia dei dati sono disponibili su richiesta.

---

## ⚠️ 7. Limiti

📌 Dataset fittizio creato da IBM per esercitarsi.

📌 Una sola fotografia nel tempo: non vediamo come cambiano le persone negli anni.

📌 Non sappiamo se le uscite sono dimissioni o licenziamenti.

📌 Il modello mostra **legami**, non cause sicure.

---

## 🔗 8. Da dove arrivano i dati (link)

| Fonte | Cosa ho preso | Link |
|---|---|---|
| IBM – repository GitHub "employee-attrition-aif360" | Il dataset IBM HR Analytics Employee Attrition | https://github.com/IBM/employee-attrition-aif360 |
| File scaricato | Il CSV usato da `01_scarica.py` | https://raw.githubusercontent.com/IBM/employee-attrition-aif360/master/data/emp_attrition.csv |

📅 Dati scaricati il **25 ottobre 2026**.

---

## 🪜 9. Tutti i passaggi fatti, in ordine

1️⃣ **Scelta del progetto**: un tema HR, molto richiesto nelle aziende, con dati piccoli adatti a Excel.

2️⃣ **Domande**: ho fissato le 6 domande.

3️⃣ **Raccolta** (`01_scarica.py`): ho scaricato il CSV dal GitHub di IBM.

4️⃣ **Controllo**: nessun dato mancante o duplicato; 3 colonne costanti e 3 senza significato chiaro.

5️⃣ **Pulizia** (`02_pulizia.py`): colonne tolte, traduzione in italiano, punteggi in parole, 5 fasce.

6️⃣ **Tabelle di analisi**: tasso di uscita per 18 fattori e per reparto/ruolo.

7️⃣ **Excel**: riepilogo, fattori con grafici, profilo a rischio con menu a tendina, controlli automatici; ricalcolato con 0 errori.

8️⃣ **Python**: 8 grafici, test chi-quadro e Mann-Whitney, regressione logistica (75% per allenare, 25% per provare), AUC e pesi dei fattori.

9️⃣ **Power BI**: dashboard di 6 pagine con filtri, aperta e controllata in Power BI Desktop.

🔟 **Conclusioni**: risposte alle 6 domande e 5 azioni consigliate in `02Python/02_CONCLUSIONI.md`.
