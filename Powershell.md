# PowerShell

#### Propriétés d'un fichier ou dossier
```javascript
Get-ItemProperty -Path '.\Sentinel - Acquisition.exe' | Format-list -Property * -Force
```

#### Calcul des hash pour les fichiers d'un dossier
```
Get-ChildItem -File -Recurse | Select Name,FullName,@{N='FileHash';E={(Get-FileHash $_.PSPath).Hash}} | ConvertTo-Json -Compress > list.txt
```