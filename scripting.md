#### Scripting Learning
. Executing Remote Scripts from github

```bash
#!/bin/bash
curl -sSL https://raw.githubusercontent.com/hclpandv/bash-learning/master/colors.sh | bash
```
```powershell
# PowerShell
iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/hclpandv/devops-cheatsheet/master/demo.ps1'))
```
. [http://www.theochem.ru.nl/~pwormer/teachmat/PS_cheat_sheet.html](http://www.theochem.ru.nl/~pwormer/teachmat/PS_cheat_sheet.html)

. PowerShell Alias

```powershell
Function Get-ExeLocation ($ExeName) { return (Get-Command $ExeName).Source }
Set-Alias -Name which -Value Get-ExeLocation
```
