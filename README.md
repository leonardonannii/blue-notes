# SOC Lab Journey

Questo repo documenta il mio percorso pratico verso il ruolo di **SOC Analyst (Blue Team)**.  
Ogni giorno aggiungo evidenze reali dal mio lab in VM, con spiegazioni e playbook di analisi.

---

## 📅 Giorni di evidenze

### 🔹 Day 1
- **Event ID 4625 (Failed Logon)**  
  - Count (last 24h): **2**  
  - Why it matters: utile per individuare brute-force o password spraying.  
  - Fields to check: `AccountName`, `LogonType` (2/3/10), `Source Network Address (IP)`.

---

### 🔹 Day 2
- **Sysmon ID 1 — ProcessCreate (PowerShell, 24h): N_PS**  
  - Why it matters: molte campagne automatizzano download/esecuzioni via PowerShell (LoLBins).  
  - Check: `CommandLine`, `ParentImage`, utente.  

- **Sysmon ID 22 — DnsQuery (TLD insoliti, 24h): N_DNS**  
  - Why it matters: possibile indicatore di C2 o domini maliziosi.  
  - Check: `QueryName`, processo chiamante (`Image`), utente.  

#### 🛡️ Mini scenario (Word → PowerShell → DNS sospetto)
- `WINWORD.EXE` apre `POWERSHELL.EXE` (Sysmon ID 1).  
- PowerShell fa query DNS verso `ajd92jd92.top` (Sysmon ID 22).  
- In parallelo l’attaccante prova login forzati (4625).  
- Possibile attacco: **Phishing con macro + brute force + C2 communication**.
