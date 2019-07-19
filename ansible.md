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
. https://serversforhackers.com/c/an-ansible-tutorial   
. [https://www.frostbyte.us/ansible-integrated-development-environment-setup-on-windows/](https://www.frostbyte.us/ansible-integrated-development-environment-setup-on-windows/)
