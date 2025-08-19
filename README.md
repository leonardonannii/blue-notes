# blue-notes — Leonardo Nanni
Obiettivo: diventare **Junior SOC Analyst (Blue Team)** su ambiente Windows. Qui raccolgo lab, query e playbook.

## Stack del lab (inizio)
- Windows Event Log (Security)
- Sysmon (in arrivo) → ProcessCreate (ID 1), NetworkConnect (ID 3), DnsQuery (ID 22)
- (Prossimo step: Wazuh come SIEM)

## Evidenze — Day 1
- Event ID **4625** (Logon fallito, ultime 24h): **__N4625__**

## Query iniziali
- Windows Security 4625 (conteggio ultime 24h)
- Sysmon – PowerShell eseguito (ID 1) *(in arrivo)*
- Sysmon – DNS verso TLD insoliti (ID 22) *(in arrivo)*

## Playbook
- Phishing — triage iniziale (v1.0)

## Prossimi passi
- Installare Sysmon e salvare 2–3 eventi d’esempio
- Aggiungere 2 detection con spiegazione e falsi positivi
