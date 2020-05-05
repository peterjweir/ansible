# Basic Ansible Configurations for Desktop and Workstations

## Using to configure a fresh machine ##

### Installing ansible locally ###

Run the appropriate script from ./manual_scripts/ansible_install/ with sudo

Example:
```
sudo ./manual_scripts/ansible_install/ansible_install_ubuntu_20.04.sh
```

This allows you to use ansible locally to configure the machine as opposed to registering it with a remote ansible instance like Tower.

### Install ansible galaxy modules ###
Installs requied 3rd party playbooks

### Run ansible to configure machine ###
```
ansible-playbook -u=$USER --connection=local -i localhost.inventory.yml dev_desktop.yml -K
```
Will prompt for BECOME password, in this context, this is current user's password required to run sudoss.

## Table of Contents ##

### group_vars/ ###
Global variables for this repo.

### manual_scripts/ ###
Contains scripts for things that are best done run manually.

### roles/ ###
This directory is where all the magic happens.  Contains the various 'plays' for ansible to do the installations of various tools and such.

### ansible.cfg ###
Config file for ansible.

### dev_desktop.yml ###
Ansible 'playbook' for development desktop machine.

### inventory.localhost.yml ###
Inventory file for installing on localhost.

## Notes ##
structure loosely based on https://docs.ansible.com/ansible/latest/user_guide/playbooks_best_practices.html
