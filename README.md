# ansible-apache

This Ansible role installs the Apache web server, along with some modules and libraries

### Requirements

* A Debian machine running an SSH server and a user account with ``sudo`` permission

## Role variables

* ``packages``: List of [packages](vars/main.yml). Override in order to specify specific versions or extra packages. When overriding, be aware that the initial value of ``packages`` doesn't hold anymore, so you need to specify all packages you'd like to install.
* ``enabled_modules``: List of Apache modules to enable
* ``disabled_modules``: List of Apache modules to disable

## Examples

    playbook.yml

    ---
    hosts: all
    remote_user: foo
    sudo: yes
    roles:
     - {role: "ansible-apache"}

Invoke playbook
    
    ansible-playbook --ask-pass playbook.yml

