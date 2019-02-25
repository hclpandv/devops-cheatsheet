. Playbook for Unix

```yml
---
- name: Viki test playbook
  hosts: localhost
  #become: true
  #become_method: sudo
  vars:
      #repository_url: git@github.com:valet2you/DemoGitTest.git
      #repository_path: /var/www/html
      #key_file: /root/.ssh/id_rsa.github
      #project_name: viki-devops-test
      playbook_dir: "{{ playbook_dir }}" # Defined by Ansible itself
      files_dir: "{{ playbook_dir }}/files/"
  tasks:
    - name: setup a cron job
      cron:
        name: "Clear Cache"
        #user: "root"
        #minute: 1
        #hour: 0
        job: "echo Hello >> {{ files_dir }}cron_output.log"
        state: present
        #become: true
    - name: setup another cron job
      cron:
        name: another jon
        job: "sleep 5; echo Another Hello >> {{ files_dir }}cron_output.log"
        state: present 
```

. Playbook for Windows

```yml
---
- name: Install various softwares to setup windows 10x 64 DevOps workstation
  hosts: windows
  #become: yes
  #become_user: Administrator
  #become_user: SYSTEM
  #become_method: runas
  vars:
      playbook_dir: "{{ playbook_dir }}" # Defined by Ansible itself
      files_dir: "{{ playbook_dir }}/files/"
  tasks:
    - name: Install chocolatey to be able to install packages from repository
      win_chocolatey:
        name: chocolatey
        state: present
      become: yes
      become_user: SYSTEM
      become_method: runas

    - name: Install multiple chocolatey packages
      win_chocolatey:
        name: "{{ packages }}"
        state: present
      vars:
        packages:
        - git
        - virtualbox
        - vagrant
        - conemu
        - insomnia-rest-api-client
      become: yes
      become_user: SYSTEM
      become_method: runas

    - name: Uninstall multiple packages
      win_chocolatey:
        name:
        - Nosoftware1
        - Nosoftware2
        - Nosoftware3
        state: absent
      become: yes
      become_user: SYSTEM
      become_method: runas
```
