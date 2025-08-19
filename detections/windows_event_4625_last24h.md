# Detection — Windows Security 4625 (Logon Failed) – ultime 24h

**Scopo:** contare e monitorare i tentativi di accesso falliti per individuare possibili brute-force o password spraying.

**Comando (PowerShell):**
```powershell
Get-WinEvent -FilterHashtable @{
  LogName='Security'; Id=4625; StartTime=(Get-Date).AddDays(-1)
} | Measure-Object
