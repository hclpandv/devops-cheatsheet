#### General DevOps Learning
. [Periodic table of devops tools](periodic-table-of-devops-tools-v3.pdf)

-------------------------------------------
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
-------------------------------------------
#### VIM Learning  
. [https://openvim.com/](https://openvim.com/)

-------------------------------------------
#### Git Learning
. Git Alias

```bash
# Create an Alias for nicely decorated graphed Log
alias git-graph="git log --all --decorate --oneline --graph"
```
. [https://www.atlassian.com/git/tutorials](https://www.atlassian.com/git/tutorials)  
. [Git cheat sheet](atlassian-git-cheatsheet.pdf)

-------------------------------------------
#### Vagrant Learning
. [Sample](sample-vagrant-file.md) `Vagrantfile`  
. `vagrant` Basic commamd-Line  

```bash
# Spin up the Vagrant VM
vagrant up
vagrant --no-provision
# Provision Only
vagrant provision
# halt - Stops he vagrant machine | destroy - Stops and deletes all traces of the vagrant machine 
# suspend - Suspends the vagrant machine. saves current state.
# resume - Resumes a suspended machine | reload - restarts and loads new Vagrantfile config
vagrant destroy -f # -f for force i.e. no confirmation msg
vagrant destroy <VM Name> # as defined in Vagrantfile
```  
. [http://bertvv.github.io/notes-to-self/2015/10/05/one-vagrantfile-to-rule-them-all/](http://bertvv.github.io/notes-to-self/2015/10/05/one-vagrantfile-to-rule-them-all/)

-------------------------------------------
#### Ansible Learning
. [Sample](sample-ansible-playbook.md) `ansible-playbook`  
. `ansible` Basic Command-line  

```bash
# Basic ping module
ansible localhost -m ping
# Use -a to provide the value of parameters
ansible localhost -m debug -a "msg='Msg from Ansible...'"
# Get the details of the target server (Complete facts). Usefull for hacks
ansible windows -i inventory_file -m setup
# Execute a playbook
ansible-playbook -i inventory_file ./win-test-playbooks/win_ping.yml
```
. Ansible setup on Windows 10 - WSL (ubuntu) 
. https://serversforhackers.com/c/an-ansible-tutorial (a good blog)  
. [https://www.frostbyte.us/ansible-integrated-development-environment-setup-on-windows/](https://www.frostbyte.us/ansible-integrated-development-environment-setup-on-windows/)

----------------------------------------------
#### YAML Learning
https://learnxinyminutes.com/docs/yaml/  
. [YAML CheatSheet](yaml-cheatsheet.md) 
