# Ansible script to deploy a personal development server

Tired do do all installations manually, I am trying to setup everything
in an ansible playbook. It will be a good training exercise and I am 
expecting to save some time the next time that I will have to do it again.

Typically for me a private development server contains:
* an apache server on https
* a jenkins server
* a mysql server
* php
* some php tools

In this play book, sensitive data are encrypted, especially the inventory.
The inventory onctains a single entry:

[flub78]
target_domain:ansible_port ansible_become_password=password

## To run it
ansible-playbook -i hosts --ask-vault-pass dev_server.yml
or
ansible-playbook -i hosts dev_server.yml
