Ansible configuration
=====

Ansible configuration for single page app and accompanying backend server.

To install ansible dependencies:

`ansible-galaxy install -r requirements.yml`

To test out this playbook you can use vagrant:

* change `Vangrantfile` and specify which role you want to deploy
* `vagrant up` will start the box and provision it
* `vagrant up` will provision again

To install it on servers use:

`ansible-playbook -i hosts playbook.yml --vault-password-file=~/.vault_pass.txt`

This playbook show cases:

* setting up nginx server
* setting up account for deployments
* remote syslog to papertrail
* letsencrypt certificates generation
* swap file creation
* runit configuration
* rbenv configuration
* using encrypted vaults