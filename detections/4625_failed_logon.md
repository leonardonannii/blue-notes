# Detection: Event ID 4625 (Failed Logon)

## Description
Windows Security Log records failed logon attempts.  
Useful for detecting brute-force and password spraying.

## Command used
```powershell
Get-WinEvent -FilterHashtable @{
  LogName='Security'; Id=4625;
  StartTime=(Get-Date).AddDays(-1)
} | Measure-Object

Count : 2
