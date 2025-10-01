# Xiple's homelab

## Installation

1. Install ansible.
2. Set up public key authentication to homelab server.
3. Clone or download this repository to your local drive
4. Update inventory file `hosts.ini` if needed.
5. Run `ansible-galaxy install -r requirements.yml` inside this directory to install required Ansible roles.
6. Run `ansible-playbook main.yml --ask-become-pass` inside this directory.

## Test the playbook

Test the playbook using Vagrant. A `Vagrantfile` is included in the project.

```sh
cd ansible-playbook-homelab
vagrant up

# if you need to restart ansible provisioning, run :
vagrant provision
```
