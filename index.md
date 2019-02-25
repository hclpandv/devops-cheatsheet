# devops-cheatsheet
[Periodic table of devops tools](periodic-table-of-devops-tools-v3.pdf)

### # Executing Remote Scripts from github
```bash
#!/bin/bash
curl -sSL https://raw.githubusercontent.com/hclpandv/bash-learning/master/colors.sh | bash
```
```powershell
# PowerShell
iex ((New-Object System.Net.WebClient).DownloadString('https://raw.githubusercontent.com/hclpandv/devops-cheatsheet/master/demo.ps1'))
```
#### # VIM Learning  
[https://openvim.com/](https://openvim.com/)

### # Git Tutorials
```bash
# Create an Alias for nicely decorated graphed Log
alias git-graph="git log --all --decorate --oneline --graph"
```
[https://www.atlassian.com/git/tutorials](https://www.atlassian.com/git/tutorials)  
[Git CheatSheet](atlassian-git-cheatsheet.pdf)

#### # Vagrant Learning
[http://bertvv.github.io/notes-to-self/2015/10/05/one-vagrantfile-to-rule-them-all/](http://bertvv.github.io/notes-to-self/2015/10/05/one-vagrantfile-to-rule-them-all/)

#### # Powershell Learning
[http://www.theochem.ru.nl/~pwormer/teachmat/PS_cheat_sheet.html](http://www.theochem.ru.nl/~pwormer/teachmat/PS_cheat_sheet.html)

#### # Ansible Learning
* Ansible setup on Windows 10 - WSL (ubuntu)  
[https://www.frostbyte.us/ansible-integrated-development-environment-setup-on-windows/](https://www.frostbyte.us/ansible-integrated-development-environment-setup-on-windows/)



