# 🛡️ Enti e Standard per la Cybersecurity – Compliance e Sicurezza Tecnica

## 🌐 Organizzazioni Internazionali

### 🇺🇳 ISO / IEC – International Organization for Standardization / International Electrotechnical Commission

Organizzazioni internazionali che sviluppano standard riconosciuti globalmente, in particolare in ambito tecnico e IT.

---

### ✅ ISO/IEC 27000 Series – *Information Security Management Systems (ISMS)*

- **Ambito**: Gestione della sicurezza delle informazioni a livello organizzativo.
- **Standard principali**:
  - **ISO/IEC 27001** – Requisiti per un sistema di gestione della sicurezza delle informazioni.
  - **ISO/IEC 27002** – Codice di buona pratica per i controlli di sicurezza.
  - **ISO/IEC 27005** – Linee guida per la gestione del rischio.
  - **ISO/IEC 27017** – Sicurezza per i servizi cloud.
  - **ISO/IEC 27018** – Protezione dei dati personali nei cloud pubblici.

---

### ✅ ISO/IEC 15408 – *Common Criteria for Information Technology Security Evaluation*

- **Ambito**: Valutazione e certificazione della sicurezza di prodotti IT.
- **Struttura**:
  - **Protection Profiles (PP)**: insiemi di requisiti generali di sicurezza.
  - **Security Targets (ST)**: specifiche di sicurezza del prodotto valutato.

#### 📊 Tabella riassuntiva: EAL vs TOE**                     |
| **EAL (Evaluation Assurance Level)**                  | **Descrizione**                                                       | **TOE (Target of Evaluation)**                            |
| ----------------------------------------------------- | --------------------------------------------------------------------- | --------------------------------------------------------- |
| **EAL1 – Functionally Tested**                        | Verifica funzionale minima. Adatto a prodotti commerciali comuni.     | Il prodotto o sistema da valutare (es. firewall, OS).     |
| **EAL2 – Structurally Tested**                        | Verifica strutturata. Documentazione di progettazione necessaria.     | Deve avere una specifica Security Target (ST).            |
| **EAL3 – Methodically Tested and Checked**            | Revisione metodica. Controllo formale delle procedure di sviluppo.    | Può fare riferimento a un Protection Profile (PP).        |
| **EAL4 – Methodically Designed, Tested and Reviewed** | Verifiche avanzate. Livello di fiducia adatto per ambienti operativi. | TOE con solida documentazione tecnica e test.             |
| **EAL5 – Semi-Formally Designed and Tested**          | Progettazione semi-formale. Maggiore rigore nella documentazione.     | Destinato a sistemi con requisiti di sicurezza elevati.   |
| **EAL6 – Semi-Formally Verified Design and Tested**   | Verifica avanzata della progettazione. Alta sicurezza.                | Usato per dispositivi critici o infrastrutture sensibili. |
| **EAL7 – Formally Verified Design and Tested**        | Massimo livello. Verifica matematica e test esaustivi.                | TOE altamente critico: difesa, aerospazio, crittografia.  |


### ✅ ISO/IEC 9126 – *Software Engineering – Product Quality*

- **Ambito**: Misurazione e gestione della qualità del software.
- **Sostituito da**: **ISO/IEC 25010** – che include caratteristiche come sicurezza, affidabilità, efficienza.

---

### ✅ ISO/IEC 12207 – *Software Life Cycle Processes*

- **Ambito**: Standardizzazione dei processi del ciclo di vita del software (SLC).
- **Contenuto**: Specifica, progettazione, implementazione, testing, manutenzione.

---

### ✅ ISO/IEC 33001 – *Process Assessment Framework (ex-SPICE)*

- **Ambito**: Valutazione della maturità dei processi software.
- **Utilizzo**: audit ISO/IEC 15504, definizione di capability levels.

---

## 🇺🇸 Normative e Standard Statunitensi

### ✅ NIST – *National Institute of Standards and Technology*

Agenzia federale USA responsabile per la definizione di standard tecnologici.

---

### ✅ NIST SP 800 Series – *Special Publications*

**Principali pubblicazioni**:

- **SP 800-53** – *Security and Privacy Controls*.
- **SP 800-171** – *Protezione delle informazioni non classificate*.
- **SP 800-30** – *Risk Assessment*.
- **SP 800-37** – *Risk Management Framework (RMF)*.
- **SP 800-39** – *Gestione del rischio organizzativo*.

---

### 🔍 Approfondimento: NIST SP 800-39 – RMF

Fornisce un framework integrato in **6 step**:

1. **Categorize**: classificazione del sistema e dei dati.
2. **Select**: scelta dei controlli di sicurezza (da SP 800-53).
3. **Implement**: implementazione dei controlli selezionati.
4. **Assess**: verifica dell’efficacia dei controlli.
5. **Authorize**: autorizzazione formale a operare.
6. **Monitor**: monitoraggio continuo del sistema e dei controlli.

---

### ✅ FIPS – *Federal Information Processing Standards*

- **FIPS 140-3**: moduli crittografici.
- **FIPS 199/200**: categorizzazione dei sistemi e requisiti minimi.

---

### ✅ FISMA – *Federal Information Security Modernization Act*

- Obbliga le agenzie federali a:
  - Adottare un ISMS conforme a NIST.
  - Usare SP 800-37 e SP 800-39 per il RMF.
  - Valutare e mitigare i rischi.
- Rende obbligatorio l’uso dei FIPS e NIST SP.

> **Controparte UE**: Direttiva NIS 2 e GDPR

---

### ✅ SCAP – *Security Content Automation Protocol*

Protocollo per l'automazione della gestione di vulnerabilità e configurazioni:
- Include: **CVE**, **CPE**, **OVAL**, **XCCDF**, ecc.

---

### ✅ ITL – *Information Technology Laboratory (di NIST)*

Unità interna a NIST, produce SP 800 e altri standard tecnici.

---

### ✅ SAFECode – *Software Assurance Forum for Excellence in Code*

- Comunità industriale che promuove la **security by design**.
- Fornisce **linee guida per lo sviluppo sicuro**, modelli di SDL.

---

## 📜 Norme Settoriali USA

---

### ✅ SOX – *Sarbanes-Oxley Act (2002)*

- **Ambito**: integrità dei dati finanziari.
- **Impatto IT**: log, auditing, accessi.
- **Controparte UE**: Direttiva 2014/56/UE.

---

### ✅ GLBA – *Gramm-Leach-Bliley Act (1999)*

- Protezione dei dati finanziari.
- **Controparte UE**: GDPR + PSD2.

---

### ✅ HIPAA – *Health Insurance Portability and Accountability Act*

- Protezione dei dati sanitari.
- **Controparte UE**: GDPR – Art. 9.

---

### ✅ HITECH – *Health Information Technology for Economic and Clinical Health Act*

- Estensione di HIPAA per obbligo di notifica e digitalizzazione sanitaria.
- **Controparte UE**: GDPR Art. 33-34.

---

## 💳 PCI Standards – *Payment Card Industry*

### ✅ PCI DSS – *Data Security Standard*

- Obbligatorio per tutti gli attori nella gestione di carte di pagamento.

### ✅ PA DSS – *Payment Application DSS* (ora sostituito da SSF)

### ✅ PTS – *PIN Transaction Security*

---

## 🏦 FFIEC – *Federal Financial Institutions Examination Council*

- Emana:
  - **IT Examination Handbook**
  - **Cybersecurity Assessment Tool (CAT)**
- Regola sicurezza ICT nel settore bancario.
- **Controparte UE**: EBA Guidelines + DORA Regulation.

---

## 🇪🇺 Regolamentazione Europea in Cybersecurity

---

### ✅ GDPR – *General Data Protection Regulation (Regolamento UE 2016/679)*

- **Protezione dei dati personali e dei diritti digitali**.
- **Obblighi**:
  - Registro trattamenti
  - DPIA (valutazioni d’impatto)
  - Notifiche entro 72h
  - Misure tecniche e organizzative (Art. 32)
- **Sanzioni**:
  - Fino a 20 milioni di € o 4% del fatturato globale.
- **Controparte USA**: HIPAA, GLBA, CCPA

---

### ✅ NIS 2 – *Network and Information Security Directive (2022/2555)*

- Successore della Direttiva NIS (2016/1148).
- **Categorie**:
  - **Essenziali**: energia, trasporti, PA, sanità, finanza.
  - **Importanti**: servizi digitali, ICT, tecnologie industriali.
- **Obblighi**:
  - Gestione rischio informatico
  - Sicurezza della supply chain
  - Notifiche entro 24h
  - Responsabilità a livello dirigenziale
- **Sanzioni**:
  - Fino a 10 milioni di € o 2% del fatturato annuo.
- **Coordinamento europeo**:
  - ENISA, CSIRT, EU-CyCLONe

> **Controparte USA**: FISMA + NIST RMF

---

