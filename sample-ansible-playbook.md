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
