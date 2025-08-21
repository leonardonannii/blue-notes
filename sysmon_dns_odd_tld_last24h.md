# Detection — Sysmon ID 22 (DnsQuery) · TLD insoliti (ultime 24h)

**Scopo**: rilevare richieste DNS verso TLD comuni in abuso (.top, .ru, .xyz, .click, .info).

**Comando**
```powershell
Get-WinEvent -FilterHashtable @{
  LogName='Microsoft-Windows-Sysmon/Operational'; Id=22;
  StartTime=(Get-Date).AddDays(-1)
} | Where-Object { $_.Message -match '\.(top|ru|xyz|click|info)\b' } |
  Measure-Object
