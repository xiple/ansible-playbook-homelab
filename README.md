Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

Before using the role, run :

ansible-galaxy install geerlingguy.docker

Example Vagrantfile
----------------

```ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :

VAGRANTFILE_API_VERSION = "2"

Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|
  config.vm.box = "generic/debian12"
  config.vm.box_version = "4.3.12"

  # to speed up VM creation disable sync folder
  config.vm.synced_folder ".", "/vagrant", disabled: true

  config.vm.provider :virtualbox do |v|
    v.memory = 512
  end

  # to speed up VM creation, keep insecure ssh key
  config.ssh.insert_key = false

  # Ansible provisioner.
  config.vm.provision :ansible do |ansible|
    ansible.playbook = "playbook.yml"
  end

end
```

Example Playbook
----------------

```yaml
- hosts: all
  become: yes
  roles:
    - geerlingguy.docker
    - ansible-role-homelab
```

License
-------

MIT

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
