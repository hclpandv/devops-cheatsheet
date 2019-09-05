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
```bash
# Adhoc commands
# Try mulipls times and observe the parrelism
ansible viki_managed_servers -a "hostname"
ansible app -a "hostname"
ansible db -a "hostname"
ansible viki_managed_servers -a "df -h"
ansible viki_managed_servers -a "free -m"
ansible viki_managed_servers -a "date"

# Details of ansible facts | setup is a module
ansible viki_managed_servers -m setup

# Configure app servers | Install python and django 
# `-b` is become sudo
ansible app -b -m yum -a "name=MySQL-python state=present"
ansible app -b -m yum -a "name=MySQL-python state=present"
ansible app -b -m yum -a "name=python-setuptools state=present"
ansible app -b -m easy_install -a "name=django<2 state=present"
ansible app -a "python -c 'import django; print django.get_version()'"

# Configure db server | Install mariadb
ansible db -b -m yum -a "name=mariadb-server state=present"
ansible db -b -m service -a "name=mariadb state=started enabled=yes"
ansible db -b -a "iptables -F"
ansible db -b -a "iptables -A INPUT -s 192.168.60.0/24 -p tcp -m tcp --dport 3306 -j ACCEPT"

ansible db -b -m yum -a "name=MySQL-python state=present"
ansible db -b -m mysql_user -a "name=django host=% password=12345 priv=*.*:ALL state=present"

```


. Ansible setup on Windows 10 - WSL (ubuntu)  
. https://serversforhackers.com/c/an-ansible-tutorial   
. [https://www.frostbyte.us/ansible-integrated-development-environment-setup-on-windows/](https://www.frostbyte.us/ansible-integrated-development-environment-setup-on-windows/)
