# Ansible playbook for homelab creation

[![CI](https://github.com/xiple/ansible-playbook-homelab/actions/workflows/ci.yml/badge.svg)](https://github.com/xiple/ansible-playbook-homelab/actions/workflows/ci.yml)

## Installation

1. Install ansible.
2. Set up public key authentication to homelab server.
3. Clone or download this repository to your local drive
4. Update inventory file `inventory` if needed.
5. Run `ansible-galaxy install -r requirements.yml` inside this directory to install required Ansible roles.
6. Run the playbook with :

```bash
ansible-playbook main.yml \
    --ask-become-pass \
    --extra-vars "homelab_user=debian"
```

## Notes

This playbook has been tested with molecule using a Debian 13 podman image.

Run `molecule test` to start the entire molecule test workflow (need molecule to be installed).
