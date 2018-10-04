## Nevalabs Infrastructure as Code
Contains Ansible Roles for common infrastructure tasks.
- VM generations on Proxmox VE
- Jenkins CI Server Configuration -- *Will be moved from fr_web_api project to this repository*
- High Availability Setup for Nginx
- High Availability Setup for HAProxy
- RabbitMQ
- Redis
- Oracle Java8
- Samba Server Configuration
- NFS Configuration


## Running the Playbooks
`ansible-playbook` command line tool will be used to run individual [Playbooks](http://docs.ansible.com/ansible/latest/playbooks.html).

### Create A New VM on Nevalabs Proxmox VE _(Be Carefull!)_
`$ ansible-playbook spinup-kvm.yml -v`

### Create Staging Environment for Corvo _(Contains 11 Server Configurations)_

VMs or physical servers should have been created.

`$ ansible-playbook site.yml --ask-become-pass -v`

### Applying updates
`ansible-playbook rolling_update.yml --ask-become-pass -v`

For partial update(s)
`ansible-playbook rolling_update.yml --tags="rust" --ask-become-pass -v`