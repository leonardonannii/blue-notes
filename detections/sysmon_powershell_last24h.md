# Detection — Sysmon ID 1 (ProcessCreate) · PowerShell (ultime 24h)

**Scopo**: monitorare l’uso di `powershell.exe` (spesso abusato da attaccanti).

**Comando**
```powershell
Get-WinEvent -FilterHashtable @{
  LogName='Microsoft-Windows-Sysmon/Operational'; Id=1;
  StartTime=(Get-Date).AddDays(-1)
} | Where-Object { $_.Message -match 'Image:.*\\powershell\.exe' } |
  Measure-Object
